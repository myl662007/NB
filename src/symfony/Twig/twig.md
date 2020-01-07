## twig常用操作：

### 在使用Symphony项目时，需要一些常用的twig，经过自己做的几个项目，自己的总结如下：

- twig-数据判断

        有时候在使用后台传给前台数据时需要判断是否有这个值，（是否为空(”或null)或是否定义defined或is empty）

        多维数组时：
        {% if item.image is defined %}
            <div class=”trade-show-imgs”>
                {% for img in item.image %}
                    {% if img != “” %}
                        <div class=”trade-show-box”>
                        <img class=”small-img” src=”{{ asset(‘image/member/order/’) }}{{ img }}” alt=”” title=”” />
                        </div>
                    {% endif %}
                {% endfor %}
            </div>
        {% endif %}
    
- 拼接url(一种是路由path，一种是路径asset)，使用replace()转换

        var dataid = data[i].id;
        var dataimg = data[i].brand_image;
        var idurl = “{{ path(‘zm_member_myCar_choose_series’,{‘id’:’dataId’})}}”;
        idurl = idurl.replace(“dataId”,dataid);
        var idimg = “{{ asset(‘image/brand/’) }}{{ ‘dataImg’ }}”;
        idimg = idimg.replace(“dataImg”,dataimg);
        
- 后台传的是多维数组，且第一维数组中是A,B,C,F,G,R等字母，其中包含数组
       
        如图所示：{D77246D3-3585-4BDB-BC9D-E33FB2A72DBA}
        {% for key,item in result %}
            <div class=”lettlecity”>
                <div class=”lettletitle”>{{ key }}</div>
                {% for items in item %}
                    <a href=”{{ path(‘zm_frontend_set_city’,{‘id’:items.id}) }}” class=”lettlebox”>{{ items.name }}</a>
                {% endfor %}
            </div>
        {% endfor %}
        
- twig路由

        1.最简单的：{{ path(‘zm_frontend_index_search’) }}
        2.带ajax的: {{ path(‘zm_member_address_info_ajax’) }}
        3.拼接id的：{{ path(‘zm_member_order_show’,{‘id’:review_info[‘id’]}) }}
        4.拼接Id 和type的：{{path(‘zm_member_favorites_action_ajax’,{‘id’:’storeid’,’type’:1})}}
        5.带排序的：<a class=”” href=”{{ url }}&order=grade&{% if filter.sort == “DESC” %}sort=ASC{%else%}sort=DESC{%endif%}”>好评</a>
        6.搜索在url中拼接（？和&）：href=”{{ path(‘zm_frontend_store_list’) }}?manufacturer_id={{ manufacturers.id }}{% if filter.district_id != ” %}&district_id={{ filter.district_id }}{% endif %}”

- 将后台传来的数据，转换另一种格式

        （1）{{ data.market_price |number_format }}元（如89.00转换为89）
        （2）提取需要长度的字符串 {{ app.session.get(‘city_name’)[0:2] }}（如北京市提取出北京）
        （3）文章格式输出 {{ data.content |raw }}
        （4）日期格式（如2015-8-23 11:20:45） {{orderlists[‘date_added’] |date(‘Y-m-d’)}}&nbsp;{{orderlists[‘date_added’] |date(‘H:i:s’)}}

- {% set  %} 设置变量

        {% if reply is defined %}
            {% set floor = 2 %}
            {% for item in reply %}
                <p class=”message-floor”>{{ floor }}楼</p>
            {% set floor = floor+1 %}
            {% endfor %}
        {% endif %}
        
- twig循环-样式不同的（利用loop.index:从1开始）

        {% for storelists in local_master %}
        <div  {% if loop.index == “1” %}style=”background: #c51a1a”
        {% elseif loop.index == “2” %}style=”background: #1a53c5″
        {% endif %}class=”maintenance-men-list”></div>
        {% endfor %}

- 分页

        后台一般也写好分页，所有的分页都是一样的，我们前端再定义一个都可以引用到的样式
        只需调用{{ render|raw }}即可

- session

        利用session可以获得用户信息（如名称，号码，甚至头像），也可以获得定位的城市
        如：
        {{ app.session.get(‘member_name’) }}
        {{ app.session.get(‘city_name’) }}
