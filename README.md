### 1.文件说明

<kbd>trainData.csv</kbd>中数据用于训练与验证

<kbd>testData.csv</kbd>中数据用于测试

### 2.列说明

timestamp:时间戳
tSide_copTem01:温度测点
eSide_copTem01:温度测点
tSide_outWin01:温度测点
tSide_outWin02:温度测点
eSide_outWin01:温度测点
eSide_outWin02:温度测点
AB_Vol:电压测点
BC_Vol:电压测点
AC_Vol:电压测点
pwrNeg:功率测点
freq:频率测点
hydPres:压力测点
pwrPos01:功率测点
pwrPos02:功率测点
pwrPos03:功率测点

### 3.建模目标

针对温度型测点<kbd>tSide_copTem01</kbd>、<kbd>eSide_copTem01</kbd>，建立运行值预测模型，要求至少能够实现+1期的准确预测，并据此建立上述两测点运行值超限判断的依据与模型。

### 4.先验知识

 - "tSide_"类测点从物理上相关

 - "eSide_"类测点从物理上相关

 - "tSide_"类与"eSide_"类测点从物理上不应相关

 - 考察<kbd>tSide_copTem01</kbd>、<kbd>eSide_copTem01</kbd>测点温度时,可以变相考察其温升:
   $$
   tSideCopTem01_{温升}=tSideCopTem01 - tSideOutWin01
   $$
   或
   $$
   tSideCopTem01_{温升}=tSideCopTem01 - \frac{(tSideOutWin01 + tSideOutWin02)}{2}
   $$
   

- 注意<kbd>testData.csv</kbd>中,freq列的数据应当X1000倍

