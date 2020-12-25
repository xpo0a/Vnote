这是一个目录、索引
别闹了，Mr.Feynman 
### 线性回归
### 代价函数 J
    误差函数
### 梯度下降法（最快下山算法）
    对J(山) 求梯度(看周围哪里下山最快)，沿着梯度下降的方向行走，接着重复，求梯度。。。
### 多元梯度下降法
    多个特征 特征缩放(对不同的特征进行 放缩，让他们相互匹配) 迭代
    多元无/有 条件极值 拉格朗日乘数法
### 朴素贝叶斯分类 （分类法）
    您还记得朴素贝叶斯的细节吗，要是忘了，给你30min 回顾一下
    要求：Feynman 讲通
    [1](https://www.cnblogs.com/geo-will/p/10468401.html)
    [2](https://blog.csdn.net/qiu_zhi_liao/article/details/90671932)
    [3](https://www.jianshu.com/p/b6cadf53b8b8)
### K近邻法 Knn
### HMM
### 聚类
    1.聚类任务
    2.性能度量
    3.距离计算
    4.原型、密度、层次 聚类
### 分割模型
    目标检测，在图中绘制出目标框
    目标分类，车、人、动物
### 分类与回归
    分类：离散、标签
    回归：连续、预测
### 隐马尔科夫模型 HMM
    HMM 中文分词：
	5个隐含状态：BME S
	观测值：今天天气不错呀
	分词：今(B)天(E) 天(B)气(E) 不(B)错(E) 呀(S)
	结果：今天/天气/不错/呀
	输入：观测值序列
	输出：转态值序列
	初始状态概率分布
	转移概率矩阵：齐次马尔科夫链，维特比算法，对比概率
### AdaBoost
![扫描 2020年12月9日 下午8](_v_images/20201209205640223_21584.jpg =937x)
![扫描 2020年12月9日 下午8](_v_images/20201209205725039_23202.jpg =1073x)

    回答我：后向误差是啥啊，咋传播的，有啥影响啊
    Relu通，反向导数通，比较有难度的是对矩阵求偏导运算，改变w，b的值
    神经网络，能找到良好的心理表征吗？（理性认识+感性认识）
### 模型评估参数
#### 0.查准率（precesion） 查全率（recall）
    感性：
    以挑西瓜为例，瓜有好瓜（甜）、坏瓜（不甜），总瓜有100个，训练出N个特征，特征对瓜判断的效果（权重）不同
    希望查准率P 高，即 挑出好瓜的准度更高，那么就会“宁缺毋滥”
    希望查全率R 高，即 挑出更多的好瓜，那么就会“宁可错挑，绝不放过”
    理性：
    True/False + Positive/Negative
    判断 正确/错误 + 原来是 正例/反例
    eg. TP:正例判对    TN:反例盘对    FP:正例判错    FN:反例判错 这个是错的。
    eg. TP:判对为正    TN:判对为反    FP:判错为正    FN:判错为反 
    查准率=TP/（TP + FP） 真正判对的/判对的  （对的判错不管）
    
    查全率=TP/ (TP + FN) 真正判对的/所有对的
### 神经网络
[神经网络是啥呀](https://www.cnblogs.com/maybe2030/p/5597716.html)
[后向传播算法是干嘛的](https://www.cnblogs.com/charlotte77/p/5629865.html)

### 卷积神经网络 CNN
[参考文档1](https://www.cnblogs.com/wj-1314/p/9593364.html)
[参考文档2](https://www.jianshu.com/p/1ea2949c0056)
    
    （请打开文档，按照思路走）
    特征提取，哪些特征是有用的，哪些特征是重要的？
    输入层：预处理 取均值 归一化 PCA/SVD
    结构：
        Input layer:
        Conv layer:
        ReLU layer:激活函数（分段）sigmoid TanH ReLU
        Polling layer:
        Full Connected layer: FC 全连接，ReLU前的最后一层Conv layer，！！！将各个representation整合成一个值，想想Taylor公式吧，用多项式函数去近似拟合光滑函数
### 全连接层、卷积层、池化层
    不懂么？
[看看这个block吧](https://blog.csdn.net/m0_37407756/article/details/80904580)

    全连接层：将局部特征（feature map）全连接起来
    卷积层（Filter）：提取局部特征，输入FeatureMap to 输出FeatureMap
    池化层：缩小输入FeatureMap规模，通道数不变，取min max average（算数平均Mean 中位数Median 众数Mode）...

模型设计，模型结构，还有训练方法
### 反向传播算法
[参考1](https://zhuanlan.zhihu.com/p/79657669)
[实例计算](https://www.cnblogs.com/charlotte77/p/5629865.html)
[反向传播-计算图](https://blog.csdn.net/wzw12315/article/details/80856698)

    计算图：直观展示计算过程
    节点（局部计算）->图（全局计算）
    正向传播 ReLu 反向传播 求导
![](_v_images/20201222101033709_17744.png =604x)





