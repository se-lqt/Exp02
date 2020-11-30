# Exp02/实验2_Android布局

## 一、实验内容

学习关于ConstraintLayout（约束布局）, LinearLayout（线性布局）和 TableLayout（表格布局）的相关内容

## 二、实验步骤

（一）利用线性布局实现如下界面

![XUX_~__T_5X~KP_CFKK@JBW.png](https://i.loli.net/2020/10/06/w7gl23zB1seHNkY.png)

改界面使用线性布局嵌套，前两行、第三行、第四行，为三个模块竖直排列，每个模块为水平排列，第一个模块的水平排列中又是一个竖直排列（三层嵌套）

**相关知识点：**

（1）LinearLayout是一个视图组，用于使所有子视图在单个方向（垂直或水平）保持对齐。您可使用 android:orientation属性指定布局方向。

（2）这里需要注意的是LinearLayout中子控件或子布局的属性设置，如果LinearLayout的排列方向是horizontal,内部的控件就绝对不能将宽度指定为match_parent。如果LinearLayout的排列方向是vertical，内部的控件就不能将高度指定为match_parent。

（3）android:layout_weight: 此属性根据视图应在屏幕上占据的控件量向视图分配“重要性的值”，值越大，所占的屏幕空间越大。可以指定权重，对应屏幕占比。

<LinearLayout></LinearLayout>标签相当一个容器，存放线性布局中的组件

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

**相关知识点：**

（1）[`ConstraintLayout`](https://developer.android.google.cn/reference/androidx/constraintlayout/widget/ConstraintLayout) 可让您使用扁平视图层次结构（无嵌套视图组）创建复杂的大型布局。它与 [`RelativeLayout`](https://developer.android.google.cn/reference/android/widget/RelativeLayout) 相似，其中所有的视图均根据同级视图与父布局之间的关系进行布局，但其灵活性要高于 `RelativeLayout`，并且更易于与 Android Studio 的布局编辑器配合使用。

（2）`ConstraintLayout` 的所有功能均可直接通过布局编辑器的可视化工具来使用，因为布局 API 和布局编辑器是专为彼此构建的。 因此，您完全可以使用 `ConstraintLayout` 通过拖放的形式（而非修改 XML）来构建布局。

直接选择xml文件中的Design模式

![HY2QG__5~_R~_UK@ZQD_GA0.png](https://i.loli.net/2020/10/06/KJ59jqyD7d8VasS.png)

 

直接将左边的组件拖入界面区域

![L@TOD`9_AMS_IS_Y6S59OL5.png](https://i.loli.net/2020/10/06/MLhVmgIyGYT2x78.png)

右边可以调节相应属性

![G__P6D_@UUUBT_C_~DD_@YK.png](https://i.loli.net/2020/10/06/zj9tGrWnb68OYui.png)

直接运行即可出效果，注意您必须为该视图添加至少一个水平约束条件和一个垂直约束条件。



（三）利用表格布局实现如下界面

![_HD__2L_1UC_X_7_V4W1G_L.png](https://i.loli.net/2020/10/06/CHQUMLlxgJrcyKb.png)

表格布局中，一个<TableRow>标签代表一行，此处每行设置左对齐、右对齐即可

可以用<view>标签来实现分割线

**相关知识点：**

（1）TableLayout以行和列的形式对控件进行管理，每一行为一个TableRow对象，每加入一个TableRow就表示添加一行，然后在TableRow中每添加一个控件，就表示在该行中加入了一列，TableRow中的控件是不能指定宽度的。除了添加TableRow，也可以直接添加View控件,一个View控件占一行。



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



**补充：**

**约束布局相关知识点：**

（1）`RelativeLayout` 是一个以相对位置显示子视图的视图组。每个视图的位置可以指定为相对于同级元素的位置（例如，在另一个视图的左侧或下方）或相对于父级 `RelativeLayout` 区域的位置（例如在底部、左侧或中心对齐）。

（2）`RelativeLayout` 可以指定子视图相对于父视图或彼此（由 ID 确定）的位置。因此，您可以按照右边框对齐两个元素，或者使它们一上一下，屏幕居中，左侧居中，等等。默认情况下，所有子视图均绘制在布局的左上角，因此您必须使用 `RelativeLayout.LayoutParams` 中提供的各种布局属性定义每个视图的位置。（可以解决线性布局层层嵌套的问题）

**常用的属性有：**

```
android:layout_above="@id/xxx"  --将控件置于给定ID控件之上

android:layout_below="@id/xxx"  --将控件置于给定ID控件之下

android:layout_toLeftOf="@id/xxx"  --将控件的右边缘和给定ID控件的左边缘对齐

android:layout_toRightOf="@id/xxx"  --将控件的左边缘和给定ID控件的右边缘对齐

android:layout_alignLeft="@id/xxx"  --将控件的左边缘和给定ID控件的左边缘对齐

android:layout_alignTop="@id/xxx"  --将控件的上边缘和给定ID控件的上边缘对齐

android:layout_alignRight="@id/xxx"  --将控件的右边缘和给定ID控件的右边缘对齐

android:layout_alignBottom="@id/xxx"  --将控件的底边缘和给定ID控件的底边缘对齐

android:layout_alignParentLeft="true"  --将控件的左边缘和父控件的左边缘对齐

android:layout_alignParentTop="true"  --将控件的上边缘和父控件的上边缘对齐

android:layout_alignParentRight="true"  --将控件的右边缘和父控件的右边缘对齐

android:layout_alignParentBottom="true" --将控件的底边缘和父控件的底边缘对齐

android:layout_centerInParent="true"  --将控件置于父控件的中心位置

android:layout_centerHorizontal="true"  --将控件置于水平方向的中心位置

android:layout_centerVertical="true"  --将控件置于垂直方向的中心位置

```



（2）Android Activity 生命周期，学习链接

https://blog.csdn.net/TTAndroid/article/details/80926753?utm_source=app

https://blog.csdn.net/liyuanjinglyj/article/details/47055407?utm_source=app

