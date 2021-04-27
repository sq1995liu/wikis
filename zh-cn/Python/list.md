## 数据类型

数字（Numbers）

字符串（String）

列表（List）

元组（Tuple）

字典（Dictionary）

集合（Set）

不可变集合（frozenset）：集合是无序，可变的。而不可变集合却不可变，这意味着我们无法改变它的值，从而也使其无法作为字典的键值。



## 列表(List)常用方法


## 1.1 append

```
#1. append用于在列表末尾追加新的对象
a = [1,2,3]
a.append(4)                          #the result ： [1, 2, 3, 4]
```

## 1.2 count

```
#2. count方法统计某个元素在列表中出现的次数
a = ['aa','bb','cc','aa','aa']
print(a.count('aa'))                 #the result ： 3
```
## 1.3 extend

```
#3. extend方法可以在列表的末尾一次性追加另一个序列中的多个值
a = [1,2,3]
b = [4,5,6]
a.extend(b)                          #the result ：[1, 2, 3, 4, 5, 6]

```

## 1.4 index

```
#4. index函数用于从列表中找出某个值第一个匹配项的索引位置
a = [1,2,3,1]
print(a.index(1))                   #the result ： 0
```
## 1.4 index

```
#4. index函数用于从列表中找出某个值第一个匹配项的索引位置
a = [1,2,3,1]
print(a.index(1))                   #the result ： 0
```
## 1.5 insert

```
#5. insert方法用于将对象插入到列表中
a = [1,2,3]
a.insert(0,'aa')            #the result : ['aa', 1, 2, 3]
```

## 1.6 pop

```
#6. pop方法会移除列表中的一个元素（默认是最后一个），并且返回该元素的值
a = [1,2,3]
a.pop()                             #the result ： [1, 2]
a.pop(0)
```

## 1.7 remove

```
#7. remove方法用于移除列表中某个值的第一个匹配项
a = ['aa','bb','cc','aa']
a.remove('aa')                      #the result ： ['bb', 'cc', 'aa']
```
## 1.8 reverse

```
#8. reverse方法将列表中的元素反向存放
a = ['a','b','c']
a.reverse()                         #the result ： ['c', 'b', 'a']
```

## 1.9 sort

```
#9. sort方法用于在原位置对列表进行排序，意味着改变原来的列表，让其中的元素按一定顺序排列
a = ['a','b','c',1,2,3]
a.sort()                           #the result ：[1, 2, 3, 'a', 'b', 'c']
```
## 1.10 enumerate

```
li = [11,22,33,44,55,66]
for k,v in enumerate(li, 1):  # 1.代表 k 从哪个数字开始
    print(k,v)
'''
1 11
2 22
3 33
'''
```

## 1.11 range和xrange

- 指定范围，生成指定的数字
- 注：python3中的range类似python2中的xrange，比如a = range(1,4) : a返回的不是列表对象而是一个可迭代对象（<class 'range'>）
```
#1、range根据start与stop指定的范围以及step设定的步长，生成一个序列：range([start,] stop[, step])
#2、xrange 用法与 range 完全相同，所不同的是生成的不是一个list对象，而是一个生成器
for i in range(1,10,2):
    print(i)
```
## 1.12 列表去空

```
# 法1：
filter(None, your_list)

# 法2：
while '' in your_list:
    your_list.remove('')

# 法3：
your_list = [x for x in your_list if x != '']
```

## 02.元祖

- **元组定义：**元组和列表一样，也是一种序列，唯一的不同是元组不能修改。

### 2.1 创建元组

```python
#1. 创建元组
a = (1,2,3,4,5,6)
#2. 将列表转换成元组
tuple([1,2,3,4])                                    #the result ： (1, 2, 3, 4)
```

- 元祖常用方法

```python
t=(1,2,3,1)
print( t.count(1) )   # 2 : 元祖中出现 1 的次数为2次
print( t.index( 3 ) )  # 2 : 元祖中出现三的索引位置为 2
```

