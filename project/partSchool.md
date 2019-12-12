##省委党校项目

- 常用命令

        加载菜单：php bin/console menu:load
        
        清除缓存命令（此命令包含了清除redis里面的doctrine缓存）：php bin/console kit:cache:clear
        
        

- 

        $numberService = $this->get('kit.number_service');
        dump($numberService->toChinese(2019));
