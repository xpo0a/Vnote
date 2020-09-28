#  0.Python 目录(你得知道该去哪里找吧）
# 1.基本语法
## 1.0数据类型
```x
    Number
        int float bool complex(复数)
    String
        str='HelloWorld'
        索引
            前索引 0~N
            后索引 -N-1~-1
        str[1]
        str[2:5]输出2~5
        str[2:-1]输出2,~尾-1
    List 列表
        list = [ 'abcd', 786 , 2.23, 'runoob', 70.2 ]//可修改
    Tuple 元组
        tuple = ( 'abcd', 786 , 2.23, 'runoob', 70.2  )//不可修改
    Set
        set = { 'abcd', 786 , 2.23, 'runoob', 70.2  }//不重复
    Dictionary
```
## 1.1 print()
    print('HelloWorld')
    print("HelloWorld")
    print('Hello'+'World')  //HelloWorld
## 1.2 运算符
    %取余 //取整 **幂
    == != > < >=
## 1.3 循环、判断
```x
    while a>b:
        xxx1
        xxx2
    else :
        xxx3
```
```x
    for <1> in <2>: //遍历<2>
        xxx1
    else :
        xxx2
        break
```
```x
    if xxx:
    else xxx:
    doge=str(intput("emoji"))
```
```x
    elif==else+if 
    eg.
    if xxx1:
    elif xxx2:
    else xxx3://优先级低于if 但高于else
```
## 1.4 函数
    def Fun1(A1,A1...) //函数定义
## 1.5 文件读写
    append_text='Hlelang \n This is a Joke.'
    my_file=open('FileName','r+w')//创建文件
## 1.6 class类
```x
    class Calculator :
        name='FuLg'
        price=18
        def add(x,y)
        result = x+y
        print(result)
    __init__
```
##  1.7 input and print
    a=input("请输入一个数字")
    print("请输入一个数字")
    print格式化
        print("转换后的温度是{:.2f}" .format(c))
    eval(<字符串>) 将字符串最外侧"" ''去掉
        eval("1") >>>1
        eval("1+2") >>>3
    保留字
|          |         |        |        |          |
| -------- | ------- | ------ | ------ | -------- |
| and      | elif    | import | raise  | global   |
| as       | else    | in     | return | nonlocal |
| assert   | except  | is     | try    | True     |
| break    | finally | lambda | while  | False    |
| continue | for     | not    | with   | None     |
| class    | form    | or     | yield  |          |
| def      | if      | pass   | del    |          |

# 2. python 基本图像绘制
    深入理解PYTHON
    蟒蛇绘制
    模块1：turtle库的使用
    turtle分析
## 2.1 深入理解Python
    1946~1981 计算能力，计算机架构
    ~2008 视窗时代
    ~2017 数据问题
|   C    | 理解计算机结构 |  底层设计  |  架构时代  |
| ------ | ------------- | --------- | --------- |
| JAVA   | 理解主客体     | 跨平台     | 视窗时代   |
| C++    | 理解主客体     | 大规模程序 | 视窗时代   |
| Python | 理解问题求解   | 各种问题   | 复杂新时代 |
```Eg2
    #python 花蟒蛇
    import turtle #导入库
    turtle.setup(650, 350, 200, 200)
    #import<库名>
    #<库名>.<函数名>
    #from<库名> import<函数名>
    #import <库名> as <别名>
    #import turtle as T
    #T.penup
    #T.pendown
    turtle.penup()
    turtle.penup()
    turtle.fd(-250)
    turtle.pendown()
    turtle.pensize(25)
    turtle.pencolor("purple")
    turtle.seth(-40)
    for i in range(4):
        turtle.circle(40, 80)
        turtle.circle(-40, 80)
    turtle.circle(40, 80 / 2)
    trutle.fd(40)
    turtle.circle(16, 180)
    turtle.fd(40 * 2 / 3)
    turtle.done()
```

# 3基本数据类型
    数字类型及操作
    eg3 天天向上
    字符串类型及操作
    模块2:time库
    eg4 文本进度条
## 3.1 数字类型 操作
    整数类型
        pow(x,y) #x的y次方
        十进制
        二进制 0B 0b
        八进制 0O 0o
        十六进制 0X 0x
    浮点类型
        round(x ,d) 对x四舍五入，保留d位
    复数类型
            z=1.23e-4+5.6e+89j
            z.real z.imag
    数值运算操作符
        + - * / // % **
    abs(x) divmod(x,y) pow(x,y) round(x,d) int(x) float(x） complex(x）
## 3.2 eg天天向上
    基本问题：持续价值
    一年365天，工作日 进步1% 休息日 退步1%
```x
    x=1.01
    y=0.99
    dayup=pow(x,365)
    daydown=pow(y,365)
    print("向上：{:2f},向下：{:.2f}".format(dayup,daydown))
```
    一年365天，工作日进步1%，休息日退步1% 
    一年进步4.63
```x
    dayup = 1.0
    dayfactor = 0.01
    for i in range(365):
        if i % 7 in [6, 0]:
            dayup = dayup * (1 - dayfactor)
        else:
            dayup = dayup * (1 + dayfactor)
    print("工作日的力量：{:.2f}".format(dayup))
```
    A君：一年365天，每天进步1%不停
    B君：一年365天，每周工作6天休息1天，休息日下降1%，那么B想赶上A，B要努力多少呢？
    B君，每天需进步0.019 %1.9
```x
        def dayUP(df):
        dayup=1
        for i in range(365):
            if i%7 in [6,0]:
                dayup=dayup*(1-0.01)
            else:
                dayup= dayup*(1+df)
        return dayup
    dayfactor=0.01
    while dayUP(dayfactor)<37.78:
        dayfactor+=0.001
    print("工作日的努力参数:{:.4f}".format(dayfactor))
```
## 3.3 字符串类型及操作 
    str:这是字符串的正反序号表吧
| -12 | -11 | -10 | -9  | -8  | -7  | -6  | -5  | -4  | -3  | -2  | -1  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 这  | 是  | 字  | 符  | 串  | 的  | 正  | 反  | 序  | 号  | 表  | 吧  |
| 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  |
    索引: <str>[M]
    str[-1] :吧
    切片：<str>[0:3] 这是字
    str[:3] 这是字
    [1:8:2] 从1~8，步长是2
    [1:8:-1] 逆序
    转义字符 '\'
    字符串可用 ' '   ""  '"  "' 单，双，三引号表示
    字符串运算
        x+y 字符串连接
        x*n 将x重复n次
        x in y y中含有x字符串吗？True False
|           函数名            |              功能              |
| --------------------------- | ----------------------------- |
| len()                       | 长度                           |
| str()                       | 任意类型转换为字符串            |
| hex() oct()                 | 16进制   8进制                 |
| chr()                       | Unicode-->字符                 |
| ord()                       | 字符--->Unicode                |
| str.lower() str.upper()     |                               |
| ---                         | ---                           |
| str.split(xxx)              | 根据xxx,将字符串分开           |
| str.count(a)                | 统计字符串中a出现的次数         |
| str.replace(old,new)        |                               |
| str.center(width,[fillchar] | "python".center(20,"*")       |
| str.strip(chars)            | 将str中的char去掉              |
| str.join(iter)              | ",".join("123456") "1,2,3..." |
    字符串格式化
        槽
        <str>.format(<逗号分隔的参数>)
        "{}是{}的基本{}{}" .format("这","槽format","基本用法",23333)  
        这是槽format的基本基本用法23333
|  :  | 填充 |       对齐       | 宽度 |  ,  | .精度 |             类型             |
| --- | ---- | --------------- | --- | --- | ----- | --------------------------- |
| 引导 |      | 左<>右 ^居中对齐 |     |     |       | 整数类型b c d o x,浮点 e F % |
    "{:=^20}".format("Python") '=======Python======='
        说明 将Python填充到槽处，:引导，填充=，^居中对齐，20长度20
## 3.4 time库
    import tiem
    time.<b>()
    时间获取 ：time ctime gmtime
        time.time() #1599983340.5645614
        time.ctime() #'Sun Sep 13 15:49:31 2020'
        gmtime() #计算机可方便用的时间格式
    时间格式化 : strftime strptime
        strftime(tpl,ts) 将时间ts 按照tpl模板化
            eg. t=time.gmtime()
            time.strftime("%Y-%m-%d %H:%M:%S",t) 格式自行百度
    程序计时 : sleep perf_counter
        perf_counter()
            返回一个CPU的精准时间
        sleep(s) 让程序暂停s秒时间
# 4. 程序控制
    分支结构
    循环结构
    模块3
## 4.1 分支结构
    单分支
        if <>:
            <>
    二分支
        if
        else
    二分支紧凑
        <表达式1> if <条件> else <表达式2>
    多分支
        if
        elif
        elif
        elif
        elif......
## 4.2 条件判断
    与and 或or 非not
    if x=99 or x=98
## 4.3 异常处理
    try:
        <>
    except <异常类型>:
        <>
    else:
        <>
    finally:
        <>
## 4.4 eg5 BMI(Body Mass Index)
    BMI=体重/身高**2
```x
    #BMI.PY
    height, weight = eval(input("请输入身高和体重，用','隔开"))
    bmi = weight / pow(height, 2)
    print("BMI为：{:.2f}".format(bmi))
    who = ""
    if bmi < 18.5:
        who = "z"
    elif 18.5 < bmi < 25:
        who = "x"
    elif 25 < bmi < 30:
        who = "c"
    else:
        who = "肥胖"
    print("BMI指标为：{}".format(who))
```
## 4.5 循环结构
    1.遍历循环
    数字循环
    for <循环变量> in <遍历结构>:
    <语句块>
    for i in range(N): #i从0循环到N-1
        <>
    for i in range(M,N): #i 从M到N-1
    字符串循环
    for char in str: #逐一取出str中的char
    列表循环
    for item in ls:  #遍历ls 中的元素
    文本遍历
    for line in fi :
    2.无限循环
    while <条件>:
        <语句1>
    3.循环保留字
        break: 跳出所在循环
        continue: 跳出本次循环，继续其他循环
    4.循环高级用法
        for <> in <>:
        break
        else:
## 4.6 random库
    import random
    随机数库
    基本随机数函数：seed() random()
    扩展随机数函数:randint(),getrandbits(),uniform(),randrange(),choice(),shuffle()
    
# 5.函数和代码复用
    函数定义与使用
    七段数码管绘制
    代码复用与函数地柜
    模块4：Pyinstaller库的使用
    科赫雪花小包裹
## 5.1 函数定义与使用
```x
    def <函数名>( 参数 ):
        <函数体>
        return<返回值> # return m,n,x
```
    lambda 函数
        匿名函数
## 5.2 代码复用与函数递归
    递归
    def fact(n):
        if n==0: 
            return 1
      else:
       return n*fact(n-1)
##  5.3 模块4 PyInstaller库的使用
    将.py文件转换为各种系统可执行文件
    .py ->windows Linux Macos
    pip install
```雪花
    #Kk.py
    import turtle
    def koch(size,n):
        if n==0:
            turtle.fd(size)
        else:
            for angle in[0,60,-120,60]:
                turtle.left(angle)
                koch(size/3,n-1)

    def main():
        turtle.setup(600,600)
        turtle.penup()
        turtle.goto(-200,100)
        turtle.pendown()
        turtle.pensize(2)
        level=3
        koch(400,3)
        turtle.right(120)
        koch(400,3)
        turtle.right(120)
        koch(400,3)
        turtle.hideturtle()
    main()
    input("xxx")
```
# 6.组合数据类型
    集合类型{}
    序列类型=元组+列表
    字典类型
    模块5 jieba库
## 6.1 集合类型
    不可变数据类型
    无序，类比数学概念--集合
    不可重复
    集合用 { ,  ,  }
    使用set()建立集合
    B=set("Python")  #{'h', 'p', 'o', 'n', 't', 'y'}
    集合操作符
    A|B并 A-B补 A&B并 A^B返回A、B中的不相同的元素
    > < =
    集合处理方法
        S.add(x)  S.discard(x) S.remove(x)  S.clear(x) S.pop() S.copy() len(S) set(x)
```x
    try:
        while True:
            print(A.pop(),end="")
    except:
        pass  #while 是无限循环，当A.pop遇到空元素时，报错，这个错可以被try捕捉到，跳出循环
```
    集合用途
        包含 关系比较
            数据去重复
## 6.2 序列类型
```x
    元素之间有相互关系
    一维元素序列
    序列=字符串+元组+列表
    正向递增(0~N-1) 反向递减(-N~-1)
    操作符
        x in s    x not in s     s+t    s*n s[i]    s[i:j]
        len(s) min() max()#相同类型可比较 s.index()
        [::-1]将序列进行逆向提取
```
```x
    元组
    使用（） 或者不用 来表示
    一旦创建，不可修改
```
```x
    列表
    一种序列类型，可任意修改
    使用[] 或者list()创建
    列表操作符
    ls[i]=x 
    ls[i:j:k]=lt #用lt切片替换ls 中的元素
    del ls[i] 删除列表ls中的第i个元素
    del ls[i:j:k] 删除切片
    ls+=lt 将lt更新到ls中
    ls*=n 将ls重复n次
    ls.append(x) ls最后加一个元素x
    ls.clear() 删除ls
    ls.copy() 拷贝ls中的所有元素
    ls.insert(i,x) 第i位置插入
    ls.pop(i) 取出并删除ls第i位置元素
    ls.remove(x) 将ls中出现的第一个x 元素删除
    ls.reverse() 将ls翻转
```
## 6.3 eg.9
```x
    def dev(numbers,mean):#计算方差
        sdev=0.0
        for num in members:
            sdev=sdev+(num-mean)**2
        return pow()

    def getNum(): #获取不定长度数据
        nums=[]
        iNumStr=input("xxx")
        while iNumStr !="":
            nums.append(eval(iNumStr))
            iNumStr=input("xxx")
        return nums

    def mean (numbers):
        s=0.0
        for num in numbers:
            s=s+num
        return s/len(numbers)
```
## 6.4 字典类型
```x
    {key1:value1, key2:value2, key3...}
    映射= 键(索引)-->数据
    d={键1:数据,键2:数据,键3:数据,键4:数据...}
    操作方法
    del d[k] 删除键d对应的数据
    k in d 键k是否在d中
    d.keys() 返回字典d中所有键的信息
    d.values() 返回字典d中所有值得信息
    d.get(k,<>) 键k在，返回数据 不在返回<>
    d.pop(k,<>) 键k在，取出数据，不在返回<>
    d.popitem() 随机从d中取出一个键值对，以元组形式返回
    d.clear()    删除所有键值对
    len(d) 返回字典中元素的个数
```
    元组() 列表[] 字典、集合{}
    字典类型的应用场景
        元素遍历
            for k in d:
## 6.5 jieba库的使用
    中文分词第三方库
    
# 7.文件的使用
    文件的创建、删除
    文件的打开，读写
    文件的打开
        <句柄>=open (<文件名>,<打开模式>)
        python中\表示转义字符，而windows中默认路径使用\，产生冲突，故使用'/'进行操作，'r'只读模式  'w'覆盖写  'x'创建写 'a'追加写 'b'二进制模式 't'文本模式 '+' r+w+b
    <变量名>.close()
    文件读取
    <f>.read(size=-1) 读入全部内容
    <f>.readline(size=-1) 读一行
    <f>.readlines(x) 读前x行，不给定x 则默认全部读取
    文件写入
    <f>.write(s) 向文件中写入一个字符串
    <f>.writelines(lines) 将列表lines写入到f中
    <f>.seek(offset) 改变当前文件操作指针位置，offset含义，0-文件开头，1-当前位置，2-文件结尾
```X
    fo=open("output.txt","w+")
    ls=["中国","法国","美国"]
    fo.writelines(ls)
    for line in fo:
        print(line)
    fo.close()
    #为什么没输出？？，当执行完fo.writelines(ls)时，文件的指针在ls最末尾，执行for循环时，print打印从当前位置到最末尾的字符串，故无输出
    fo=open("output.txt","w+")
    ls=["中国","法国","美国"]
    fo.writelines(ls)
    fo.seek(0)
    for line in fo:
        print(line)
    fo.close()#此时 可以打印了
```
## 7.1 一维数据的格式化
    一维数据表示：列表 [ ]
    存储
        1.空格分隔
        2.逗号分隔
        3.其他方式（特殊符号 分隔)
## 7.2 二维数据的格式化
    二维
    ls[row][colum]
# 8.Python第三方库
    pypi.org #检索第三方库
    安装方法：pip 文件安装 批量安装
```x
    os库
        操作系统相关的库
        路径操作
        进程管理
        环境参数
    路径操作
        import os.path
        import os.path as op#别名
        op.abspath 返回绝对路径
        os.normpath(path) 归一化表示path，使用//分隔路径
        os.relpath(path) 返回相对路径
        os.dirname(path) 返回path中的目录名称
        os.basename(path) 返回path中最后文件的名称
        os.join(path,*paths) 组合路径
        os.exists(path) 判断path对应地方是否存在
        os.isfile(path) 判断path是否存在文件
        os.isdir() 是否存在目录
        os.getatime()
        os.getmtime()
        os.getctime()
    进程管理
        os.system(path)
    环境参数
```
        
```x
    pip常见命令
    pip install <第三方库> 安装
    pip install -U <第三方库> 更新
    pip uninstall <xxx> 卸载
    pip download <x> 安装
    pip show <> 
    pip search <>
```
    第三方库 自动安装脚本
|      库名      |            用途            |
| -------------- | ------------------------- |
| numpy          | n维数据可视化               |
| matplotlib     | 二维数据可视化              |
| PIL            | 图像处理                   |
| scikit-Learn   | 机器学习和数据挖掘          |
| Requests       | Http协议与网络爬虫          |
| jieba          | 中文分词                   |
| beautiful soup | HTML XML解析库             |
| wheel          | 打包工具                   |
| pyinstaller    | 将python为可执行文件        |
| Django         | web开发框架                |
| flask          | 轻量级web开发工具           |
| werobot        | 微信机器人开发工具          |
| sympy          | 数学符号计算工具            |
| pandas         | 高效数据分析和计算          |
| networkx       | 复杂网络和图结构的建模和分析 |
| PyQT5          | QT开发工具                 |
| pyopengl       | openGL开发工具             |
| docopt         | python命令行解析           |
# 8.类
#dog.py
```x
    class Dog():
        "一次类的简单尝试"

        def __init__(self, name,age):  #约定俗成的方法，在创建类的过程中，将某几个必需的参数捆绑上去，！self表示 创建的实例本身，不可修改
            #每个调用class的函数（方法），都传递实参self
            self.name = name
            self.age = age

        def sit(self):
            print(self.name.title() + " is sitting new")  #。title将字符串标题化

        def roll_over(self):
            print(self.name.title() + " rolled over")


    my_dog = Dog('luku', 6)
    my_dog.sit()
    my_dog.roll_over()
    #体会其中调用方法的感受
```
## 8.1 继承
紧接上面Dog例子
类、继承、多态、访问限制、对象
注意哦 ‘类是不会下海干活的，干活的只有实例’
```x
    class hyena():
        def __init__(self,name,years)
        super().__init__(name,years) #super()是一个特殊函数，让子类包含父类的所有属性--继承
```
## 40来个例子
```x
print("He's %d tall %s wigh"%(my_height,MyWeight)) #多个输出参数了解下
print("He's {:.2f} tall {:.2f} wigh".forma(xxx1,xxx2))
print("Its fleece was white as %r."%'snow')
Num=23333
print("Its fleece was white as %r."%Num)
%r 任意格式打印输出
formatter="%r %r %r"
print(formatter %(1,23,3))3
print(formatter %('one','tow','three'))

days2="Mon Tue Wed Thu Fri Sat Sun"
print("here are the days2",days2)

创建文件
target=open(filename,'w')#句柄
向文件中引入变量
from sys import argv
argv，参数2....参数N=argv
line1=input("xxx)
target.write(line\n)
target.close()

xxx=open(file_name,'x')
w+ 清空原文件，再读写
r+ 原文件存在，再读写
a+ 保留原文件，再读写

def print_two(*args):
    arg1, arg2 = args
    print("arg1:%r ,arg2:%r" % (arg1, arg2))
print_two("zed", "shaw")
#此处*，提醒args

name="Xpo"
DaZhaoHu="Nice to meet you"
print (f"Hi,{name}{DaZhaoHu}")#没有空格
#以 f 开头，包含的{}表达式在程序运行时会被表达式的值代替

注释 # = """  """

模块
    get X form Y
    from X import Y
    1.一个包含函数和变量的Python文件
    2.导入这个文件
    3.用 . 来获取该模块中的函数或者变量
    import mystuff
    mystuff.apple()
class
    class Name(object):
        def __init__(self):
对象
    实例化的class
```
# 2.0 python 学习之路
```x

参数
    默认参数
        默认参数需要指向不变值，常常课将其赋值为Null
        def Name(x,y=Null)
        调用 Name(1)
            Name(1,2)
    可变参数
    *numbers '*'说明该参数是可变的，可以是空，可以是2个，可以是3个。。。
        def calc(*numbers):
            sum=0
            for n in numbers:
                sum+=n*n
            return sum
        num=[1,2,3,4]
        print(calc(*num))
    关键字参数 **k
        区别于可变参数，要求传入0个或者任意个含参数名的参数，即字典
        def person(name,age,**k) #name 与age为必选参数 **k为关键字参数
        def person(Lee,14) 可
        def person(Lee,14,city='BeiJing')可
        def persong(Lee,14,city='',Nation='Han')
    练习 
    def product(s,*num):
    for i in num:
        s=s*i
    return s #将任意输入的数乘起来
```
```x
eg 1.
递归调用，去掉字符串首尾的 空格
    def trim(s):
        if s=='':
            return s
        elif s[0]==' ':
            return trim(s[1:])
        elif s[-1]==' ':
            return tirm(s[:-1])
        else:
            return s
```
```x
索引高级用法
eg 2.
    for i,value in enumerate(['A', 'B', 'C'])
        print(i,value)
        0 A
        1 B
        2 C
```
```x
eg 3.
查找列表中最大、最小元素
    def findMinAndMax(L):
        if len(L) == 0:
            Min = None
            Max = None
        else:
            Max = L[0]
            Min = L[0]
            for i in range(len(L) - 1):
                if Max < L[i + 1]:
                    Max = L[i + 1]
                elif Min > L[i + 1]:
                    Min = L[i + 1]
                else:
                    pass #占位符 pass
        return (Min,Max)
        # 测试
    if findMinAndMax([]) != (None, None):
        print('测试失败!')
    elif findMinAndMax([7]) != (7, 7):
        print('测试失败!')
    elif findMinAndMax([7, 1]) != (1, 7):
        print('测试失败!')
    elif findMinAndMax([7, 1, 3, 9, 5]) != (1, 9):
        print('测试失败!')
    else:
        print('测试成功!')
```
```x
列表生成器
    list generator
        生成[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
        list(range(1,11)) #range(start,end) 始于start，终于end-1

        生成[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
        [x*x for x in range(1,11)] #列表中还可以加 循环

        生成[2, 4, 6, 8, 10, 12, 14, 16, 18]
        [x for x in range(1,20) if x%2==0] #列表中还可以加 判断
```
```x
生成器
    L = [x * x for x in range(10)]
    g = (x * x for x in range(10))
    a, b = b, a + b  # 很厉害的赋值语句
    Iterator 迭代器
        for A in B 
```
```x
函数高级用法
    1.变量可以指向函数
        x=abs
    2.传入函数
        函数A 可接受 函数B 作为参数
        def add(x,y,f):
            return f(x)+f(y)
        f=abs
        add(-100,99,f)
    3.map/reduce
        map (Function, 列表)
                def f(x):
            return x * x
        r = map(f, [1, 2, 3, 4, 5, 6, 7, 8]) #将列表作为参数传入f中
        reduce (f,[1,2,3,4,5,6])
    4.filter 过滤函数
    5.sorted 列表排序
    6.返回函数 闭包
    7.简单函数 用 lambda吧
    8.装饰器 脑壳有点混沌。。
    9.偏函数
    
        




```








