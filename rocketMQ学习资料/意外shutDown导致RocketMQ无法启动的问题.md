# 意外shutDown导致RocketMQ无法启动的问题

### NameServer

启动会出现 Address already in use:的情况

**解决方法**

先找到哪个进程占用9876端口

**netstat -ano**

**![image.png](意外shutDown导致RocketMQ无法启动的问题.assets/1594174640682-317f1198-6797-41aa-b9c3-dccd25434174.png)**

利用taskkill /f /im 8244 删除即可



### Broker

![image.png](意外shutDown导致RocketMQ无法启动的问题.assets/1594174715258-4e43ee65-6e2e-454b-a453-f9e5a492d532.png)

![image.png](意外shutDown导致RocketMQ无法启动的问题.assets/1594174906265-ad9f6a10-fa0f-4ff6-864b-171fdff08a45.png)

原因也是程序没关,Lock文件被锁



**解决方法：**

**
**

打开资源管理器,点击性能

![image.png](意外shutDown导致RocketMQ无法启动的问题.assets/1594175167041-d5e6b6e9-870c-43c8-a9b2-1380586ad84c.png)

打开资源监视器

![image.png](意外shutDown导致RocketMQ无法启动的问题.assets/1594175186167-2b47a069-aec6-4a50-bfc4-876b99e5f1a1.png)

选择cpu

![image.png](意外shutDown导致RocketMQ无法启动的问题.assets/1594175214514-a403faa3-8ee7-455c-8790-7e10ad60c604.png)

将被锁文件输入即可找到对应的进程,杀了即可

![image.png](意外shutDown导致RocketMQ无法启动的问题.assets/1594175241251-12ea32c0-6448-40c3-b1bd-1c9a2fefaecd.png)