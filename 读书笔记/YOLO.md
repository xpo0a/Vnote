# YOLO
    结构、与已有知识的联系
    （良好心理表征是啥）
    YOLO是啥啊？
    YOLO能做什么？
    YOLO特点是啥？
    YOLO用到了机器学习、统计学习方法、深度学习的哪些内容啊？
    YOLO这个网络，你觉得怎么样？给个评价吧
## 1.初步印象
    YOLO you look only once
    单独的end to end 网络，输入：原始图像 输出：物体类别、位置
    回归问题
    没有显示的求取 region proposal
## YOLO步骤
     1.resize图片 448*448
     2.448*448分成S*S个格子
     3.每个格子输出 Bounding box信息（物体中心点坐标(x,y) BoundingBox 宽度W 高度H confidence 是否包含位置、物体位置的准确性）X Y W H confidence
     
