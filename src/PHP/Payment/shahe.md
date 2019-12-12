## 支付宝沙河测试支付

- 相关支付宝地址
    
        沙盒环境：https://openhome.alipay.com/platform/appDaily.htm?tab=account
        PHP版本的demo: https://docs.open.alipay.com/270/106291/
        下载密钥生成工具: https://docs.open.alipay.com/291/105971

- 沙盒步骤：

        1.沙箱位置-》开发者中心>研发服务
        
        2.密钥配置
            
        下载密钥生成工具（https://docs.open.alipay.com/291/105971）
        下载完成后按照页面详细操作步骤生成密钥（https://docs.open.alipay.com/291/105971）

        3.配置沙箱环境
        
        进入商户的管理中心，进入开发者中心->研发服务的沙箱应用
        按照上一步生成的应用公钥进行设置
        
        4.应用配置
          
        修改配置文件config.php
        app_id（应用ID）和gatewayUrl（支付宝网关）可以登录商户账号，进入开发者中心—>沙箱环境即可查看
        merchant_private_key（商户私钥）为刚才生成的私钥
        alipay_public_key（支付宝公钥）为设置应用公钥后生成的支付宝公钥

        5、配置php环境
        
        查看php环境，开启PHP的 php_openssl
        打开php.ini，确认开启 php_openssl

        6、访问index.php

- thinkphp对接需要注意：
        
        1.think PHP对接，需要include_once引入vendon下的sdk
