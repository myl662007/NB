##nsq消息队列
- 介绍
        
        NSQ是实时分布式消息传递平台。
- 安装
    
        brew install nsq
- nsq的组件

        nsqd：一个负责接收、排队、转发消息到客户端的守护进程
        nsqlookupd：管理拓扑信息, 用于收集nsqd上报的topic和channel,并提供最终一致性的发现服务的守护进程
        nsqadmin：一套Web用户界面，可实时查看集群的统计数据和执行相应的管理任务
        utilities：基础功能、数据流处理工具，如nsq_stat、nsq_tail、nsq_to_file、nsq_to_http、nsq_to_nsq、to_nsq
