## line {#cmd:line}

### 概要

控制绘图中的线型

### 语法

LINE \[ON|OFF|S`OLID`|D`OTTED`|n\] \[FILL ON|OFF|pos\_color/neg\_color\]
\[I`NCREMENT` \[ON|OFF\]\] \[L`IST` STANDARD|nlist\]

### 输入

ON

:   打开线型选项，不改变线型

OFF

:   关闭线型选项

SOLID

:   改变线型为实线型，并打开线型开关

DOTTED

:   改变线型为虚线型，并打开线型开关

n

:   设置线型为n并绘制线条。若n取值为0则表示不绘制该线条

FILL ON|OFF

:   打开/关闭颜色填充

FILL pos\_color/neg\_color

:   对每个数据的正值和负值部分涂色

INCREMENT ON

:   每个数据被绘出之后，按照线型表中的次序改变为另一个线型

INCREMENT OFF

:   不改变线型

LIST nlist

:   改变线型列表

LIST STANDARD

:   设置为标准线型列表

### 缺省值

line solid increment off list standard

### 说明

这个命令控制绘图时的线型，图形的框架（轴、标题等等）通常使用实线。网格的
线型用 [grid](/commands/grid.md)
命令控制。并非所有的图形设备都有除实线型之外的
其他线型的，在那些设备上显然这个命令没有什么效果。而对于不同的设备线型号
n也可能是不同的。

还有其他命令可以控制数据显示的其他方面。[symbol](/commands/symbol.md)
命令用于将
每个数据点的值用一个符号显示在图上。[color](/commands/color.md)
命令控制彩色图形
设备的颜色选择。所有的这些属性都是独立的。如果你想的话你可以选择在每个数
据点上选择带符号的蓝色虚线。线型为0代表关闭画线选项。在 `LIST` 选项和
[symbol](/commands/symbol.md)
命令中可以利用线型为0的特性，在同一张图上将
某些数据用线显示某些数据用符号显示。

### 示例

选择依次变化的线型，从线型1开始：

``` {.bash}
SAC> line 1 increment
```

改变线型表使之包含线型3、5和1：

``` {.bash}
SAC> line list 3 5 1
```

使用 [plot2](/commands/plot2.md)
在同一个图形上绘制三个文件，第一个使用实线无符号，
第二个没有线条，用三角符号，第三个无线条，用十字符号：

``` {.bash}
SAC> read file1 file2 file3
SAC> line list 1 0 0 increment
SAC> symbol list 0 3 7 increment
SAC> plot2
```

将地震图的正值部分涂上红色，负值部分涂上蓝色，如果线型为0，则涂色区域用
黑色描边：

``` {.bash}
SAC> fg seis
SAC> line 0 fill red/blue
SAC> p
```