# 截图

![img1](https://github.com/brightlicong/UR5-Writing-Control/blob/master/img/img1.png)

![img2](https://github.com/brightlicong/UR5-Writing-Control/blob/master/img/img2.png)

![img3](https://github.com/brightlicong/UR5-Writing-Control/blob/master/img/img3.png)

# 使用方法

1. 将含有笔画信息的文件放在`dots-information`文件夹中，其满足以下要求：
   1. 一幅图放进一个文件夹中。`0.txt`写明图像的长与宽和笔画的总数量。
   2. 其余的`txt`以一个笔画为单位存放关键点的二维坐标信息。
   3. 一行只写一个点的横坐标与纵坐标，两者之间用`space`相隔。
2. 将部分函数的参数调整至满意后运行`main.m`。
3. 生成的move.txt文件中包含了两个ur5机器人的关节角信息。

# 函数及其参数说明

## `creat_ur5`

创建一个UR5机器人，可以设置机器人的名字`rn`与基坐标系`bp`。

## `ur5_ikine`

UR5机器人的逆解函数，输入由`ctraj`函数得到一系列末端位姿，返回相对应的一组关节角。

## `cordinate2T`

将点[x y]转化为末端位姿。可以通过`zoom_x`和`zoom_z`来进行横向和纵向的伸缩。也可以按照需求更改矩阵的数据。

## `writeQlits`

将最后计算得到的系列关节角写入到txt文件中以便以后使用。

## `main`

主程序。

可以设置笔的长度`pen_length`，每次抬笔的距离`lift_dis`。

设置`original_display_mode = 1;`显示预期的书写效果。

设置`path_disply_mode = 1;`显示实际通过计算得到的UR5末端移动轨迹。

在最后使用函数`test_plot()`可以用动画的形式演示机器人写字的全过程。

