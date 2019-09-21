##redis

    <?php
    namespace app\redis\controller;
    
    use Redis;
    
    class Index
    {
        public function index()
        {
            //实例化对象
            $redis = new Redis();
            $redis->connect('127.0.0.1', 6379);
            $redis->flushAll();
    
            //字符串
            $redis->set("test","愿有你的每一天，都是那么幸福");
            echo $redis->get("test")."</br>";
    
            //数组(存储需要序列化)
            $data = ['me','mother','father'];
            $redis->set('data',serialize($data));
            echo $redis->get('data')."</br>";
    
            //增加和减少
            $redis->set("num",2);
            echo $redis->incrBy('num',3)."</br>";
            echo $redis->decrBy('num',1)."</br>";
            echo $redis->get('num')."</br>";
            $redis->del('num');
    
            //lists链表
            $redis->lpush('key1','order1');
            $redis->lpush('key1','order2');
            $redis->lpush('key1','order3');
            $redis->lpush('key1','order4');
            $redis->lpush('key1','order5');
            $result = $redis->lRange('key1',0,-1);
            var_dump($result);
            echo "</br>";
    
            //lists删除
            $redis->lPop('key1');
            $redis->rPop('key1');
            $res = $redis->lRange('key1',0,-1);
            var_dump($res);
            echo "</br>";
    
            //lists链表
            $redis->lSet('key1',2,'订单5');
            $res_one = $redis->lRange('key1',0,-1);
            dump($res_one);
            dump($redis->lLen('key1'));
            echo "</br>";
    
            $redis->lRem('key1','订单5',1);
            $res_one = $redis->lRange('key1',0,-1);
            dump($res_one);
            dump($redis->lLen('key1'));
            echo "</br>";
    
            //hashes哈希结构数据 hset，hget,hlen,hdel,hexists
    
            //sets集合类型数据
            //flushAll()，清空内存中的所有数据
            //sAdd，添加元素
            //sMembers()，查询数组的成员
    
    
        }
    }
