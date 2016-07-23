## distancewindow {#sss:distancewindow}

### 概要

控制接下来的剖面图的距离窗属性

### 语法

D`ISTANCE`W`INDOW` \[U`SEDATE`|W`IDTH`i v|F`IXED` v1 v2\] \[UN`ITS`
K`ILOMETERS`|D`EGREES`\]

### 输入

USEDATA

:   使用迭加文件列表中文件的距离属性的最大最小值

WIDTH v

:   使用迭加文件列表中文件的距离属性的最小值，但强制其宽度为v，即最大值为最小值加上v

FIXED v1 v2

:   固定距离的最小、最大值分别为v1和v2

UNITS KILOMETERS

:   设置距离窗的单位为 [^1]

UNITS DEGREES

:   设置距离窗的单位为度

### 缺省值

distancewindow usedata units kilometers

[^1]: 该选项尚未实现