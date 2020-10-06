# Exp02/实验2_Android布局

## 一、实验内容

学习关于ConstraintLayout（约束布局）, LinearLayout（线性布局）和 TableLayout（表格布局）的相关内容

## 二、实验步骤

（一）利用线性布局实现如下界面

![XUX_~__T_5X~KP_CFKK@JBW.png](https://i.loli.net/2020/10/06/w7gl23zB1seHNkY.png)

改界面使用线性布局嵌套，前两行、第三行、第四行，为三个模块竖直排列，每个模块为水平排列，第一个模块的水平排列中又是一个竖直排列（三层嵌套）

LinearLayout标签相当一个容器，存放线性布局中的组件

.xml中的代码如下

```java
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#999"
    android:orientation="vertical">/*竖排版*/

    /*模块一*/
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:orientation="horizontal">
        /*1*/
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="match_parent"
            android:layout_weight="1"
            android:gravity="center"
            android:orientation="vertical">
        <Button
            android:layout_width="160dp"
            android:layout_height="wrap_content"
            android:text="1，1" />
            <Button
                android:layout_width="160dp"
                android:layout_height="wrap_content"
                android:text="2，1" />
        </LinearLayout>
        /*2*/
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="match_parent"
            android:layout_weight="2"
            android:gravity="center"
            android:orientation="vertical">
            <Button
                android:layout_width="220dp"
                android:layout_height="wrap_content"
                android:text="1，2" />
            <Button
                android:layout_width="220dp"
                android:layout_height="wrap_content"
                android:text="2，2" />
        </LinearLayout>
        /*3*/
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="match_parent"
            android:layout_weight="3"
            android:gravity="center"
            android:orientation="vertical">
            <Button
                android:layout_width="160dp"
                android:layout_height="wrap_content"
                android:text="1，3" />
            <Button
                android:layout_width="160dp"
                android:layout_height="wrap_content"
                android:text="2，3" />
        </LinearLayout>
        /*4*/
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="match_parent"
            android:layout_weight="4"
            android:gravity="center"
            android:orientation="vertical">
            <Button
                android:layout_width="150dp"
                android:layout_height="wrap_content"
                android:text="1，4" />
            <Button
                android:layout_width="150dp"
                android:layout_height="wrap_content"
                android:text="2，4" />
        </LinearLayout>

    </LinearLayout>

    /*模块二*/
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:orientation="vertical">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center">

            <Button
                android:layout_width="182dp"
                android:layout_height="wrap_content"
                android:text="3，1" />

            <Button
                android:layout_width="182dp"
                android:layout_height="wrap_content"
                android:text="3，2" />

            <Button
                android:layout_width="182dp"
                android:layout_height="wrap_content"
                android:text="3，3" />

            <Button
                android:layout_width="182dp"
                android:layout_height="wrap_content"
                android:text="3，4" />
        </LinearLayout>

    </LinearLayout>

    /*模块三*/
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:orientation="vertical">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center">

            <Button
                android:layout_width="170dp"
                android:layout_height="wrap_content"
                android:text="4，1" />

            <Button
                android:layout_width="220dp"
                android:layout_height="wrap_content"
                android:text="4，2" />

            <Button
                android:layout_width="170dp"
                android:layout_height="wrap_content"
                android:text="4，3" />

            <Button
                android:layout_width="170dp"
                android:layout_height="wrap_content"
                android:text="4，4" />
        </LinearLayout>

    </LinearLayout>

</LinearLayout>
```



（二）利用ConstraintLayout实现如下界面

 学习文档：https://developer.android.google.cn/training/constraintlayout/index.html

![MI@_UN__FA0@K@3OI_YNICR.png](https://i.loli.net/2020/10/06/NW5tRELC6gBeUz4.png)

直接选择xml文件中的Design模式

![HY2QG__5~_R~_UK@ZQD_GA0.png](https://i.loli.net/2020/10/06/KJ59jqyD7d8VasS.png)

 

直接将左边的组件拖入界面区域

![L@TOD`9_AMS_IS_Y6S59OL5.png](https://i.loli.net/2020/10/06/MLhVmgIyGYT2x78.png)

右边可以调节相应属性

![G__P6D_@UUUBT_C_~DD_@YK.png](https://i.loli.net/2020/10/06/zj9tGrWnb68OYui.png)

直接运行即可出效果，注意您必须为该视图添加至少一个水平约束条件和一个垂直约束条件。



（三）利用表格布局实现如下界面

![_HD__2L_1UC_X_7_V4W1G_L.png](https://i.loli.net/2020/10/06/CHQUMLlxgJrcyKb.png)

表格布局中，一个TableRow标签代表一行，此处每行设置左对齐、右对齐即可

可以用view标签来实现分割线

.xml中的代码如下

```Java
<?xml version="1.0" encoding="utf-8"?>
<TableLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@android:color/darker_gray"
    android:shrinkColumns="3">

    /*1*/
    <TableRow>

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:text="Open..." />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"  />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:layout_gravity="right"
            android:text="Ctrl-O" />


    </TableRow>

    /*2*/
    <TableRow>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:text="Save..." />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"  />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:layout_gravity="right"
            android:text="Ctrl-S" />

    </TableRow>

    /*3*/
    <TableRow>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:text="Save AS..." />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"  />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:layout_gravity="right"
            android:text="Ctrl-Shift-S" />

    </TableRow>

    <View  android:layout_height="1px"
        android:layout_width="match_parent"
        android:background="#333"
        />

    /*4*/
    <TableRow>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:text="X Impor..." />
    </TableRow>

    /*5*/
    <TableRow>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:text="X Export..." />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"  />
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:layout_gravity="right"
            android:text="Ctrl-E" />

    </TableRow>

    <View  android:layout_height="1px"
        android:layout_width="match_parent"
        android:background="#333"
        />

    /*6*/
    <TableRow>
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dip"
            android:text="Qiut" />
    </TableRow>


</TableLayout>
```



PS：2020 年 10 月 1 日开始，GitHub 上的所有新库都将用中性词「main」命名，取代原来的「master」，上传时需注意



补充：Android Activity 生命周期，学习链接

https://blog.csdn.net/TTAndroid/article/details/80926753?utm_source=app

https://blog.csdn.net/liyuanjinglyj/article/details/47055407?utm_source=app
