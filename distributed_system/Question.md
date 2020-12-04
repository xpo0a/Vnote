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
### 1号工作站
    center
    cluster
    inventory 03,04 命令，conda activate tensorflow python main.py
    pretreat 命令，conda activate tensorflow，./workstation
    fat01 conda activate pytorch python main.py
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
QA-No.2 pretreat（tensorflow） weight
QA-No.3 测试用，对应 2号
QA-No.4 测试用，对应1号
1~4 均在公司
pretreat启动,conda activate tensorflow  ./workstation
### 2号工作站
    screen 上层目录
    查看，杀死进程 screen - kill + 进程名
    运行 测重，


日常维护任务：

    早晨
    QA-No.1 将/Documents/Product/cluster/中的昨日文件        （depth、depthtxt、rgb手动移到 B，删除原有）
    B=2.0TB Volume /home/ubuntu/Documents/product/back
    早晚：
    看服务器崩了没，崩了则重启


图片没传全
Computer

#### 工作计划
    1.log修改
        md5+imgsize 等等
    2.越界访问
        哪个变量，数组，是动态的，动态变量没被释放(delete)
    3.PNG格式改成JPG(imencode) (x)
        压缩率
    4.main 定义的锁，删除无用的锁，拆开用冲突的锁，换重复的锁、共享锁、独占锁 (x)
    5.cluster 中的重连功能
    6.补充其他部分的 READ.ME

### 发生的bug
    2号工作站：
        weight : list index out of range 列表无一个元素
    1号工作站：
    fat01问题： imgLength= int (lengthrecv.split('^_^'))崩掉了
    cluster: terminate called after throwing an instance of 'std::bad_alloc' !!!!内存不够，new获取内存空间失败，内存没及时释放掉，new 完，没delete
    vector clear
    更新服务器过程中，发现了一个bug，cluster_to workstation to equipment new的动态变量没被delete
    pretreat换了流程

内存不足，
    更新服务器过程中，发现了一个bug，cluster_to workstation to equipment new的动态变量没被delete
1.分布式日常维护
2.完善log、盘点图片格式修改为JPG、完善mutex、BUG(bad_alloc)
3.复习 统计学习方法

1.分布式日常维护
2.代码中添加README.md，学习代码测试
3.学习《Effective C++》第三章、AdaBoost
