Docker container monitor plugin for Open-Falcon  Micadvisor-Open
--------------
描述
--------
本项目是基于小米开发的micadvisor_open项目，对上报数据引擎进行了修改，使其更容易维护和扩展，并且减少了依赖包.

build和启动方法：
-----------------
```bash
chmod +x cadvisor
chmod +x build.sh
./build.sh
```
注：

```
1  容器的启动参数在build文件中，参数含义都无变化
2  修正了之前取值错误的问题
3  修正了数据断线的问题
4  pushDatas.go 为主上报程序，都有中文注释，有些上报指标被隐藏了，去掉注释即可使用。
5  增加了更多异常log,方便问题排查
```

编译和运行环境
-------------------------
docker v1.12.1</p>
golang v1.6.3

采集的指标
--------------------------
| Counters | Notes|
|-----|------|
|cpu.loadaverage|cpu的平均负载|
|cpu.usageTotalSec|cpu的整体负载,单位秒|
|disk.io.read_MBps|硬盘读取速度，单位MBps|
|disk.io.write_MBps|硬盘写入速度，单位MBps|
|mem.memtotal|内存总量，即容器的内存limit值|
|mem.memused|内存使用量|
|mem.totalUsed.percent|整体内存使用占比|
|mem.Rss.percent| RSS在内存总量中的占比|
|mem.cache.percent| Cache在内存总量中的占比|
|mem.WorkingSet.percent| WorkingSet在内存总量中的占比|
|net.rx.KBps|网卡接收数据包速度,单位KBps|
|net.rxDrop.packets|网卡收包丢包量,单位包|
|net.tx.KBps|网卡发送数据包速度,单位KBps|
|net.txDrop.packets|网卡发包丢包量,单位包|



Contributors
------------------------------------------
原项目作者：mengzhuo   QQ:296142139, MAIL:mengzhuo@x.com </p>
本项目作者: yihongfei  QQ:413999317, MAIL:yihongfei@x.com
