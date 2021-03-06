﻿ ![](http://i.imgur.com/hozR5pB.jpg)


## JavaScript基础

##### JavaScript中的算术运算和数据库函数
- （+） 加
- （-） 减
- （*） 乘
- （/） 除
- （%） 取余

JavaScript同时拥有一个数学库，用来完成一些高级运算，比如平方根，绝对值和三角函数。算数运算符合标准的运算顺序，可以用括号来改变运算顺序。

##### 判断结构
有if语句和switch语句
if语句有三种形式：
1. 简单的if语句
2. if-else语句
3. if-else-if语句

##### 循环结构
while循环和for循环，和其他语言类似。

##### 函数
JavaScript定义了两种函数，一种有返回值的，一种没有返回值的（这种函数叫做void函数）。

##### 变量作用域
变量的作用域是指一个变量在程序中的哪些地方可以访问。JavaScript中的变量作用域被定义为函数作用域，这是指变量的值在定义该变量的函数内是可见的，并且定义在函数内的嵌套函数中也可以访问。


在主程序中，如果在函数外定义一个变量，那么该变量拥有全局作用域，这是指可以在包括函数体内的程序的任何部分访问该变量。

下面是全局和局部的区别

![](http://i.imgur.com/yZnnnBf.png)


![](http://i.imgur.com/Vi77NQO.png)


这些都是符合一切的标准的，但是如果在定义的时候省略了var，那就变了。JavaScript允许在定义的时候不使用关键字var，但是这样定义的变量就变成了全局变量，拥有全局作用域。

![](http://i.imgur.com/03LDXTg.png)

JavaScript中没有块级作用域。

##### 递归
JavaScript有能力处理递归层次比较深的递归调用，但是有的时候会超出JavaScript的处理能力。

## 数组
##### JavaScript中对数组的定义
数组的标准定义是:一个存储元素的线形集合，元素可以通过索引来任意的存取，索引通常是数字，用来计算元素之间的存储位置的偏移量。


JavaScript中的数组是一种特殊的对象，用来表示偏移量的索引是该对象的属性，索引可能是整数，严格来说，应该称为对象。
##### 创建数组
最简单的方式:
var numbers = [];
var numbers = [1,2,3,4,5];
还可以调用Array的构造函数创建数组：
var numbers = new Array();
##### 读写数组
可以用for循环遍历数组
##### 由字符串生成数组
调用字符串对象的split(）方法可以生成数组，该方法通过一些常见的分隔符。
![](http://i.imgur.com/LDWvokM.png)
##### 对数组的整体性操作
深拷贝  浅拷贝
##### 查找元素
indexOf()函数是最常用的存取函数之一，用来查找传进来的参数在目标数组中是否存在。如果目标数组包含该参数，就返回该元素在数组中的索引，如果没有，就返回-1.


另一个相反的是，但功能相似的是：lastIndexOf（），该函数返回相同元素中的最后一个元素的索引，如果没有，就返回-1.

![](http://i.imgur.com/G2QGT9s.png)

##### 数组的字符串表示

将数组转换字符串：join()和toString()。这两个方法都返回一个包含数组所有元素的字符串，各元素之间用逗号分隔开。
![](http://i.imgur.com/GOMtXMK.png)
##### 有已经有的数组创建数组
concat()和splice()方法允许通过已有的数组创建新数组。concat方法可以合并度个数组创建一个数组，splice()方法截取一个数组的子集创建一个新数组。


conact()方法的发起者是一个数组，参数是另一个数组，作为参数的数组，所有的元素被连接到调用concat()方法的数组后面。


splice()从现有的数组中截取一个新数组，该方法的第一个参数是截取的起始索引，第二个参数是截取的长度。
![](http://i.imgur.com/4meIm6c.png)
##### 为数组添加元素
两个方法添加数组：push()和unshift()。

![](http://i.imgur.com/gre0UxM.png)
##### 从数组中删除元素
使用pop()方法可以删除数组末尾的元素，shift()可以删除数组的第一个元素。
![](http://i.imgur.com/il1Wa34.png)
##### 从数组中间位置添加和删除元素
删除数组中的第一个元素在数组开头添加一个元素存在同样的问题---两种操作都需要将数组中的剩余元素向前或者前后移动，然而splice()可以解决。


splice()参数如下：

- 起始索引（也就是希望添加元素的地方）
- 需要删除的元素的个数（添加元素是该参数设为0）
- 想要添加进数组的元素

![](http://i.imgur.com/A2DK6p7.png)
##### 数组排序
reverse(),该方法将数组中的元素的顺序进行反转。
![](http://i.imgur.com/2wItazn.png)

sort(),该方法针对元素是字符串类型就好使，如果是数字类型，就不行，因为这个方法是按照字典顺序进行排序的，就得传入一个大小比较函数。


![](http://i.imgur.com/FnA3RCC.png)
##### 不生成新数组的迭代器方法
这些迭代器方法对数组中的每一个元素应用一个函数，可以返回一个值，一组值或者一个新数组。


第一个方法forEach()，该方法接受一个函数作为参数，对数组中的每个元素使用该函数。
![](http://i.imgur.com/bPaCgOQ.png)


第二个迭代器方法是every(),该方法接受一个返回值为布尔类型的函数，对数组中的每个元素使用该函数，如果对于所有的元素，该函数均返回true，则该方法返回true。
![](http://i.imgur.com/MIFMrTE.png)


第三个方法是some(),该方法接受一个返回值为布尔型的函数，只要一个元素使得该函数返回true，该方法就返回true。
![](http://i.imgur.com/J5zREkH.png)


第四个方法是reduce()方法接受一个函数，返回一个值，该方法会从一个累加值开始，不断对累加值和数组中的后续元素调用该函数，直到数组中的最后一个元素，最后返回得到的累加值。
![](http://i.imgur.com/7fh6H02.png)

##### 生成新数组的迭代器方法
两个迭代器方法可以生成新数组：map()和filter()。
map()和forEach()有点像，对数组中的每个元素使用某个函数。两者的区别是map()返回一个新手，该数组的元素是对所有原有元素应用某个函数得到的结果。

![](http://i.imgur.com/YJIxLN1.png)

filter()和every()类似，传入一个返回值为布尔类型的函数。和every()方法不同的是，当数组中的所有元素应用该函数，结果均为true时，该方法并不返回true，而是返回一个新数组，该数组包含应用函数后结果为true的元素。
![](http://i.imgur.com/aYgWAVc.png)

还可以使用filter()方法过滤掉字符串数组。


## 二维数组和多维数组

##### 处理二维数组，通过嵌套for循环。
求一个grades数组的平均成绩
![](http://i.imgur.com/4DASZpb.png)

##### 对象中的数组

在一个对象内部使用数组保存数据。
在例子中，创建一个对象，用于保存观测到的周最高气温。该对象有两个方法，一个方法用来增加一条新的气温记录，另外一个方法用来计算存储在对象中的平均气温。
![](http://i.imgur.com/DqsdbGj.png)

## 列表
列表是一组有序的数据，每个列表中的数据项称为元素，列表拥有那些属性，应该执行什么操作。

#### 列表的抽象数据类型定义：
![](http://i.imgur.com/T4MKTyk.png)
##### append:给列表添加元素
![](http://i.imgur.com/N4VrElK.png)
##### remove:从列表中删除元素
splice()方法可以简化这一过程，首先从find()开始。
![](http://i.imgur.com/XOlLtD8.png)
##### find:在列表中查找某一元素
find()方法通过对数组对象dataStore进行迭代，查找给定的元素，如果找到的话，就返回该元素在列表中的位置，否则返回-1。
![](http://i.imgur.com/72B9x0n.png)
##### length:列表中有多少个元素
![](http://i.imgur.com/E6BKegB.png)
##### toString:显示列表中的元素
![](http://i.imgur.com/NYg1NgD.png)
##### insert:向列表中插入一个元素
![](http://i.imgur.com/tuwp279.png)
##### clear:清空列表中所有元素
![](http://i.imgur.com/eMVITjL.png)
##### contains:判断给定值是否在列表中
![](http://i.imgur.com/MBxKUsJ.png)
## 栈
栈是一种特殊的列表，后入先出的数据结构。


对栈的操作：
- 入栈使用push()
- 出栈使用pop()，调用该方法后，栈顶元素永久的被删除了
- peek()返回栈顶元素，但是不删除它,如果是空栈，再返回就是undefined。


定义一个Stack类的构造函数

![](http://i.imgur.com/XJohLIL.png)
##### push()
![](http://i.imgur.com/5XvIsUX.png)
##### pop()
![](http://i.imgur.com/vPRtlUc.png)
##### peek()
![](http://i.imgur.com/3YkHJb8.png)

## 使用Stack类
### 数制间的相互转换
##### 将数字转换为二进制和八进制

![](http://i.imgur.com/LMbyma7.png)
### 回文
![](http://i.imgur.com/lLrkKbl.png)
### 递归演示
##### 使用递归模拟过程
![](http://i.imgur.com/irXqPmB.png)

## 队列
队列是一种列表，不同的是队列只能在队尾插入元素，在队首删除元素。


定义一个队列的构造函数

![](http://i.imgur.com/1KMwwQ3.png)
##### enqueue()
![](http://i.imgur.com/P52cUZa.png)
##### dequeue()
![](http://i.imgur.com/P4qZyMT.png)
##### front()
![](http://i.imgur.com/Z1dDxC0.png)
##### back()
![](http://i.imgur.com/croWK8W.png)
##### toString()
![](http://i.imgur.com/pO5lVxC.png)
##### empty()
![](http://i.imgur.com/wqcgWZn.png)

## 排序算法

### 冒泡排序

冒泡排序算法的流程如下：

- 比较相邻的元素。如果第一个比第二个大，就交换他们两个。
- 对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。在这一点，最后的元素应该会是最大的数。
- 针对所有的元素重复以上的步骤，除了最后一个。
- 持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。

![](http://i.imgur.com/ECmEp7j.gif)

    function maopao(arr){
        var len = arr.length;
 		for(var i=0;i<len;i++){
			for(var j=0;j<len-1-i;j++){
				if(arr[j]>arr[j+1]){
					var t = arr[j+1];
					arr[j+1] = arr[j];
					arr[j] = t;
				}
			}
		}
		return arr;
    }


### 插入排序

插入排序算法的流程如下：

- 从第一个元素开始，该元素可以认为已经被排序
- 取出下一个元素，在已经排序的元素序列中向后扫描
- 如果该元素（已排序）大于新元素，将该元素移动到下一个位置
- 重复步骤3，直到找到已排序的元素小于或者等于新元素的位置
- 将新元素插入到该位置后
- 重复步骤2~5

其实，有点类似打扑克。

![](http://i.imgur.com/TVwdCNK.gif)

    function charu(arr){
       var len = arr.length;
       var pre,current;
       for(var i=1;i<len;i++){
          pre = i-1;
          current = a[i];
          while(pre>=0 && arr[pre]>current){
             arr[pre+1] = arr[pre];
             pre--;
		  }
          arr[pre+1] = current;
	   }
	   return arr;
    }


### 选择排序

选择排序算法流程：

从数组的开头开始，将第一个元素和其他的元素进行比较，检查完所有元素后，最小的元素会被放到数组的第一个位置，然后算法会从第二个位置继续，这个过程一直进行，当进行到数组的倒数第二个位置时，即可完成。

![](http://i.imgur.com/Qp8zF5l.gif)

    function xuanze(arr){
       var len = arr.length;
       var mminIndex,t;
       for(var i=0;i<len-1;i++){
          minIndex = i;
          for(var j=i+1;j<len;j++){
             if(arr[j]<arr[minIndex]){
				minIndex = j;
             }
          }
          t = arr[i];
          arr[i] = arr[minIndex];
          arr[minIndex] = t;
       }
       return arr;
    }


### 快速排序

快速排序的流程：

- 从数列中挑出一个元素，成为基准。
- 重新排列数列，所有比基准值小的元素摆放在基准前面，所有比基准值大的元素摆在基准后面（相同的数可以到任一边）。在这个分区结束后，该基准处于数列的中间位置。这个称为分区操作。
- 递归地把小于基准值元素的子数列和大于基准值元素的子数列排序。
递归到最底部时，数列的大小是零或一，也就是已经排序好了。这个算法一定会结束，因为在每次的迭代中，它至少会把一个元素摆到它最后的位置去。

![](http://i.imgur.com/9sPh5yT.gif)

    function quickly(arr,left,right){
        var len = arr.length;
        partitionIndex;
        left = typeof left != 'number' ? 0 : left;
        right = typeof right != 'number' ? len-1 : right;
        if(left < right){
            partitionIndex = partition(arr,left,right);
            quickly(arr,left,partitionIndex-1);
            quickly(arr,partitionIndex+1,right);
        }
        return arr;
    }
    //分区操作
    function partition(arr,left,right){
        var pivot = left;              //设定基准值(pivot)
        index = pivot + 1;
        for(var i = index;i<=right;i++){
           if(arr[i]<arr[pivot]){
              swap(arr,i,index);
              index++;
           }
        }
        swap(arr,pivot,index-1);
        return index-1;
    }
    function swap(arr,i,j){
        var temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }