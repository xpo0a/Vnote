# 0.文件执行几个过程
    -E 预处理：将.c .h展开成一个文件
        gcc -E hello.c -o hello.i
    -S 汇编： .i 生成一个汇编代码文件 .S
        gcc -S hello.i -o hello.S
    -c 编译： .S生成一个 .o .obj
        gcc -c hello.S -o hello.o
    -o 链接： .o链接 .exe windows .elf
        gcc hello.o -o hello

# 1.第一层 文件的编译、链接过程
    目标文件：依赖文件
        指令
    eg.从下到上
    test:main.o
        gcc main.o -o test
    main.o: main.c
        gcc main.c -o main.c

    伪命令：
        .PHONY:
        目标：
            命令 #类似宏定义，目标==执行命令
        eg.
        .PHONY:
        clearall:
            rm -rf hello.o hello.S
        clear:
            rm -rf hello.o
# 2.第二层 变量
    变量    =（替换）    +=（追加）    ：=（恒等于，常量）
    使用变量 $(变量名)
    eg.
    TAR=test
    OBJ=main.o cube.o circle.o
    CC:=gcc
    
    $(TAR):$(OBJ)
        $(CC) $(OBJ) -o $(TAR)
# 3.第三层 隐含规则 %.c %.o任意的.c .o文件 *.c *.o 所有的.c .o文件
    eg:
    %.o :%.c   #将所有的.c 生成.o文件
        $（CC) -c %.c -o %.o
# 4.通配符
    $^所有目标文件 $@所有的依赖文件 $<所有的依赖文件的第一个文件
# 5.函数

