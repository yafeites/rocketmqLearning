# RocketMQ源码分析之环境搭建 

### MQ下载地址

https://www.apache.org/dyn/closer.cgi?path=rocketmq/4.7.1/rocketmq-all-4.7.1-source-release.zip



下载Binary包和Source包,将Binary包中的Conf文件夹下的broker.conf和logback_broker.xml和logback_namesrv.xml复制到Source包中RocketMQ中的新建的RocketData中的Conf中

![image.png](未命名.assets/1593416170779-4f6db954-147b-4467-aa6a-017e640f67f2.png)

![image.png](未命名.assets/1593416414796-7cfd0d47-8783-49aa-b97b-2d29ca28b392.png)



###  启动nameServer

设置运行参数

![image.png](未命名.assets/1593416624918-3021158c-d039-4be6-ad72-2296b15fba68.png)ROCKETMQ_HOME=D://rocketmq/rocketmq-all-4.7.1-source-release/RocketData

###  启动Broker



![image.png](未命名.assets/1593416675897-1279621e-2003-462b-b625-d9bf2811bfc9.png)

Program arguments: -c D://rocketmq/rocketmq-all-4.7.1-source-release/RocketData/conf/broker.conf  -n 127.0.0.1:9876

VM options: -server -Xms4g -Xmx4g -Xmn2g



###  启动测试用例

#### Consumer

org\apache\rocketmq\example\quickstart\Consumer.java

![image.png](未命名.assets/1593416894136-78c85585-3747-4733-b652-24ffd5e53fce.png)

运行结果

![image.png](未命名.assets/1593417118586-5c5c01ff-0fd2-46e7-abc4-1871c6c2fe47.png)

#### Provider

org\apache\rocketmq\example\quickstart\Producer.java

![image.png](未命名.assets/1593417012292-7be07249-59fc-42e5-8bf6-e0b927646663.png)

运行结果

![image.png](未命名.assets/1593417078228-f2bca08d-4f06-4634-a35c-0705f26a4b2e.png)