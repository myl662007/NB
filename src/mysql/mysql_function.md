##数据库常用函数

1. find_in_set() 用来判断某个值是否在字段中

        案例：
        $branchId = 5; $branchIdList = 1,2,3,4,55 
        find_in_set($branchId,$branchIdList)
