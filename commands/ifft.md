## ifft {#cmd:ifft}

### 概要

对数据进行离散反傅立叶变换

### 语法

IFFT

### 说明

数据文件必须是之前利用 [fft](/commands/fft.md)
命令生成的谱文件，可以是 实部-虚部格式或振幅-相位格式。

该命令会从 `sb`、`sdelta`、`nsnpts` 中读取原始
数据在时间域的起始时间、采样周期和数据点数。频率域的起始频率、采样频率、
采样点数将被保存到 `sb`、`sdelta`、`nsnpts` 中。

### 头段变量

b、delta、npts、sb、sdelta、nsnpts

### 限制

目前 `ifft` 所允许的最大数据点数为65536。