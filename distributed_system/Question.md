# 0.通信流程
1.采集设备连接中央服务器，得到集群服务器的地址，小车断开与中央服务器连接，接着连接集群服务器
2.集群服务器拿到数据传给计算工作站，工作站计算结果，传给集群服务器
3.集群服务器
    a.测重、测膘->值
    b.盘点->值+掩模（限位栏->框 猪的位置，群养栏->不同颜色标注猪）
    发送a 给 中央服务器->云端监控
    发送a 给 测重客户端->得到回复，流程结束（客户端公司写的）
    发送b 给 盘点客户端->云端监控

！！！！！！！！！！！！

测重用深度图
盘点用RGB

客户端类型type
1.限位栏母猪-测重=测重+测膘
2.群养栏育肥猪-测重
3.群养栏育肥猪-盘点
4.限位栏母猪-盘点（0,1）

conda activate tensorflow

# 1.Boost 问题
[asio](https://zhuanlan.zhihu.com/p/39973955)
简单教程

# 2.常见Bug
list index out fo range ：与cluster 连接失败

# 3.工作站启动流程
    1号工作站：cluster -> inventory 03/ inventory 04/ fat 01 /pretreat ->center
    2号工作站：pretreat weight
    启动流程-> 1号工作站：cluster -> inventory 03/ inventory 04/ fat 01 /pretreat ，2号工作站：pretreat weight，一号工作站：center
    向日葵 用户名：ubuntu 密码：xl123456
huanging
| 服务器名称    |   用户名  |   密码  |   备注  |
| :-: | :-: | :-: | :-: |
|  QA-No.1 | ubuntu    |  xl16   |     |
|   QA-No.2 | ubuntu     |     |   ctrl+A+D返回上一菜单  |
|   QA-No.3|  huanging   |     |     |
|QA-No.4     |  ubuntu   |     |     |
screen -ls （查看进程名）
screen -r 设备号
kill 进程名
conda activate xxx
QA-No.1 inventory /pretreat 均tensorflow(其余均pytorch)  fat
QA-No.2 pretreat weight
QA-No.3 测试用，对应 2号
QA-No.4 测试用，对应1号
1~4 均在公司
pretreat启动,conda activate tensorflow  ./workstation

日常维护任务：

    早晨
    QA-No.1 将/Documents/Product/cluster/中的昨日文件        （depth、depthtxt、rgb手动移到 B，删除原有）
    B=2.0TB Volume /home/ubuntu/Documents/product/back
    早晚：
    看服务器崩了没，崩了则重启


图片没传全
Computer