### 2.2 列表和元组常用函数

| 方法          | 作用                                 |
| ------------- | ------------------------------------ |
| com(x,y)      | 比较两个值                           |
| len(seq)      | 返回序列的长度                       |
| list(seq)     | 把序列转换成列表                     |
| max(args)     | 返回序列或者参数集合中得最大值       |
| min(args)     | 返回序列或者参数集合中的最小值       |
| reversed(seq) | 对序列进行反向迭代                   |
| sorted(seq)   | 返回已经排列的包含seq 所有元素的列表 |
| tuple(seq)    | 把序列转换成元组                     |

## 03.列表和元祖区别

### 3.1 列表和元祖区别

- `可变不可变：`   列表可变，元组不可变，除非整体替换

- `存储差异：`    对列表和元组，我们放置了相同的元素，但是元组的存储空间，却比列表要少16字节
  - 列表为了减小每次增加/删减操作时空间分配的开销，Python每次分配空间时都会额外多分配一些

- 元组比列表的访问和处理速度快。

- 列表不能作为字典的键，而元组可以

### 3.2 举例

- `元祖内存长度大小固定，所以无法进行切片`

```python
>>> t = (1,2,3)
>>> t[0] = 100  # 元祖中无法进行切片，因为元祖中长度是固定的
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

- 存储差异：`放置了相同的元素，但是元组的存储空间，却比列表要少16字节`

```python
>>> l = [1, 2, 3]
>>> l.__sizeof__()
64
>>> tup = (1, 2, 3)
>>> tup.__sizeof__()
48
```

### 3.3 使用场景

- 需要返回的是一个`地点的经纬度`，然后直接传给前端渲染，那么肯定选用元组更合适。

- 式化字符串，格式化字符串后面的（）本质上就是一个元祖

- ```python
     print("%s 年龄是 %d 身高是 %。2f" %("小明",18,1.75))
  ```



## 字符串(String)常用方法






**查找**

find(value)：在字符串中查找子串，如果不存在，返回-1

index(value)：同上，如果不存在会抛出ValueError异常

count(value)：统计字符出现次数

**操作**

replace(oldvalue, newvalue, count)：替换，第一个参数代表原来字符，第二个参数代表新字符  第三个参数 代表替换个数

split(value)：将字符串进行分割，分割的结果会变为一个列表

join()：按照指定字符拼接字符串

**判断**

startswith(value)：  判断字符串以什么开头  返回结果是 True 或  False

endwith(value)：  以什么结尾   跟startswith对应

isalpha()：检测所有字符是否为字母

isdigit()：检测是否都为数字

isalnum()： 检测所有字符都是字母或数字返回 True,否则返回False

**大小写转换**

upper()  转换为大写

lower()  转换为小写

title()  每个单词的首字母变大写

**去空白字符**

lstrip() 删除左边的空白字符

rstrip() 删除字符串末尾的空白字符

strip() 删除字符串两端的空白字符

**ASCII转换**

ASCII转换字符：chr()

字符转换ASCII：ord()

## dict

clear()：清空字典的所有项

get(key, value(若key不存在可以指定返回的value))：通过key获取对应的value，如果不存在返回None，也可以指定返回的value

fromkeys()：使用给定的key建立一个新的字典，每个key都对应一个默认value：None

keys()：获取字典中所有的key

value()：获取字典中所有的value

items()：每个键值以元组的方式存入列表，返回结果

pop(key)：通过传入的key删除对应的键值对，并且将这个键值对返回

update()：用法：a.update(b)，a和b都是字典，利用一个字典更新另一个字典，如果有相同的key则会被覆盖

zip()：可以将两个列表组合成字典

## set

add()

clear()

pop()

remove()

交集：set1.intersection(set2)：在set1和set2中都有的元素

并集：set1.union(set2)，获取两个集合中的全部元素，重复元素只获取一个

差集：set1.difference(set2)，在set1中有，set2中没有

## tuple

count()

index()

## list和tuple区别

相同点：都是按顺序保存元素，都可以用索引来访问元素

最本质的区别，list是可变，tuple是不可变的

元组用于存储异构数据，也就是具有不同意义的数据，例如记录一个人的身高，体重，年龄。列表一般用来存储同构数据，就是具有相同意义的数据

由于元组支持的操作比列表小，所以性能会更好一点

## list和dict区别：

1. list是有序的，dict是无序的
2. list通过索引访问，dict使用key访问
4. dict的占用内存稍比list大，会在1.5倍左右
4. 列表是序列，可以理解为数据结构中的数组，字典可以理解为数据结构中的hashmap

## python2和python3区别

print语句变为了函数

python2的默认编码是ascii，需要更改字符集才能正常支持中文，所以在.py文件中会看到#-- coding: UTF-8 --

除法运算：python2是整数，python3结果是浮点

不等运算符：去掉了<>

去掉了long类型

## 可变、不可变

可变类型：list、dict、set

不可变类型：数字、string、tuple

可变和不可变是指内存中的value是否可以被改变，操作不可变对象时，会申请一块新空间用来存储。而可变类型在改变时内存地址保持不变，区域会变长或者变短。

## 深浅拷贝

- **浅copy与deepcopy（What）**
    
    - **浅copy：** 不管多么复杂的数据结构，浅拷贝都只会copy一层

    - **深deepcopy:** 深拷贝会完全复制原变量相关的所有数据，在内存中生成一套完全一样的内容，我们对这两个变量中任意一个修改都不会影响其他变量

    ```python
    import copy
    sourceList = [1,2,3,[4,5,6]]
    copyList = copy.copy(sourceList)
    deepcopyList = copy.deepcopy(sourceList)

    sourceList[3][0]=100

    print(sourceList)           # [1, 2, 3, [100, 5, 6]]
    print(copyList)             # [1, 2, 3, [100, 5, 6]]
    print(deepcopyList)         # [1, 2, 3, [4, 5, 6]]

    ```

    ![](/docs/style/copy.png) 

-  案例

    ```python
    import copy
    a = [1,2,3,4,['a','b']]
    b = a
    c = copy.copy(a)
    d = copy.deepcopy(a)
    a.append(5)
    a[4].append('c')
    print(a)     # [1, 2, 3, 4, ['a', 'b', 'c'], 5]
    print(b)     # [1, 2, 3, 4, ['a', 'b', 'c'], 5]
    print(c)     # [1, 2, 3, 4, ['a', 'b', 'c']]
    print(d)     # [1, 2, 3, 4, ['a', 'b']]
    ```

浅拷贝：只拷贝顶层数据，其余层拷贝的是引用，切片也是浅拷贝

深拷贝：是递归性质的拷贝，会在内存中生成一套完全一样的内容。改变时互不影响

> 例子：克隆羊与化名

## 浅拷贝三种情况

拷贝不可变对象：只是增加一个指向原对象的引用，改变会互相影响。

拷贝可变对象(一层结构)：产生新的对象，开辟新的内存空间，改变互不影响。

拷贝可变对象(多层结构)：产生新的对象，开辟新的内存空间，不改变包含的子对象则互不影响、改变包含的子对象则互相影响。

## 值传递引用传递

传值：是把实参的值赋给形参，修改形参，不会影响实参

传引用：以地址的方式传递参数，形参实参都是一个对象

于是就将传递**不可变数据**称为**传值**，传递**可变数据**称为**传引用**

## 形参实参

形参是声明函数时定义的，多个形参用逗号隔开，需要与传入的实参一一对应。

实参是在调用时，实际传入函数中的值。

## 不定长参数

在声明函数时，若不确定需要接收多少实参，就可以使用不定长参数来定义

*args接收单个出现的参数，接收后存为元组

**kwargs接收以键值对形式出现的参数，接收后存为一个字典