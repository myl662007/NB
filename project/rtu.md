##项目

- 项目思路梳理：

        通过twig获取设备状态 address_status(address)
        通过redis获取他的状态

- 

GatewayListener

- 请求接口
        禹门口： 
        监听：GatewayListener
        需要参数：
            
            app_id:1541419779
            app_token:84d63db047d0e20f24c0ab9025920e24
        
        台兰河：
            app_id:1099700001
            app_token:078c3067fcf7263fde8d6adc667dea9f
            
- sql数据修改

        select a.id,a.address,a.roar_width,a.offset,b.roar_width,b.offset from device as a left join devices b on a.address=b.address where a.project_code='1541419779';
        
        update device as a JOIN devices as b ON a.address=b.address set a.offset=b.offset,a.roar_width=b.roar_width where a.project_code='1541419779';
