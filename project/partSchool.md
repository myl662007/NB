##省委党校项目

- 线上地址
    
## 命令       
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
        
##项目
- 研究生管理
    
        user前端用户表
        
        在线报名：graduate_sign_up在线报名
                graduate_duty_rank职级表

- 系统管理-配置管理-添加配置

        位置：configBundle-DataFixtures-ConfigFixture.php
        php bin/console doctrine:fixtures:load --append
        
        
涉及到的系统函数：
    
        array_keys()
        array_walk()
        strpos($className, ':')获取参数2在参数1中，第一次出现的位置

## 功能
- 人员选择
        
        twig方法：research_select_html（$entity, $groupName = '', $selectType = '', $isWrite = true, $btnAttrs = [], $isAutoSave = true, $style = 0）
            参数：$entity 可以传实体对象，也可以传字符串（twig中new了一个对象）
                 $groupName 组名，区分多种类型实体
                 $selectType
                 $isWrite
                 $btnAttrs
                 $isAutoSave
                 $style
                 
- twig如何引入service
        
        $this->selectUserOrDepartmentService = $this->container->get('research.select_user_or_department_service');

- PHP中static::class用来获取父类

- 密码设置
    
        /**
         *
         * @var \Symfony\Component\Security\Core\Encoder\UserPasswordEncoder $encoder
         */
        $encoder = $this->container->get('security.password_encoder');
        if (empty($password) || strlen($password)==0) {
            $password = 'lcp@0578';
        }
        $password = $encoder->encodePassword($user, $password);
        $user->setPassword($password);
        $salt = uniqid();
        $user->setSalt($salt);

- 配置：
    
        
