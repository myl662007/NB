##省委党校项目

- 常用命令

        加载菜单：php bin/console menu:load
        
        清除缓存命令（此命令包含了清除redis里面的doctrine缓存）：php bin/console kit:cache:clear
        
        更新entity: php bin/console doctrine:generate:entities
        
        更新datafixtures: php bin/console doctrine:fixtures:load --append
        
        创建数据表：php bin/console kit:doctrine:generate:entity
        
        生成crudl: php bin/console kit:doctrine:generate:crud:theme --theme=Pintuer     
        
- 数字转中文
        $numberService = $this->get('kit.number_service');
        dump($numberService->toChinese(2019));
        
        //数字转为中文思路：
        定义一个数组，中文汉字,然后循环遍历
        
- 常用电话存到配置中
        
- class     
