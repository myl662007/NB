##禹门口项目

- 综合数据库

    Bundle:DatabaseBundle
    数据库：Default数据库
    
    功能：
        数据库列表：databaseList
        备份与恢复：backups
        日志列表：systemLog
        
    数据库：Dispatch
        Canal 配水点表
        
- 水资源调度

    功能：
        系统首页：
            首页：DispatchBundle\Controller\DefaultController
        
        水雨情信息：
            墒情信息：DispatchBundle\Controller\WaterController
            数据表：SoilMoisture（数据如何生成的）
            
            水位流量信息
            干渠：DispatchBundle\Controller\NilometerController
            数据表：waterLine

            支斗口：DispatchBundle\Controller\WaterGaugeController
            数据表：WaterRuler
            
- 移动综合应用

- 水费记收
        
    - 数据表
            
            数据表：irri_water
            数据表：irri_dispath
            
    - 添加灌季
            用水季度：Season
            申报用水计划：SeasonPlan
            
            渠系:dispath  Canal
            Water SeasonWater

- 办公自动化

- 系统管理

##定时任务

- php bin/console api:pull
    
##相关命令：
 
- 命令：
        
        生成用户：php bin/console rbac:create:user -u admin -p lcp@0578
        
        上面导航：php bin/console doctrine:fixtures:load --append

        拉取：php bin/console api:pull:frame
        
        rtu:frame:water
        rtu:frame:waterRuler
### 支付功能


- 从RSA1升级到RSA2？
https://opensupport.alipay.com/support/knowledge/20069/201602242782?ant_source=zsearch

### 流量计


### 相关twig

        station_name(departmentId) 通过departmentId来获取departmentName
















