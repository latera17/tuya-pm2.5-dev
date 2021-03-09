# tuya-pm2.5-dev
This project is developed using Tuya SDK, which enables you to quickly develop branded apps connecting and controlling smart scenarios of many devices.
For more information, please check Tuya Developer Website.

一、方案标题
======================================================================================================
室内PM2.5检测器

二、方案应用场景
======================================================================================================
到了冬季大家就非常关心雾霾天气了,特别是一旦大雾的时候,大家第一时间就会查询官方公布的pm2.5数据,达到一定程度了就会选择戴口罩出门。近期有人说室内pm2.5不一定比室外低,进而很多科学达人就会购买相关设备便携式pm2.5检测仪放在家里测试。如果能在家中检测pm2.5，并且能上报数据到IOT平台，就可以在手机APP中参看到家里的情况。根据这些状态，我们也能控制家里的定时通风或者控制空调等设备。
所以，本方案就是希望解决这个问题。其中本方案的应用场景：

本方案用于检测空气环境中的PM2.5、温度、湿度等参数，以基本反映空气质量指标，。

通过tuyaIOT上传检测测量数据到云平台，并能通过APP控制室内的温湿度条件和排风控制。

此方案可用于楼宇暖通、智能家居、学校 机场车站等场所。


三、方案说明
======================================================================================================
#1.设计要求
本方案是通过参考涂鸦IOT的宠物喂食器的方案中通信方式来设想功能的。
1）监控实时PM2.5、温度、湿度数据，并保存到IOT平台。且能实时查看。基本单元为：
  检测模块 -> 单片机 -> 显示模块
                   -> 继电器控制模块
                   -> wifi模组

2）wifi通信稳定可靠，故障率低。要求wifi模组能以半小时一次的速度上传数据，或能按需传输1小时内的60组数据。并且能上传报警状态。

3）能通过手机APP监控。APP中能实时监控当前的状态，并能在界面中看到异常状态，如数据超标，或通讯故障。

#2.设计材料
涂鸦IOT平台 
  参考宠物喂食器的方案，重新定制上传的参数，和控制的变量。
WBR3 wifi&ble模组
  通过wifi和IOT平台通信。
stm32f103CB
  完成功能逻辑，控制传感器通信和上报数据到wifi模组。
PM2.5检测传感器
  激光PM2.5传感器六度空气HLPM025K3远超夏普0.1分辨率
  测量范围： 0.1ug/m3 ～1000.0ug/m3
  分辨率： 0.1ug/m3
温湿度传感器
  dht11
  精度湿度±5%RH， 温度±2℃，量程湿度5-95%RH， 温度-20~+60℃。
继电器模组
  使用 8路24V继电器模块。
  需要带光耦隔离，以及支持高低电平触发。
家用路由器

四。方案计划
======================================================================================================
3月25前完成

#1）3月9前准备物料及知识储备
  a. 画出整个系统硬件电路图，将需要买的设备下单，齐套。准备好需要用到的工具。
  b.参考IOT平台开发样例。学习平台开发的必要知识。
  c.学习APP面板开发的
#2）3月10-30日嵌入式开发、云开发
  a.参加涂鸦【宠物喂食器】实战训练营培训。
  b.完成整个系统硬件电路的搭建。
  c.学习模组SDK开发过程，使用云平台的SDK搭建本方案中数据上传和命令下达的方案。
  d.开始嵌入式软件开发,完成stm32f103cb控制功能。
  e.软硬件功能联调。
  f.APP开发，主要是APP面板的设计。
#3）4月10日前整体调试。
  a.查漏补缺，优化使用上问题，主要是易用性的问题。
  b.方案完工。上传相关开发资料到github中
  c.录制方案演示相关的资料。
