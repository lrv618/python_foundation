# python



### print()函数

> - 功能：向目的地传出内容
> - 输出内容：数字、字符串、表达式
> - 目的地：IDLE、控制台、文件



### 常见的转义字符

| 转义字符 | 说明                                                 |
| -------- | ---------------------------------------------------- |
| \n       | 换行符，将光标位置移到下一行开头。                   |
| \r       | 回车符，将光标位置移到本行开头。                     |
| \t       | 水平制表符，也即 Tab 键，一般相当于四个空格          |
| \b       | 退格（Backspace），将光标位置移到前一列。            |
| \\       | 反斜线                                               |
| \'       | 单引号                                               |
| \"       | 双引号                                               |
| \        | 在字符串行尾的续行符，即一行未完，转到下一行继续写。 |



```python

#开发时间：2020/5/12 15:47
#转义字符
print('hello\nworld')  #\  +转义功能的首字母   n-->newline的首字符表示换行
print('===================================')

print('hello\tworld')
print('===================================')

print('helloooo\tworld')
print('===================================')

print('hello\rworld')  #world将hello进行了覆盖
print('===================================')

print('hello\bworld') #\b是退一个格，将o退没了
print('===================================')

print('http:\\\\www.baidu.com')
print('===================================')

print('老师说:\'大家好\'')
print('===================================')

#原字符，不希望字符串中的转义字符起作用，就使用原字符，就是在字符串之前加上r,或R
print(r'hello\nworld')
print('===================================')
#注意事项， 最后一个字符不能是反斜杠
#print(r'hello\nworld\')
print(r'hello\nworld\\')
```

输出结果

![image-20230327173727334](.\images\image-20230327173727334.png)



### 关键字

```python
import keyword
print(keyword.kwlist)
```

![image-20230327175733828](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020678.png)



### 变量的定义和使用



```python
name='cxk'
print(name)
print("================")

print('标识',id(name))
print('类型',type(name))
print('值',name)
```



![image-20230327181055994](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020192.png)



当多次赋值后，变量名会指向新的空间

```python
name='dmm'
print(name)

name='cxk'
print(name)    #指向新的空间
```



<img src="https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020961.png" alt="image-20230327181544281" style="zoom:150%;" />



### 数据类型

![img](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020503.png)



#### 整数类型

> - 十进制：默认
> - 二进制：0b开头
> - 八进制：0o开头
> - 十六进制：0x开头



```python
n1=90
n2=-76
n3=0
print(n1,type(n1))
print(n2,type(n2))
print(n3,type(n3))
print("===========================")
#整数可以表示为二进制，十进制，八进制，十六进制
print('十进制',118)
print('二进制',0b10101111)  #二进制以0b开头
print('八进制',0o176)   #八进制以0o开头
print('十六进制',0x1EAF)
```

![image-20230327182420638](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020548.png)



#### 浮点类型

> *浮点数存储不精确性*
>
> 使用浮点数进行计算时，可能出现小数位数不确定情况



```python
n1=1.1
n2=2.2
n3=2.1
print(n1+n2)    #输出结果：3.3000000000000003
print(n1+n3)    #输出结果：3.2
```



解决方法；

*引用decimal()函数*

```python
from decimal import Decimal
print(Decimal('1.1')+Decimal('2.2'))  #输出结果：3.3
```



#### 布尔类型

> - 用来表示真或者假的值
> - true表示真，false表示假
> - ***区别于别的语言：python的布尔值可以转换成整数来计算***

```python
f1=True
f2=False
print(f1,type(f1))
print(f2,type(f2))
print("===========================")

#布尔值可以转成整数计算
print(f1+1)  #2     1+1的结果为2,True表示1
print(f2+1)  #1     0+1的结果为1,False表示0
```



<img src="https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020083.png" alt="image-20230327183718853" style="zoom:150%;" />



#### 字符串类型

> *字符串可以是''、'' ''、''' 换行输出'''、''' 换行输出'''*

```python
str1='人生苦短，我用Python_1'
print(str1,type(str1))
print("===================================")

str2="人生苦短，我用Python_2"
print(str2,type(str2))
print("===================================")


str3="""人生苦短，
我用Python_3"""
print(str3,type(str3))
print("===================================")

str4='''人生苦短，
我用Python_4'''
print(str4,type(str4))
```

![image-20230327184546251](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020510.png)



#### 数据类型转换

将不同数据类型拼接就需要数据类型转换

| 函数名  |            作用            | 注意事项                                                     |             举例             |
| :-----: | :------------------------: | ------------------------------------------------------------ | :--------------------------: |
|  str()  |   将其他类型转换成字符串   | 也可以带"引号 "转换                                          |  str(123)            '123'   |
|  int()  |    将其他类型转换成整数    | 1.文字类和小数类字符串，无法转换成整数                                         2.浮点数转换成整数：抹零取整 |  int('123')       int(9.8)   |
| float() | 将其他数据类型转换成浮点数 | 1.文字类无法转换成整数                                                                               2.整数转成浮点数，末尾为0 | float('9.9')        float(9) |



##### str()将其它类型转成str类型

```python
print('----------------str()将其它类型转成str类型---')
a=10
b=198.8
c=False
print(type(a),type(b),type(c))
print(str(a),str(b),str(c),type(str(a)),type(str(b)),type(str(c)))
```

![image-20230327191052847](.\images\image-20230327191052847.png)



##### int()将其它的类型转int类型

```python
print('----------int()将其它的类型转int类型-----------------')
s1='128'
f1=98.7
s2='76.77'
ff=True
s3='hello'

print(type(s1),type(f1),type(s2),type(ff),type(s3))
print("==========================================================================")
print(int(s1),type(int(s1)))   #将str转成int类型 ,字符串为 数字串
print(int(f1),type(int(f1)))   #float转成int类型，截取整数部分，舍掉小数部分
#print(int(s2),type(int(s2)))  ####将str转成int类型，报错，因为字符串为小数串
print(int(ff),type(int(ff)))
#print(int(s3),type(int(s3)))  ####将str转成int类型时，字符串必须为数字串（整数），非数字串是不允许转换
```

![image-20230327191459828](.\images\image-20230327191459828.png)



##### float()函数将其它数据类型转成float类型

```python
print('------------float()函数，将其它数据类型转成float类型')

s1='128.98'
s2='76'
ff=True
s3='hello'
i=98

print(type(s1),type(s2),type(ff),type(s3),type(i))
print("==========================================================================")
print(float(s1),type(float(s1)))
print(float(s2),type(float(s2)))
print(float(ff),type(float(ff)))
#print(float(s3),type(float(s3))) #字符串中的数据如果是非数字串，则不允许转换
print(float(i),type(float(i)))
```



![image-20230327191626654](.\images\image-20230327191626654.png)



### input()函数

```python
present     =      input  ('大圣想要什么礼物呢?')
 变量   赋值运算符  输入函数 
print(present,type(present))
```



> 从键盘录入两个整数，计算两个整数的和

```python
a=int(input('请输入一个加数:'))
#a=int(a)   #将转换之后的结果存储到a中
b=int(input('请输入另一个加数:'))
#b=int(b)
print(type(a),type(b))
print(a+b)
```



```python
import time

hero = input('输入你的名字:')
gf = input('输入女友/男友的名字:')
boss = input('输入老板的名字:')
test = input('进群验证，你是谁？')
if hero == test:
    print('-*50')
    time.sleep(1)
    print('-*50 ')
    print('恭候{}大驾光临'.format(hero)+'\n')
    time.sleep(1.5)
    print('群主：第一次听到{}这个名字的时候就知道，你一定非常优秀'.format(hero)+'\n')
    time.sleep(2)
    print('{}:I love you three thousand times，{}'.format(gf,hero)+'\n')
    time.sleep(2)
    print('{}:终有一天，你将担任ceo，迎娶白富美，走上人生巅峰'.format(boss)+'\n')
    time.sleep(2)
    print('王健林:{}，我很看好你，一定会很快完成一个小目标，赚上一个亿'.format(hero)+'\n')
    time.sleep(2)
    print('七大姑八大姨:看看人家{}，年少有为，多和人家学学'.format(hero))
    time.sleep(2)
    print(' ')
    print('-*50')
else:
    print('-*50')
    time.sleep(1)
    print('你不是天选之人，进群失败')
```



### 运算符

#### 算术运算符

> 假设变量： **a=10，b=20**：

| +    | 加 - 两个对象相加                               | a + b 输出结果 30                                  |
| ---- | ----------------------------------------------- | -------------------------------------------------- |
| -    | 减 - 得到负数或是一个数减去另一个数             | a - b 输出结果 -10                                 |
| *    | 乘 - 两个数相乘或是返回一个被重复若干次的字符串 | a * b 输出结果 200                                 |
| /    | 除 - x除以y                                     | b / a 输出结果 2                                   |
| %    | 取模 - 返回除法的余数                           | b % a 输出结果 0                                   |
| **   | 幂 - 返回x的y次幂                               | a**b 为10的20次方， 输出结果 100000000000000000000 |
| //   | 取整除 - 返回商的整数部分（**向下取整**）       | `>>> 9//2 4 >>> -9//2 -5`                          |



```python
print(1+1) # 加法运算

print(1-1) # 减法运算

print(2*4) # 乘法运算

print(1/2) # 除法运算

print(11/2) # 除法运算

print(11%2) # 取余运算

print(2**2) #表示的是2的2次方

print(2**3) #表示的是2的3次方  2*2*2

print(11//2)  # 5 整除运算
print(9//4) #2
print(-9//-4) # 2

print(9//-4) #-3
print(-9//4) # -3  一正一负的整数公式，向下取整

print(9%-4) # -3  公式  余数=被除数-除数*商    9-(-4)*(-3)  9-12-->  -3
print(-9%4) # 3                             -9-4*(-3) -9+12--> 3
```



#### 赋值运算符

> 假设变量： **a=10，b=20**：

| 运算符 | 描述             | 实例                                  |
| :----- | :--------------- | :------------------------------------ |
| =      | 简单的赋值运算符 | c = a + b 将 a + b 的运算结果赋值为 c |
| +=     | 加法赋值运算符   | c += a 等效于 c = c + a               |
| -=     | 减法赋值运算符   | c -= a 等效于 c = c - a               |
| *=     | 乘法赋值运算符   | c *= a 等效于 c = c * a               |
| /=     | 除法赋值运算符   | c /= a 等效于 c = c / a               |
| %=     | 取模赋值运算符   | c %= a 等效于 c = c % a               |
| **=    | 幂赋值运算符     | c **乘乘= a 等效于 c = c乘乘 ** a     |
| //=    | 取整除赋值运算符 | c //= a 等效于 c = c // a             |



#### 比较运算符

> 以下假设变量a为10，变量b为20：

| 运算符 | 描述                                                         | 实例                                     |
| :----- | :----------------------------------------------------------- | :--------------------------------------- |
| ==     | 等于 - 比较对象是否相等                                      | (a == b) 返回 False。                    |
| !=     | 不等于 - 比较两个对象是否不相等                              | (a != b) 返回 True。                     |
| <>     | 不等于 - 比较两个对象是否不相等。**python3 已废弃。**        | (a <> b) 返回 True。这个运算符类似 != 。 |
| >      | 大于 - 返回x是否大于y                                        | (a > b) 返回 False。                     |
| <      | 小于 - 返回x是否小于y。所有比较运算符返回1表示真，返回0表示假。这分别与特殊的变量 True 和 False 等价。 | (a < b) 返回 True。                      |
| >=     | 大于等于 - 返回x是否大于等于y。                              | (a >= b) 返回 False。                    |
| <=     | 小于等于 - 返回x是否小于等于y。                              | (a <= b) 返回 True。                     |



```python
a,b=10,20
print('a>b吗?',a>b)  #False
print('a<b吗?',a<b) #True
print('a<=b吗?',a<=b) #True
print('a>=b吗?',a>=b) #False
print('a==b吗?',a==b) #False
print('a!=b吗?',a!=b) #True

''' 一个  = 称为赋值运算符  , ==称为比较运算符
  一个变量由三部分组成，标识，类型，值 
   == 比较的是值还是标识呢?  比较的是值
  比较对象的标识使用  is 
'''
a=10
b=10
print(a==b)  #True  说明，a与b的value 相等
print(a is b ) #True 说明,a与b的id标识 ，相等
#以下代码没学过，后面会给大家讲解
lst1=[11,22,33,44]
lst2=[11,22,33,44]
print(lst1==lst2)  #value   -->True
print(lst1 is lst2) #id   -->False
print(id(lst1))
print(id(lst2))
print(a is not b ) #False  a的id与b的id是不相等的
print(lst1 is not lst2) #True
```



#### 逻辑运算符

> Python语言支持逻辑运算符，以下假设变量 a 为 10, b为 20:

| 运算符 | 逻辑表达式 | 描述                                                         | 实例                    |
| :----- | :--------- | :----------------------------------------------------------- | :---------------------- |
| and    | x and y    | 布尔"与" - 如果 x 为 False，x and y 返回 False，否则它返回 y 的计算值。 | (a and b) 返回 20。     |
| or     | x or y     | 布尔"或" - 如果 x 是非 0，它返回 x 的计算值，否则它返回 y 的计算值。 | (a or b) 返回 10。      |
| not    | not x      | 布尔"非" - 如果 x 为 True，返回 False 。如果 x 为 False，它返回 True。 | not(a and b) 返回 False |



> 除了以上的一些运算符之外，Python还支持成员运算符，测试实例中包含了一系列的成员，包括字符串，列表或元组。

| 运算符 | 描述                                                    | 实例                                              |
| :----- | :------------------------------------------------------ | :------------------------------------------------ |
| in     | 如果在指定的序列中找到值返回 True，否则返回 False。     | x 在 y 序列中 , 如果 x 在 y 序列中返回 True。     |
| not in | 如果在指定的序列中没有找到值返回 True，否则返回 False。 | x 不在 y 序列中 , 如果 x 不在 y 序列中返回 True。 |



```python
a,b=1,2
print('---------------------and 并且--------------------------')
print(a==1 and b==2) #True     True and True-->True
print(a==1 and b<2)  #False    True and False -->False
print(a!=1 and b==2)  #False   False and True-->False
print(a!=1 and b!=2) #False    False and False -->False

print('----------------------or 或者-------------------------')
print(a==1 or b==2)  #True or True -->True
print(a==1 or b<2)   #True  or False  -->True
print(a!=1 or b==2)  #False or True -->True
print(a!=1 or b!=2)  #False or False -->False

print('-----------------not 对bool类型操作数取反-------------------')
f=True
f2=False
print(not f)
print(not f2)

print('---------------------in 与not in------------------------------')
s='helloworld'
print('w' in s)
print('k' in s)
print('w' not in s ) #False
print('k' not in s) #True
```



#### 位运算符

> 按位运算符是把数字看作二进制来进行计算的。Python中的按位运算法则如下：
>
> 下表中变量 a 为 60，b 为 13，二进制格式如下：

```python
a = 0011 1100

b = 0000 1101

-----------------

a&b = 0000 1100

a|b = 0011 1101

a^b = 0011 0001

~a  = 1100 0011
```

| 运算符 | 描述                                                         | 实例                                                         |
| :----- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| &      | 按位***与运算符***：参与运算的两个值,*如果两个相应位都为1,则该位的结果为1,否则为0* | (a & b) 输出结果 12 ，二进制解释： 0000 1100                 |
| \|     | 按位***或运算符***：只要*对应的二个二进位有一个为1时，结果位就为1*。 | (a \| b) 输出结果 61 ，二进制解释： 0011 1101                |
| ^      | 按位***异或运算符***：当*两对应的二进位**相异时**，结果为1*  | (a ^ b) 输出结果 49 ，二进制解释： 0011 0001                 |
| ~      | 按位***取反运算符***：对数据的每个*二进制位取反,即把1变为0,把0变为1 。**~x** 类似于 **-x-1*** | (~a ) 输出结果 -61 ，二进制解释： 1100 0011，在一个有符号二进制数的补码形式。 |
| <<     | 左移动运算符：*运算数的各二进位全部左移若干位*，由 **<<** 右边的数字指定了移动的位数，*高位丢弃，低位补0*。 | a << 2 输出结果 240 ，二进制解释： 1111 0000                 |
| >>     | 右移动运算符：把">>"左边的*运算数的各二进位全部右移若干位*，**>>** 右边的数字指定了移动的位数 | a >> 2 输出结果 15 ，二进制解释： 0000 1111                  |

```python
print(4&8)  #按位与& ，同为1时结果为1
print(4|8)   #按位或| ，同为0时结果为0
print(4<<1)  #向左移动1位(移动一个位置) 相当于乘以2
print(4<<2)  #向左移动2位(移动2个位置)

print(4>>1)  #向右移动1位，相当于除以2
print(4>>2) #向右移动2位，相当于除以4
```



### 对象的布尔值

*python一切皆是对象，所有的对象都有一个布尔值*

- 获取对象的布尔值
- 使用内置函数bool()

以下对象的布尔值为flase

- false
- 数值0
- None
- 空字符串
- 空列表
- 空元组
- 空字典
- 空集合

```python
print('-----------------以下对象的布尔值为False--------------------------------')
print(bool(False)) #False
print(bool(0)) #False
print(bool(0.0)) #False
print(bool(None)) #False
print(bool('')) #False
print(bool("")) #False
print(bool([]))    #空列表
print(bool(list())) #空列表
print(bool(()))  #空元组
print(bool(tuple())) #空元组
print(bool({}))  #空字典
print(bool(dict())) #空字典
print(bool(set())) #空集合

print('---------------------其它对象的布尔值均为True------------------------------------')
print(bool(18))   #ture
print(bool(True))	#true
print(bool('helloworld'))	#true
```



### 判断

#### 选择结构

***程序根据判断条件的布尔值执行部分代码***

```python
age=int(input('请输入您的年龄:'))

if age:
    print("布尔值为ture,",+age)
else:
    print('布尔值为flase',+age)
```

<img src="https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020592.png" alt="image-20230329173304062" style="zoom:150%;" />





##### 单分支结构

```python
if 条件表达式:
	条件执行体...
```



```python
money=1000  #余额
s=int(input('请输入取款金额'))  #取款金额
#判断余额是否充足
if money>=s:
   money=money-s
   print('取款成功，余额为:',money)
```

![image-20230329170513531](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200020699.png)



##### 双分支结构

双分支结构if...else ,二选一执行

```python
if 判断条件：
    执行语句……
else：
    执行语句……
```

```python
num=int(input('请输入一个整数'))

#条件判断
if num%2==0:
    print(num,'是偶数')
else:
    print(num,'是奇数')
```

> "判断条件"成立时（非零），则执行后面的语句，而执行内容可以多行，以缩进来区分表示同一范围。
>
> else 为可选语句，当需要在条件不成立时执行内容则可以执行相关语句

![006faQNTgw1f5wnm0mcxrg30ci07o47l](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021516.gif)



##### 多分支结构

```python
if 判断条件1:
    执行语句1……
elif 判断条件2:
    执行语句2……
elif 判断条件3:
    执行语句3……
else:
    执行语句4……
```

```python
'''
从键盘录入一个整数 成绩
90-100  A
80-89   B
70-79   C
60-69   D
0-59    E
小于0或大于100 为非法数据（不是成绩的有效范围）
'''
score=int(input('请输入一个成绩:'))
#判断
if score>=90 and score<=100:
    print('A级')
elif score>=80 and score<=89:
    print('B级')
elif score>=70 and score<=79:
    print('C级')
elif score>=60 and score<=69:
    print('D级')
elif score>=0 and score<=59:
    print('E级')
else:
    print('对不起，成绩有误，不在成绩的有效范围')
```



##### 嵌套if

```python
#语句结构
if 条件表达式
	if 内置条件表达式：
		内存条件执行体1
	else:
		内存条件执行体2
else:
	条件执行体
```

```python
'''会员  >=200  8折
         >=100   9折
           不打折
   非会员  >=200   9.5折
            不打折'''
answer=input('您是会员吗?y/n')
money=float(input('请输入您的购物金额:'))
#外层判断是否是会员
if answer=='y' : #会员
    if money>=200:
        print('打8折,付款金额为:',money*0.8)
    elif money>=100:
        print('打9折,付款金额为:',money*0.9)
    else:
        print('不打折，付款金额为:',money)
else:  #非会员
    if money>=200:
        print('打9.5折,付款金额为:',money*0.95)
    else:
        print('不打折，付款金额为:',money)
```



条件表达式

条件表达式是if...else的简写

语法结构:

x 	if 	判断条件	else	y

运算规则

```python
如果判断条件的布尔值为True,
	条件表达式返回值为x,
	否则
	条件表达式返回值为flase
```

```python
'''从键盘录入两个整数，比较两个整数的大小'''
num_a=int(input('请输入第一个整数'))
num_b=int(input('请输入第二个整数'))
#比较大小
'''if num_a>=num_b:
    print(num_a,'大于等于',num_b)
else:
    print(num_a,'小于',num_b)
'''
print('使用条件表达式进入比较')
print(  str(num_a)+'大于等于'+str(num_b)   if num_a>=num_b else   str( num_a)+'小于'+str(num_b)    )
#numa>=numb 输出前面语句，否则输出后面那一句
```



##### pass语句

> pass语句，什么都不做，只是一个占位符，用到需要写语句的地方

```python
#pass语句，什么都不做，只是一个占位符，用到需要写语句的地方
answer=input('您是会员吗?y/n')

#判断是否是会员
if answer=='y':
    pass
else:
    pass
```

![image-20230329172638055](.\images\image-20230329172638055.png)





### 循环

#### range()函数

> (a,b,c)  a起始值  b结束值  c步长
>
> ***默认从0开始，默认相差1称为步长***

用于生成一个整数序列

*返回值是一个迭代器对象*

range类型的优点

> 不管range对象表示的整数序列有多长，所有range对象占用的内存空间都是相同的，因为需要存储*strat，stop，step*；只有用到range对象时，才会去计算序列中的相关元素。
>
> *in和not in判断整数序列中是否存在（不存在）指定的整数*

```python
#(a,b,c) a起始值 b结束值 c步长

#range()的三种创建方式

print("============================第一种创建方式，只有一个参数（小括号中只给了一个数）======================")
r=range(10)   #[0, 1, 2, 3, 4, 5, 6, 7, 8, 9],默认从0开始，默认相差1称为步长
print(r)  #range(0, 10)
print(list(r)) #用于查看range对象中的整数序列    -->list是列表的意思


print("===========================第二种创建方式，给了两个参数（小括号中给了两个数）==========================")
r=range(1,10)  #指定了起始值，从1开始，到10结束（不包含10），默认步长为1
print(list(r)) #[1, 2, 3, 4, 5, 6, 7, 8, 9]


print("==========================第三种创建方式，给了三个参数（小括号中给了三个数）===========================")
r=range(1,10,2)
print(list(r)) #[1, 3, 5, 7, 9]


print("==============================判断指定的整数 在序列中是否存在 in ,not in=============================")
print(10 in r) #False ,10不在当前的r这个整数序列中
print(9 in r) #True,9在当关的r这个序列中

print(10 not in r) #True
print(9 not in r) #False

print(range(1,20,1))   #[1...19]
print(range(1,101,1))  #[1,....100]
```



#### 循环结构

##### while循环

while 语句用于循环执行程序，即在某条件下，循环执行某段程序，以处理需要重复处理的相同任务。其基本形式为：

```python
while 判断条件(condition)：
    执行语句(statements)……
```

> ​		执行语句可以是单个语句或语句块。判断条件可以是任何表达式，任何非零、或非空（null）的值均为true。
>
> ​		当判断条件假 false 时，循环结束。



```python
a=1
#判断条件表达式
while a<10:
    #执行条件执行体
    print(a)
    a+=1
```

![006faQNTgw1f5wnm06h3ug30ci08cake](.\PYTHON\006faQNTgw1f5wnm06h3ug30ci08cake-168008754839810.gif)

步循环法

> 1.  初始化变量
> 2.  条件判断
> 3.  条件执行体（循环体）
> 4.  改变变量
>
>  总结： 初始化的变量与条件判断的变量与改变的变量为同一个

计算0到4之间的累加和

```python
sum=0 #用存储累加和
'''初始化变量为0'''
a=0
'''条件判断'''
while a<5:
    '''条件执行体（循环体)'''
    sum+=a
    '''改变变量'''
    a+=1  #赋值运算相当于：a=a+1
print('和为',sum)
```



计算1到100之间的偶数和

```python
#print(bool(0))
sum=0  #用于存储偶数和
'''初始化变量'''
a=1
'''条件判断'''
while a<=100:
    '''条件执行体（求和)'''
    #条件判断是否是偶数
    if not bool(a%2):               #if a%2==0:
        sum+=a
    '''改变变量'''
    a+=1
print('1-100之间的偶数和',sum)
```



![loop-over-python-list-animation](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021217.gif)



##### for循环

> for-in循环
>
> - in表达从（字符串、序列等）中依次取值，称为遍历
> - for-in遍历的对象都是可迭代对象



第一次取出来的是P ,将P赋值值item,将item的值输出

```python
for item in 'Python':  #第一次取出来的是P ,将P赋值值item,将item的值输出
   print(item,end='\t')	#end='\t'不换行输出
```



range() 产生一个整数序列，--》也是一个可迭代对象

```python
range() 产生一个整数序列，--》也是一个可迭代对象
for i in range(10):
    print(i,end='\t') #end='\t'不换行输出
```



如果在循环体中不需要使用到自定义变量，可将自定义变量写为“_”

```python
#如果在循环体中不需要使用到自定义变量，可将自定义变量写为“_”
for _ in range(5):
    print('人生苦短，我用Python')

```



使用for循环，计算1到100之间的偶数和

```python
print('使用for循环，计算1到100之间的偶数和')

sum=0  #用于存储偶数和
for item in range(0,100):
    if item %2==0:
        sum+=item

print('1到100之间的偶数和为:',sum)
#输出结果：1到100之间的偶数和为: 2550
```



##### break语句

> 用于*结束循环*结构，常与分支结构if一起使用

```python
'''从键盘录入密码，最多录入3次，如果正确就结束循环'''
for item in range(3):
    pwd=input('请输入密码:')
    if pwd=='8888':
        print('密码正确')
        break
    else:
        print('密码不正确')
```



```python
a=0
while a<3:
    '''条件执行体(循环体)'''
    pwd=input('请输入密码:')
    if pwd=='8888':
        print('密码正确')
        break
    else:
        '''改变变量'''
        a += 1
        print('密码不正确')
```



##### continue语句

> - 用于*结束当前循环，进入下一次循环*，通常与分支结构中的if一起使用

```python
'''要求输出1到50之间所有5的倍数,  5,10,15,20,25....
    5的倍数的共同点：  和5的余数为0的数都是5的倍数
    什么样的数不是5的倍数，   1，2，3，4，6，7，8，9.。。  与5的余数不为0的数都不是5的倍数
    要求是使用continue实现
   '''
for item in range(0,50):
    if item%5==0:
        print(item)

print('-------------使用continue-----------------')
for item in range(0,50):
    if item%5!=0:
        continue
    print(item)
```



##### 嵌套循环

```python
for i in range(0,3): #行表，执行三次，一次是一行
    for j in range(0,4):
        print('*',end='\t')  #,end='\t',不换行输出
    print() #打行
```

![image-20230329214612496](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200022596.png)





```python
for i in range(1,10): #行数
    for j in range(1,i+1):   #第2位开始——第11位结束
        print(i,'*',j,'=',i*j,end='\t')   #,end='\t',不换行输出
    print()
```





##### 二重循环的break和continue

> - 二重循环的break和continue用于控制本层循环

```python
for i in range(5):  #代表外层循环要执行5次
    for j in range(1,11):
        if j%2==0:
            #break
            continue
        print(j,end='\t')
    print()
```

![image-20230329222102564](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021292.png)



### 字符串

#### 逗留机制

> - 保存一份相同且不可变字符串的方法
> - 不同的值被存放在字符串的驻留池中
> - Python的驻留机制对相同的字符串*只保留一份拷贝*，<u>后续创建相同字符串时，不会开辟新空间，而是把该字符串的地址赋给创新的变量</u>



字符串逗留机制优缺点

- 当需要值相同的字符串时，可以直接从字符串池里拿出来使用，避免频繁创建和销毁，提高效率和节约内存。
- 在需要进行字符串拼接时建议使用str类型的join方法（不要+），因为*join()方法是先计算出所有字符串长度，然后再拷贝，只new一次对象*。



#### 字符串查询

```py
#字符串的查询操作
s='hello,hello'
print(s.index('lo')) #3
print(s.find('lo'))#3
print(s.rindex('lo')) #9
print(s.rfind('lo'))#9

#print(s.index('k')) #ValueError: substring not found
print(s.find('k'))  #-1
#print(s.rindex('k')) #ValueError: substring not found
print(s.rfind('k')) #-1
```



#### 字符串大小写转换

|    方法名称    | 作用                                                         |
| :------------: | ------------------------------------------------------------ |
|   *upper()*    | 把字符串中*所有字符都转变成大写字母*                         |
|   *lower()*    | 把字符串中*所有字符都转成小写字母*                           |
|  *swapcase()*  | 把字符串*所有大写字母转小写字母，把所有小写字母转大写字母*   |
| *capitalize()* | 把*第一个字符串转成大写，其余字符串转成小写*                 |
|   *title()*    | *把每个单词的第一个字符串转变为大写，把每个单词的剩余字符转换成小写* |



```py
#字符串中的大小写转换的方法
s='hello,python'
a=s.upper()  #转成大写之后，会产生一个新的字符串对象
print(a,id(a))    #HELLO,PYTHON 2536619926896
print("==============================================")

print(s,id(s))    #hello,python 2536619510384
b=s.lower()  #转换之后，会产生一个新的字符串对象
print(b,id(b))#hello,python 2536619978928

print(s,id(s))  #True

print(b==s)
print(b is s) #False
print("==============================================")
```



```py
s2='hello,Python'
print(s2.swapcase())

print(s2.title())
'''
False
HELLO,pYTHON
Hello,Python
'''
```



#### 字符串对齐

| 方法名称 | 作用                                                         |
| :------: | ------------------------------------------------------------ |
| center() | 居中对齐，*第1个参数指定宽度，第2个参数指定填充字符*，第2个参数是可选的，默认是空格，如果设置欢度小于实际宽度则返回字符串 |
| ljust()  | 左对齐，*第1个参数指定宽度，第2个参数指定填充字符*，第2个参数是可选的，默认是空格如果设置宽度小于实际宽度则返回原字符串 |
| rjust()  | 右对齐，*第1个参数指定宽度，第2个参数指定填充符*，第2个参数是可选的，默认是空格如果设置宽度小于实际宽度则返回原字符串 |
| zfill()  | 右对齐，*左边用0填充，该方法只接收一个参数，用于指定字符串宽度*，如果指定宽度小于等于字符串的长度，返回字符串本身 |

```py
s='hello,Python'
'''居中对齐'''
print(s.center(20,'*'))

'''左对齐'''
print(s.ljust(20,'*'))
print(s.ljust(10))
print(s.ljust(20))

'''右对齐'''
print(s.rjust(20,'*'))
print(s.rjust(20))
print(s.rjust(10))

'''右对齐，使用0进行填充'''
print(s.zfill(20))
print(s.zfill(10))
print('-8910'.zfill(8))
```

![image-20230401235417071](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021700.png)



#### 字符串的劈分

| 方法名称 | 作用                                                         |
| :------: | :----------------------------------------------------------- |
| split()  | 从字符串的*左边开始劈分*，*默认的劈分字符串是空格字符串，返回的值都是一个列表* |
|          | 以*通过参数sep指定劈分字符串是劈分符*                        |
|          | 通过*参数maxsplit指定劈分字符串时的最大劈分次数*，在*经过最大次劈分之后，剩余的子串会单独作为一部分* |
| rsplit() | 从字符串的*右边开始劈分*，*默认的劈分字符串是空格字符串，返回的值是一个列表* |
|          | 以*通过参数sep指定劈分字符串劈分符*                          |
|          | 通过*参数maxsplit指定劈分字符串时的最大劈分次数*，*在经过最大次劈分之后，剩余的子串会单独作为一部分* |



```py
s='hello world Python'
lst=s.split()
print(lst)
s1='hello|world|Python'
print(s1.split(sep='|'))    #以竖线为分割位分割
print(s1.split(sep='|',maxsplit=1))
print('-------------------------------')
'''rsplit()从右侧开始劈分'''
print(s.rsplit())
print(s1.rsplit('|'))     #以竖线为分割位分割
print(s1.rsplit(sep='|',maxsplit=1))
```

![image-20230402001627980](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021639.png)



#### 字符串判断

|    方法名称    | 作用                                                         |
| :------------: | ------------------------------------------------------------ |
| isidentifier() | 判断指定的字符串*是不是合法的标识符*                         |
|   isspace()    | 判断指定的字符串*是否全部由空白字符组成（回车、换行、水平制表符)*） |
|   isalpha()    | 判断指定的字符串*是否全部由字母组成*                         |
|  isdeximal()   | 判断指定字符串*是否全部由十进制的数字组成*                   |
|  isnumeric()   | 判断指定的字符串*是否全部由数字组成*                         |
|   isalnum()    | 判断指定字符串*是否全部由字母和数字组成*                     |

```py
s='hello,python'
print('1.',s.isidentifier()) #False
print('2.','hello'.isidentifier()) #True
print('3.','张三_'.isidentifier()) #True
print('4.','张三_123'.isidentifier()) #True

print('5.','\t'.isspace()) #True

print('6.','abc'.isalpha()) #True
print('7.','张三'.isalpha()) #True
print('8.','张三1'.isalpha()) #False

print('9.','123'.isdecimal()) #True
print('10.','123四'.isdecimal()) # False
print('11.','ⅡⅡⅡ'.isdecimal()) # False

print('12.','123'.isnumeric()) #True
print('13.','123四'.isnumeric())#True
print('14.','ⅡⅡⅡ'.isnumeric()) #True

print('15.','abc1'.isalnum()) #True
print('16.','张三123'.isalnum()) #True
print('17.','abc!'.isalnum()) #False
```



#### 字符串替换与合并

**字符串替换**：

| 方法名称  | 作用                                                         |
| :-------: | ------------------------------------------------------------ |
| replace() | *第一个参数指定被替换的子串，第二个参数指定替换子串的字符串*，该方法返回替换后得到的字符串，替换前的字符串不发生变化，调用该方法时可以提供*第三个参数指定最大的替换次数* |
|  join()   | *将列表或元组中的字符串合并成一个字符串*                     |

```py
s='hello,Python'
print(s.replace('Python','Java'))
s1='hello,Python,Python,Python'
print(s1.replace('Python','Java',2))


lst=['hello','java','Python']
print('|'.join(lst))
print(''.join(lst))

t=('hello','Java','Python')
print(''.join(t))

print('*'.join('Python'))
```

![image-20230402002642407](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021109.png)



#### 字符串的比较操作

**运算符:**>,>=,<,<=,==,!=

> **比较规则**:首先比较两个字符串中的第一个字符，如果相等则继续比较下一个字符，依次比较下去，直到两个字符串中的字符不相等时，其比较结果就是两个字符串的比较结果，两个字符串中的所有后续字符将不再被比较。
>
> **比较原理**:两上字符进行比较时，比较的是其ordinal value(原始值)，调用内置函数ord可以得到指定字符的ordinal value。与内置函数ord对应的是内置函数chr,调用内置函数chr时指定ordinal value可以得到其对应的字符。

```py
print('apple'>'app') #True
print('apple'>'banana') #False   ，相当于97>98 >False
print(ord('a'),ord('b'))#97 98
print(ord('杨'))#26472

print(chr(97),chr(98))  #a b
print(chr(26472))	#杨

'''== 与is的区别
  == 比较的是 value
  is  比较的是id是否相等'''
a=b='Python'
c='Python'
print(a==b)  #True
print(b==c)  #True

print(a is b)  #True
print(a is c ) #True
print(id(a)) #2204259933168
print(id(b)) #2204259933168
print(id(c)) #2204259933168
```



#### 字符串的切片操作

字符串是不可变类型

> - 不具备增删改操作
> - 切片操作将产生新对象

```py
s='hello,Python'
s1=s[:5]   #由于没有指定起始位置，所以从0开始切  
s2=s[6:]  #由于没有指定结束位置，所以切到字符串的最后一个元素  
s3='!'
newstr=s1+s3+s2  

print(s1)   #hello
print(s2)   #Python
print(newstr)  #hello!Python

print('--------------------')
print(id(s))
print(id(s1))
print(id(s2))
print(id(s3))
print(id(newstr))

print('------------------切片[start:end:step]-------------------------')
print(s[1:5:1])   #从1开始截到5（不包含5），步长为1
print(s[::2])  #默认从0 开始，没有写结束，默认到字符串的最后一个元素 ,步长为2  ，两个元素之间的索引间隔为2
print(s[::-1]) #默认从字符串的最后一个元素开始，到字符串的第一个元素结束，因为步长为负数
print(s[-6::1]) # 从索引为-6开始，到字符串的最后一个元素结束，步长为1
```

![image-20230402005941275](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021665.png)



#### 格式化字符串

python 字符串格式化符号:

| 符  号 | 描述                                   |
| :----- | :------------------------------------- |
| %c     | 格式化字符及其ASCII码                  |
| %s     | *格式化字符串*                         |
| %d     | *格式化整数*                           |
| %u     | 格式化无符号整型                       |
| %o     | 格式化无符号八进制数                   |
| %x     | 格式化无符号十六进制数                 |
| %X     | 格式化无符号十六进制数（大写）         |
| %f     | *格式化浮点数字，可指定小数点后的精度* |
| %e     | 用科学计数法格式化浮点数               |
| %E     | 作用同%e，用科学计数法格式化浮点数     |
| %g     | %f和%e的简写                           |
| %G     | %F 和 %E 的简写                        |
| %p     | 用十六进制数格式化变量的地址           |

格式化操作符辅助指令:

| 符号  | 功能                                                         |
| :---- | :----------------------------------------------------------- |
| *     | 定义宽度或者小数点精度                                       |
| -     | 用做左对齐                                                   |
| +     | 在正数前面显示加号( + )                                      |
| <sp>  | *在正数前面显示空格*                                         |
| #     | 在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X') |
| 0     | 显示的数字前面填充'0'而不是默认的空格                        |
| %     | '%%'输出一个单一的'%'                                        |
| (var) | 映射变量(字典参数)                                           |
| m.n.  | m 是显示的最小总宽度,n 是小数点后的位数(如果可用的话)        |

Python2.6 开始，新增了一种格式化字符串的函数 [str.format()](https://www.runoob.com/python/att-string-format.html)，它增强了字符串格式化的功能。



```py
#格式化字符串
#(1) % 占位符
name='张三'
age=20
print('我叫%s,今年%d岁' % (name,age))

#(2) {}
print('我叫{0},今年{1}岁'.format(name,age))

#(3)f-string
print(f'我叫{name},今年{age}岁')
```

![image-20230402011540266](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021883.png)



```py
print('%10d' % 99)  # 10表示的是宽度
print('%.3f' % 3.1415926)  # .3表示是小数点后三位
#同时表示宽度和精度
print('%10.3f' % 3.1415926)  # 一共总宽度为10，小数点后 3位


print('hellohello')
```

![image-20230402011611185](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200021615.png)



```py
print('{0:.3}'.format(3.1415926))  # .3表示的是一共是3位数

print('{:.3f}'.format(3.1415926)) # .3f表示是3位小数
1
print('{:10.3f}'.format(3.1415926))  # 同时设置宽度和精度，一共是10位，3位是小数
```

![image-20230402011650659](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200022694.png)



#### 字符串的编码转换

![02cf73cc51e2bfa345236e6fcc9143a](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200022070.png)

```py
s='唱跳rap打篮球'
#编码
print(s.encode(encoding='GBK'))  #在GBK这种编码格中 一个中文占两个字节
print(s.encode(encoding='UTF-8')) #在UTF-8这种编辑格式中，一个中文占三个字节

#解码
#byte代表就是一个二进制数据（字节类型的数据）
byte=s.encode(encoding='GBK')   #编码
print(byte.decode(encoding='GBK')) #解码

byte=s.encode(encoding='UTF-8')
print(byte.decode(encoding='UTF-8'))
```

![image-20230402013354627](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200022508.png)







### 空元组、空列表、空字典的创建

```py
'''空元组的创建方式'''
'''空列表的创建方式'''
lst=[]
lst1=list()

print('空列表',lst,lst1)

d={}
d2=dict()

print('空字典',d,d2)

#空元组
t4=()
t5=tuple()

print('空元组',t4,t5)
```



### 不可变序列与可变序列区别

> 不可变序列：字符串、元组
>
> - 不可变序列：*没有增删改操作*
>
> 可变序列：列表、字典
>
> - 可变序列：*可以对序列执行增删改操作，对象地址不发生改变*

```py
'''可变序列  列表，字典'''
lst=[10,20,45]
print(id(lst))
print("===========================")

lst.append(300)
print(id(lst))



'''不可变序列，字符串,元组'''
s='hello'
print(id(s))
s=s+'world'
print(id(s))
print(s)
```

![image-20230330203757513](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200022570.png)



### 列表、字典、元组、集合的区别

![67ba98b1a67f478e9522e62c1d2cba9f](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200022798.png)





### 列表

> - 变量存储一个元素
> - 列表可以*存储N个元素*，程序可以方便对这些数据进行整体操作
> - 列表<u>相当于其他语言的数组</u>
> - 列表是一个*有序序列*
> - 索引映射唯一个数据
> - 列表可以存储重复数据
> - 任意类型混存
> - 根据需要动态分配和回收



```python
'''创建列表的第一种方式，使用[]'''
lst=['hello','world',98,'a']
print(lst)
print(lst[0],lst[-4])   #a为-1

#['hello', 'world', 98, 'hello']
#hello hello
```



##### index()函数

> - *index()函数获取列表中元素的索引*
> - 如果列表中存在N个相同的元素，*只返回相同元素中第一个元素索引*
> - 如果查询的元素不存在于列表，抛出ValueError
> - 还可以在指定的start和stop之间进行查找   eg:list.index('hello',1,4) 1表示开始，4表示结束



```python
lst=['hello','world',98,'hello']
print(lst.index('hello')) #如果列表中有相同元素只返回列表中相同元素的第一个元素的索引
#print(lst.index('Python')) #ValueError: 'Python' is not in list
#print(lst.index('hello',1,3)) #ValueError: 'hello' is not in list   'world',98

print(lst.index('hello',1,4)) #3 list.index('hello',1,4) 1表示开始，4表示结束
```



##### 获取列表中的单个元素

> - 正向索引：0到N-1	eg:lst[0]
> - 逆向索引：-N到-1	eg:lst[-N]
> - 索引不存在抛出indexError

```python
lst=['hello','world',98,'hello','world',234]
#获取索引为2的元素
print(lst[2])
#获取索引为-3的元素
print(lst[-3])
#获取索引为10的元素
#print(lst[10]) #IndexError: list index out of range

#输出
#98
#hello
```



##### 获取列表中的多个函数

语法格式

*列表名[start:stop:step]*

```python
lst=[10,20,30,40,50,60,70,80]
#start=1,stop=6,step1
#print(lst[1:6:1])
print('原列表',id(lst))    	#原列表 2587465022336
lst2=lst[1:6:1]
print('切的片段:',id(lst2))   	#切的片段: 2587470817280
print(lst[1:6]) #默认步长为1     #[20, 30, 40, 50, 60]
print(lst[1:6:])				#[20, 30, 40, 50, 60]
#start=1,stop=6,step=2
print(lst[1:6:2])				#[20, 40, 60]
#stop=6,step=2,start采用默认
print(lst[:6:2])				#[10, 30, 50]
#start=1，step=2，stop采用默认
print(lst[1::2])				#[20, 40, 60, 80]
print('------------step步长为负数的情况-----------------')
print('原列表:',lst)			  #原列表: [10, 20, 30, 40, 50, 60, 70, 80]
print(lst[::-1])				#[80, 70, 60, 50, 40, 30, 20, 10]
#start=7,stop 省略 step=-1
print(lst[7::-1])				#[80, 70, 60, 50, 40, 30, 20, 10]
#start=6,stop=0,step=-2
print(lst[6:0:-2])				#[70, 50, 30]
```



##### 列表元素的判断与遍历

```python
print('p' in 'python') #True
print('k' not in 'python')#True

lst=[10,20,'python','hello']
print(10 in lst) #True
print(100 in lst) #False
print(10 not in lst) #False
print(100 not in lst) #True
print('--------------------------')
for item in lst:
    print(item)
```



##### 获取列表中指定元素

```python
lst=['hello','world',98,'hello','world',234]
#获取索引为2的元素
print(lst[2])
#获取索引为-3的元素
print(lst[-3])

#获取索引为10的元素
#print(lst[10]) #IndexError: list index out of range
```





##### 增加列表元素



| *append()*     | *在列表末尾添加一个元素*                           |
| -------------- | -------------------------------------------------- |
| ***extend()*** | ***在列表末尾至少添加一个元素***                   |
| ***insert()*** | ***在列表任意位置添加一个元素 [start:stop:step]*** |
| ***切片***     | ***在列表任意位置至少添加一个元素***               |



```python
list = []          ## 空列表
list.append('Google')   ## 使用 append() 添加元素
list.append('Runoob')
print (list)  #输出结果['Google', 'Runoob']
```

```python
#向列表的末尾添加一个元素
lst=[10,20,30]
print('添加元素之前',lst,id(lst))
lst.append(100)
print('添加元素之后',lst,id(lst))

lst2=['hello','world']

#向列表的末尾一次性添加多个元素
lst.extend(lst2)   #lst.append(lst2) #将lst2做为一个元素添加到list列表的末尾
print(lst)

#在任意位置上添加一个元素
lst.insert(1,90)   #在第1位置上添加90
print(lst)

lst3=[True,False,'hello']
#在任意的位置上添加N多个元素
lst[1:]=lst3  #切掉原先第1位以及后面的数，然后给它添加list3的新元素
print(lst)
```

![image-20230330001137770](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200022776.png)



##### 删除列表中的元素

| ***remove()*** | ***一次删除一个元素，重复元素只删除第一个，不存在抛出ValueError*** |
| -------------- | ------------------------------------------------------------ |
| ***pop()***    | ***删除一个指定索引位置上的元素，指定索引不抛出IndexError,不指定索引删除列表的最后一个元素*** |
| ***切片***     | ***一次至少删除一个元素***                                   |
| ***clear()***  | ***清空列表***                                               |
| ***del***      | ***删除列表***                                               |

​						

```python
lst=[10,20,30,40,50,60,30]
print(lst)

lst.remove(30) #从列表中移除一个元素，如果有重复元素只移第一个元素
print(lst)
#lst.remove(100) #ValueError: list.remove(x): x not in list

#pop()根据索引移除元素
lst.pop(1)
print(lst)

#lst.pop(5) #IndexError: pop index out of range  如果指定的索引位置不存在，将抛出异常
lst.pop()  #如果不指定参数（索引），将删除列表中的最后一个元素
print(lst)
```

![image-20230330003831889](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023976.png)



```python
print('----------切片操作-删除至少一个元素 ，将产生一个新的列表对象-------------------')
new_list=lst[1:3]
print('原列表',lst)
print('切片后的列表',new_list)

'''不产生新的列表对象，而是删除原列表中的内容'''
lst[1:3]=[]
print(lst)

'''清除列表中的所有元素'''
lst.clear()
print(lst)

'''del语句将列表对象删除'''
del lst
#print(lst) #NameError: name 'lst' is not defined
```

<img src="https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023399.png" alt="image-20230330003857399" style="zoom:150%;" />



##### 修改列表元素操作

> - 为指定索引的元素赋予一个新的值
> - 为指定的切片赋予一个新的值

```python
lst=[10,20,30,40]
print(lst)      #[10, 20, 30, 40]
#一次修改一个值
lst[2]=100
print(lst)  #[10, 20, 100, 40]

lst[1:3]=[300,400,500,600]
print(lst)   #[10, 300, 400, 500, 600, 40]
```



##### 列表排序

> sort()方法，列中所有元素默认按照从小到大的顺序进行排序，可以通过reverse=True，进行降序排序

```python
lst=[20,40,10,98,54]
print('排序前的列表',lst,id(lst))
#开始排序 ,调用列表对象的sort方法,升序排序
lst.sort()
print('排序后的列表',lst,id(lst))   #lst()调用列表对象的sort方法,升序排序

#通过指定关键字参数，将列表中的元素进行降序排序
lst.sort(reverse=True)  #reverse=True 表示降序排序, reverse=False就是升序排序
print(lst)
lst.sort(reverse=False)   #sort()将列表中的元素进行降序排序
print(lst)

#排序前的列表 [20, 40, 10, 98, 54] 2093539523456
#排序后的列表 [10, 20, 40, 54, 98] 2093539523456
#[98, 54, 40, 20, 10]
#[10, 20, 40, 54, 98]
```



> 使用内置函数sorted()对列表进行排序，将产生一个新的列表对象

```python
lst=[20,40,10,98,54]
print('原列表',lst)
#开始排序
new_list=sorted(lst)   #相当于初始化
print(lst)
print(new_list)
#指定关键字参数，实现列表元素的降序排序
desc_list=sorted(lst,reverse=True)  #reverse=True 表示降序排序, reverse=False就是升序排序
print(desc_list)

'''
原列表 [20, 40, 10, 98, 54]
[20, 40, 10, 98, 54]
[10, 20, 40, 54, 98]
[98, 54, 40, 20, 10]
'''
```



##### 列表生成式

```py
# i*i表示列表元素的表达式(即真正的元素值)   i自定义变量  range(1,10)可迭代对象
lst=[i*i for i in range(1,10)]  
print(lst)

'''列表中的元素的值为2，4，6，8，10'''
lst2=[i*2 for i in range(1,6) ]
print(lst2)
```



##### 列表脚本操作符

> 列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表。

如下所示：

| Python 表达式                | 结果                         | 描述                 |
| :--------------------------- | :--------------------------- | :------------------- |
| len([1, 2, 3])               | 3                            | 长度                 |
| [1, 2, 3] + [4, 5, 6]        | [1, 2, 3, 4, 5, 6]           | 组合                 |
| ['Hi!'] * 4                  | ['Hi!', 'Hi!', 'Hi!', 'Hi!'] | 重复                 |
| 3 in [1, 2, 3]               | True                         | 元素是否存在于列表中 |
| for x in [1, 2, 3]: print x, | 1 2 3                        | 迭代                 |



##### 列表函数&方法

Python包含以下函数:

| 序号 | 函数                                                         |
| :--- | :----------------------------------------------------------- |
| 1    | [cmp(list1, list2)](https://www.runoob.com/python/att-list-cmp.html) 比较两个列表的元素 |
| 2    | [len(list)](https://www.runoob.com/python/att-list-len.html) 列表元素个数 |
| 3    | [max(list)](https://www.runoob.com/python/att-list-max.html) 返回列表元素最大值 |
| 4    | [min(list)](https://www.runoob.com/python/att-list-min.html) 返回列表元素最小值 |
| 5    | [list(seq)](https://www.runoob.com/python/att-list-list.html) 将元组转换为列表 |

Python包含以下方法:

| 序号 | 方法                                                         |
| :--- | :----------------------------------------------------------- |
| 1    | [list.append(obj)](https://www.runoob.com/python/att-list-append.html) 在列表末尾添加新的对象 |
| 2    | [list.count(obj)](https://www.runoob.com/python/att-list-count.html) 统计某个元素在列表中出现的次数 |
| 3    | [list.extend(seq)](https://www.runoob.com/python/att-list-extend.html) 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表） |
| 4    | [list.index(obj)](https://www.runoob.com/python/att-list-index.html) 从列表中找出某个值第一个匹配项的索引位置 |
| 5    | [list.insert(index, obj)](https://www.runoob.com/python/att-list-insert.html) 将对象插入列表 |
| 6    | [list.pop([index=-1\])](https://www.runoob.com/python/att-list-pop.html) 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值 |
| 7    | [list.remove(obj)](https://www.runoob.com/python/att-list-remove.html) 移除列表中某个值的第一个匹配项 |
| 8    | [list.reverse()](https://www.runoob.com/python/att-list-reverse.html) 反向列表中元素 |
| 9    | [list.sort(cmp=None, key=None, reverse=False)](https://www.runoob.com/python/att-list-sort.html) 对原列表进行排序 |



### 字典

> - 字典是另一种可变容器模型，且*可存储任意类型对象*。
>
> - 字典是一个*无序序列*
>
> - 字典*根据key查找value所在的位置*
>
> - 字典中所有的元素都是一个key-value对，*key不允许重复，value可以重复*，key重复后者覆盖前者的value
>
> - 字典中的key必须是不可变对象
>
> - 字典可以根据需求动态伸缩
>
> - 字典会浪费较大的内存，是一种使用空间换时间的数据结构
>
> - 字典的每个键值 **key:value** 对用冒号 **:** 分割，每个键值对之间用逗号 **,** 分割，整个字典包括在花括号 **{}** 中 
>
>   ​									***d = {key1 : value1,  key2 : value2 }***



##### 字典的创建

###### 使用大括号创建{}

```python
score={'张三':100, '李四':98, '王五'55}
```

```python
'''使用{}创建字典'''
scores={'张三':100,'李四':98,'王五':45}
print(scores)
print(type(scores))

#{'张三': 100, '李四': 98, '王五': 45}
#<class 'dict'>
```



###### dict()函数创建

```python
dict( name='jack'  ,  age=20 )
```

```python
'''第二种创建dict()'''
student=dict(name='jack',age=20)
print(student)

#{'name': 'jack', 'age': 20}
```



```python
'''空字典'''
d={}
print(d)

#{}
```



##### 获取字典中的值

###### []取值

> []如果字典中不存在指定的key，抛出keyError异常

```python
'''获取字典的元素'''
scores={'张三':100,'李四':98,'王五':45}
'''第一种方式，使用[]'''
print(scores['张三'])    #100
#print(scores['陈六']) #KeyError: '陈六'
```





###### get()方法创建

> 如果字典中不存在指定的key，并不会抛出KeyError而是返回None,可以通过参数设置默认的value，以便指定的key不存在返回

```py
'''第二种方式，使用get()方法'''
print(scores.get('张三'))	#100
print(scores.get('陈六')) #None
print(scores.get('麻七',99)) #99是在查找'麻七'所对的value不存在时，提供的一个默认值
```



##### 判断字典值纯在

> - in  指定的key在字典中存在返回true
> - not in 指定的key不在字典中返回true

```python
'''key的判断'''
scores={'张三':100,'李四':98,'王五':45}
print('张三' in scores)#True
print('张三' not in scores)#False
```



##### 增加字典元素

```py
scores['陈六']=98   #新增元素
print(scores)
#{'李四': 98, '王五': 45, '陈六': 98}
```



##### 修改字典元素

```py
scores['陈六']=100  #修改元素
print(scores)
#{'李四': 98, '王五': 45, '陈六': 100}
```



##### 删除字典元素

```py
del scores['张三']  #删除指定的key-value对
print(scores)
#{'李四': 98, '王五': 45}
```



##### 清空字典元素

```py
scores.clear()  #清空字典的元素
print(scores)
#{}
```



##### (查)获取字典视图

获取所有的key

```py
scores={'张三':100,'李四':98,'王五':45}
#获取所有的key
keys=scores.keys()
print(keys)
print(type(keys))
print(list(keys))  #将所有的key组成的视图转成列表
print("===================================")
```

![image-20230330173637918](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023352.png)



获取所有的value

```py
#获取所有的value
values=scores.values()
print(values)
print(type(values))
print(list(values))
print("===================================")
```

![image-20230330173707463](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023170.png)



获取所有的key-value对

```py
#获取所有的key-value对
items=scores.items()
print(items)
print(list(items))  #转换之后的列表元素是由元组组成 
print("===================================")
```

![image-20230330173739328](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023031.png)



##### 字典元素的遍历

```py
scores={'张三':100,'李四':98,'王五':45}
#字典元素的遍历
for  item  in scores:
    print(item,scores[item])
```

![image-20230330174558227](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023995.png)



##### 字典生成式

- 内置函数zip()

> 用于将迭代的对象作为参数，将对象中对应的元素打包成一个元组，然后返回这些元组组成的列表

![image-20230330182001881](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023318.png)

upper()函数使小写变大写

```py
items=['Fruits','Books','Others']   #用作键的变量
prices=[96,78,85,100,120]       #用作值的变量

lst=zip(items,prices)
print(list(lst))
#[('Fruits', 96), ('Books', 78), ('Others', 85)]


d={ a:b    for a,b  in zip(items,prices)  }
print(d)
#{'FRUITS': 96, 'BOOKS': 78, 'OTHERS': 85}
```



##### 字典内置函数&方法

Python字典包含了以下内置函数：

| 序号 | 函数及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [cmp(dict1, dict2)](https://www.runoob.com/python/att-dictionary-cmp.html) 比较两个字典元素。 |
| 2    | [len(dict)](https://www.runoob.com/python/att-dictionary-len.html) 计算字典元素个数，即键的总数。 |
| 3    | [str(dict)](https://www.runoob.com/python/att-dictionary-str.html) 输出字典可打印的字符串表示。 |
| 4    | [type(variable)](https://www.runoob.com/python/att-dictionary-type.html) 返回输入的变量类型，如果变量是字典就返回字典类型。 |

Python字典包含了以下内置方法：

| 序号 | 函数及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [dict.clear()](https://www.runoob.com/python/att-dictionary-clear.html) 删除字典内所有元素 |
| 2    | [dict.copy()](https://www.runoob.com/python/att-dictionary-copy.html) 返回一个字典的浅复制 |
| 3    | [dict.fromkeys(seq[, val\])](https://www.runoob.com/python/att-dictionary-fromkeys.html) 创建一个新字典，以序列 seq 中元素做字典的键，val 为字典所有键对应的初始值 |
| 4    | [dict.get(key, default=None)](https://www.runoob.com/python/att-dictionary-get.html) 返回指定键的值，如果值不在字典中返回default值 |
| 5    | [dict.has_key(key)](https://www.runoob.com/python/att-dictionary-has_key.html) 如果键在字典dict里返回true，否则返回false |
| 6    | [dict.items()](https://www.runoob.com/python/att-dictionary-items.html) 以列表返回可遍历的(键, 值) 元组数组 |
| 7    | [dict.keys()](https://www.runoob.com/python/att-dictionary-keys.html) 以列表返回一个字典所有的键 |
| 8    | [dict.setdefault(key, default=None)](https://www.runoob.com/python/att-dictionary-setdefault.html) 和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default |
| 9    | [dict.update(dict2)](https://www.runoob.com/python/att-dictionary-update.html) 把字典dict2的键/值对更新到dict里 |
| 10   | [dict.values()](https://www.runoob.com/python/att-dictionary-values.html) 以列表返回字典中的所有值 |
| 11   | [pop(key[,default\])](https://www.runoob.com/python/python-att-dictionary-pop.html) 删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。 |
| 12   | [popitem()](https://www.runoob.com/python/python-att-dictionary-popitem.html) 返回并删除字典中的最后一对键和值。 |



### 集合

> - 与列表、字典一样都是属于可变类型的序列
> - *集合是没有value的字典*

##### 集合的创建

###### 大括号{}创建

集合中的元素不允许重复

```python
s={2,3,4,5,5,6,7,7} #集合中的元素不允许重复
print(s)
```

![image-20230330213256851](.\images\image-20230330213256851.png)

###### 函数set()创建

```py
s1=set(range(6))
print(s1,type(s1))

s2=set([1,2,4,5,5,5,6,6])
print(s2,type(s2))

s3=set((1,2,4,4,5,65))  #集合中的元素是无序的
print(s3,type(s3))

s4=set('python')
print(s4,type(s4))

s5=set({12,4,34,55,66,44,4})
print(s5,type(s5))
```

![image-20230330213904011](.\images\image-20230330213904011.png)



##### 集合元素的判断操作

> - *in或not  in*

```py
#集合的相关操作
s={10,20,30,405,60}
'''集合元素的判断操作'''
print(10 in s)  #True
print(100 in s) # False
print(10 not in s) #False
print(100 not in s) #True
```



##### 集合元素的新增操作

> - 调用*add()方法，一次添中一个元素*
> - 调用*update()方法至少添加一个元素*

```py
s={10,20,30,405,60}
s.add(80)  #add一次添加一个元素
print(s)
s.update({200,400,300})  #一次至少添加一个元素
print(s)
s.update([100,99,8])
s.update((78,64,56))
print(s)
```

![image-20230330214957728](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023737.png)



##### 集合元素的删除操作

> - 调用*remove()方法，一次删除一个指定元素*，如果指定元素不存在抛出KeyError
> - 调用*discaard()方法，一次删除一个指定元素*，如果指定的元素不存在不抛出异常
> - 调用*pop()方法，一次只删除一个任意元素*
> - 调用*clear()方法，清空集合*

```py
s={10,20,30,405,60}
s.remove(100)
print(s)
#s.remove(500) #KeyError: 500
s.discard(500)
s.discard(300)
print(s)
s.pop()
s.pop()
```

![image-20230330215024920](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023836.png)



##### 集合间的关系

###### 两个集合是否相等

```py
'''两个集合是否相等（元素相同，就相等）'''
s={10,20,30,40}
s2={30,40,20,10}
print(s==s2)   #True
print(s!=s2)   #False
```



###### issubset()方法

> 判断 一个集合是另一个集合的子集

```python
'''一个集合是否是另一个集合的子集'''
s1={10,20,30,40,50,60}
s2={10,20,30,40}
s3={10,20,90}
print(s2.issubset(s1))  #True
print(s3.issubset(s1))  #False
```



###### issuperset()方法

> 判断一个集合是另一个集合的超集

```py
'''一个集合是否是另一个集合的超集'''
s1={10,20,30,40,50,60}
s2={10,20,30,40}
s3={10,20,90}
print(s1.issuperset(s2))  #True
print(s1.issuperset(s3))  #False
```



###### isdisjoint()方法

> 两个集合是否有交集

```py
'''两个集合是否含有交集'''
s1={10,20,30,40,50,60}
s2={10,20,30,40}
s3={10,20,90}
print(s2.isdisjoint(s3))  #False   有交集为False
s4={100,200,300}
print(s2.isdisjoint(s4))  #True    没有交集为True
```



###### intersection()方法

> intersection()与 & 等价，交集操作

```py
#（1）交集
s1={10,20,30,40}
s2={20,30,40,50,60}
print(s1.intersection(s2))   #{40, 20, 30}
print(s1 & s2)    #intersection()与 & 等价，交集操作   #{40, 20, 30}

```



###### union()方法

> union与  | 等价，并集操作

```python
#(2)并集操作
s1={10,20,30,40}
s2={20,30,40,50,60}
print(s1.union(s2))  #{40, 10, 50, 20, 60, 30}
print( s1 | s2)  #union与  | 等价，并集操作  #{40, 10, 50, 20, 60, 30}
```



###### difference()方法

> 差集操作

```py
s1={10,20,30,40}
s2={20,30,40,50,60}
print(s1.difference(s2))  #{10}
print(s1-s2)			  #{10}
```



###### symmetric_difference()方法

> 对称差集

```py
print(s1.symmetric_difference(s2))  #{50, 10, 60}
print(s1^ s2)   #{50, 10, 60}
```



##### 集合生成式

```py
#列表生成式
lst=[ i*i for i in range(10)]
print(lst)


#集合生成式
s={ i*i for i in range(10)}
print(s)
```

![image-20230330223917752](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023944.png)





### 元组

Python 的元组与列表类似，*不同之处在于元组的元素不能修改*

元组使用小括号，列表使用方括号

元组创建很简单，只需要在括号中添加元素，并使用逗号隔开即可



##### 元组创建

###### 小括号()创建

> 如果元组中只有一个元素，  逗号不能省

```py
'''元组的创建方式'''
'''第一种创建方式，使用()'''
t=('Python','world',98)
print(t)
print(type(t))

t2='Python','world',98  #省略了小括号
print(t2)
print(type(t2))

t3=('Python',)  #如果元组中只有一个元素，  逗号不能省
print(t3)
print(type(t3))
```

![image-20230330204039274](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023855.png)



###### 内置函数tuple()创建

```py
'''第二种创建方式，使用内置函数tuple()'''
t1=tuple(('Python','world',98))
print(t1)
print(type(t1))
```

![image-20230330204122862](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023775.png)



##### 将元组设计成不可变序列

> 要将元组设计成不可变序列
>
> - 在多任务环境下，同时操作对象时不需要加锁
> - 因此，在程序中尽量使用不可变序列

注意事项：元组中存储的是对象的引用

- 如果元组中对象本身不可变对象，则不可能引用其他对象
- 如果元组中的对象是可变对象，则可变对象的引用不允许改变，但数据可以改变 

```py
t=(10,[20,30],9)
print(t)
print(type(t))
print(t[0],type(t[0]),id(t[0]))
print(t[1],type(t[1]),id(t[1]))
print(t[2],type(t[2]),id(t[2]))
print("========================================================")

'''尝试将t[1]修改为100'''
print(id(100))
#t[1]=100   #元组是不允许修改元素的
'''由于[20,30]列表，而列表是可变序列，所以可以向列中添加元素，而列表的内存地址不变'''
t[1].append(100)  #可以向列表中添加元素
print(t,id(t[1]))
```

![image-20230330210830343](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023020.png)



##### 修改元组(不允许)

> 元组中的元素值是不允许修改的，但我们可以对元组进行连接组合

```py
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')
 
# 以下修改元组元素操作是非法的。
# tup1[0] = 100
 
# 创建一个新的元组
tup3 = tup1 + tup2
print tup3

#(12, 34.56, 'abc', 'xyz')
```



##### 删除元组(不允许)

> 元组中的元素值是不允许删除的，但我们可以使用del语句来删除整个元组

```py
#!/usr/bin/python
 
tup = ('physics', 'chemistry', 1997, 2000)
 
print tup
del tup
print "After deleting tup : "
print tup

'''
('physics', 'chemistry', 1997, 2000)
After deleting tup :
Traceback (most recent call last):
  File "test.py", line 9, in <module>
    print tup
NameError: name 'tup' is not defined
'''
```



##### 元组的遍历

> 元组是可迭代对象，所以可以使用for..in进行遍历。

```py
'''元组的遍历'''
t=('Python','world',98)
'''第一种获取元组元组的方式，使用索引'''
print(t[0])
print(t[1])
print(t[2])
#print(t[3]) #IndexError: tuple index out of range
'''遍历元组'''
for item in t:
    print(item)
```

![image-20230330211050939](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200023881.png)





##### 元组运算符

> 与字符串一样，元组之间可以使用 + 号和 * 号进行运算。这就意味着他们可以组合和复制，运算后会生成一个新的元组。

| Python 表达式                | 结果                         | 描述         |
| :--------------------------- | :--------------------------- | :----------- |
| len((1, 2, 3))               | 3                            | 计算元素个数 |
| (1, 2, 3) + (4, 5, 6)        | (1, 2, 3, 4, 5, 6)           | 连接         |
| ('Hi!',) * 4                 | ('Hi!', 'Hi!', 'Hi!', 'Hi!') | 复制         |
| 3 in (1, 2, 3)               | True                         | 元素是否存在 |
| for x in (1, 2, 3): print x, | 1 2 3                        | 迭代         |

------



##### 元组索引，截取

> 因为元组也是一个序列，所以我们可以访问元组中的指定位置的元素，也可以截取索引中的一段元素，如下所示：

元组：

```
L = ('spam', 'Spam', 'SPAM!')
```

| Python 表达式 | 结果              | 描述                         |
| :------------ | :---------------- | :--------------------------- |
| L[2]          | 'SPAM!'           | 读取第三个元素               |
| L[-2]         | 'Spam'            | 反向读取，读取倒数第二个元素 |
| L[1:]         | ('Spam', 'SPAM!') | 截取元素                     |



##### 元组内置函数

Python元组包含了以下内置函数

| 序号 | 方法及描述                                                   |
| :--- | :----------------------------------------------------------- |
| 1    | [cmp(tuple1, tuple2)](https://www.runoob.com/python/att-tuple-cmp.html) 比较两个元组元素。 |
| 2    | [len(tuple)](https://www.runoob.com/python/att-tuple-len.html) 计算元组元素个数。 |
| 3    | [max(tuple)](https://www.runoob.com/python/att-tuple-max.html) 返回元组中元素最大值。 |
| 4    | [min(tuple)](https://www.runoob.com/python/att-tuple-min.html) 返回元组中元素最小值。 |
| 5    | [tuple(seq)](https://www.runoob.com/python/att-tuple-tuple.html) 将列表转换为元组。 |



### 函数



#### 函数的创建和调用

> 函数的作用：
>
> - 复用代码
> - 提高可维护性
> - 提高可读性便于调试

```py
def	函数名([输入参数])
	函数体
	[return	xxx]
```



#### 参数传递

形式参数、位置实参、关键字实参

**def calc(a,b):  #a,b称为形式参数，简称形参**

**result=calc(10,20)  #10,20称为实际参数的值,简称实参**

**res=calc(b=10,a=20)   #  =左侧的变量的名称称为  关键字参数**

```py
def calc(a,b):  #a,b称为形式参数，简称形参,形参的位置是在函数的定义处
    c=a+b
    return c

result=calc(10,20)  #10,20称为实际参数的值,简称实参，实参的位置是函数的调用处
print(result)    #30

res=calc(b=10,a=20)   #  =左侧的变量的名称称为  关键字参数
print(res)   #30
```



#### 位置实参

> 在函数调用时，使用***(*lst)***将列表中的每个元素都转换为位置实参传入

```py
def fun(a,b,c): #a,b,c在函数的定义处，所以是形式参数
    print('a=',a)
    print('b=',b)
    print('c=',c)

#函数的调用
fun(10,20,30) #函数调用时的参数传递，称为位置传参

lst=[11,22,33]
fun(*lst)  #在函数调用时，将列表中的每个元素都转换为位置实参传入
```

![image-20230403180752874](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024765.png)



#### 关键字实参

> 在函数调用时，*(**dic)*将字典中的键值对都转换为关键字实参传入

```python
def fun(a,b,c): #a,b,c在函数的定义处，所以是形式参数
    print('a=',a)
    print('b=',b)
    print('c=',c)


fun(a=100,c=300,b=200) #函数的调用，所以是关键字实参
dic={'a':111,'b':222,'c':333}
fun(**dic)  #在函数调用时，将字典中的键值对都转换为关键字实参传入
```

![image-20230403181435209](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024439.png)







#### 函数参数传递的内存分析

> 在函数调用过程中，进行参数的传递
>
> 不可变对象：在函数体的修改不会影响实参的值 arg1的修改为100，不会影响n1的值
>
> 可变对象：在函数体的的修改会影响到实参的值  arg2的修改，append(10)，会影响到n2的值

```py
def fun(arg1,arg2):
    print('arg1',arg1)   #arg1 11
    print('arg2',arg2)   #arg2 [22, 33, 44]
    arg1=100
    arg2.append(10)
    print('arg1',arg1)   #arg1 100
    print('arg2',arg2)    #arg2 [22, 33, 44, 10]
    #return


n1=11
n2=[22,33,44]
print('n1',n1)      #n1 11
print('n2',n2)      #n2 [22, 33, 44]

fun(n1,n2)     #将位置传参  ,arg1,arg2，是函数定义处的形参，n1,n2是函数调用的处的实参 ，总结，实参名称与形参名称可以不一致

print("========最终=========")
print('n1',n1)     #n1 11
print('n2',n2)    #n2 [22, 33, 44, 10]
```

![image-20230403145802918](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024029.png)



#### 函数的返回值

> -  如果函数没有返回值【函数执行完毕之后，*不需要给调用处提供数据,return可以省略不写*
> - 函数的返回值，如果是1个，直接返回类型 
> - *函数的返回值，如果是多个，返回的结果为元组*

```py
print(bool(0))  #False
print(bool(8)) #非0的布尔值为True
```



```py
def fun(num):
    odd=[] #存奇数
    even=[] #存偶数
    for i in num:
        if i%2:
            odd.append(i)
        else:
            even.append(i)
    return odd,even

#函数的调用
lst=[10,29,34,23,44,53,55]
print(fun(lst))      #([29, 23, 53, 55], [10, 34, 44])
```



```py
def fun1():
    print('hello')    #hello
    #return

fun1()

def fun2():
    return 'hello'

res=fun2()
print(res)         #hello

def fun3():
    return 'hello','world'
print(fun3())     #('hello', 'world')
```



#### 默认值参数

*不给参数使用默认值，给参数替代默认值*

b称为默认值参数

```py
def fun(a,b=10):   #b称为默认值参数
    print(a,b)

#函数的调用
fun(100)   #100 10
fun(20,30) #20 30
```



#### 个数可变的位置参数

> - 定义函数时，可能无法事先确定传递的位置实参的个数时，使用可变的位置参数
> - 使用*****定义个数可变的位置形参
> - *结果为一个元组*
> - 个数可变的位置参数，只能是1个 

```py
def fun(*args):  #函数定义时的 可变的位置参数
    print(args)
    #print(args[0])

fun(10)
fun(10,30)
fun(30,405,50)
```

![image-20230403172227336](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024175.png)





#### 个数可变的关键字形参

> - 定义函数时，无法事先确定传递的关键字实参的个数时，使用可变的关键字形参
> - 使用******定义个数可变的关键字形参
> - *结果为一个字典*
> - 个数可变的关键字参数，只能是1个 

```py
def fun1(**args):
    print(args)

fun1(a=10)
fun1(a=20,b=30,c=40)

print('hello','world','java')
```

![image-20230403174437728](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024222.png)



> 从*之后的参数，在函数调用时，**只能采用关键字参数传递**

```py
def fun4(a,b,*,c,d):   #从*之后的参数，在函数调用时，只能采用关键字参数传递
    print('a=',a)
    print('b=', b)
    print('c=', c)
    print('d=', d)

#调用fun4函数
#fun4(10,20,30,40)  #位置实参传递
fun4(a=10,b=20,c=30,d=40) #关键字实参传递

print("============================")

def fun8(a,b,*,c,d):   #从*之后的参数，在函数调用时，只能采用关键字参数传递
    print('a=',a)
    print('b=', b)
    print('c=', c)
    print('d=', d)


fun8(10,20,c=30,d=40)  #前两个参数，采用的是位置实参传递，而c,d采用的是关键字实参传递
```

![image-20230403182916175](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024594.png)



> ​		在一个函数的定义过程中，既有个数可变的关键字形参，也有个数可变的位置形参，要求，*个数可变的位置形参，放在个数可变的关键字形参之前*

```py
def fun2(*args1,**args2):
    pass
'''
    def fun2(*args,*a):   
    pass   
    以上代码，程序会报错，个数可变的位置参数，只能是1个 
    def fun2(**args,**args):
    pass
 以上代码，程序会报错，个数可变的关键字参数，只能是1个 
 '''
```

```py
'''函数定义时的形参的顺序问题'''
def fun5(a,b,*,c,d,**args):
    pass

def fun6(*args,**args2):
    pass

def fun7(a,b=10,*args,**args2):
    pass
```



#### 变量的作用域

程序代码能访问该变量的区域

> 根据变量的有效范围可分为
>
> - 局部变量
>
> 在函数内定义并使用的变量，只有函数内部有效。
>
> 局部变量<u>使用global声明，这个变量就是全局全局变量</u>
>
> - 全局变量
>
> 函数体外定义的变量，可以作用于函数内部

```py
def fun(a,b):
    c=a+b    #c,就称为局部变量，因为c在是函数体内进行定义的变量,a,b为函数的形参，作用范围也是函数内部，相当于局部变量
    print(c)
```

```py
name='杨老师'   #name的作用范围为函数内部和外部都可以使用 -->称为全局变量
print(name)  #杨老师
def fun2():
    print(name)   
#调用函数
fun2()   #杨老师
```

```py
def fun3():
    global  age   #函数内部定义的变量，局部变量，局部变量使用global声明，这个变量实际上就变成了全局变量
    age=20
    print(age)   
fun3()    #20
print(age)  #20
```



#### 递归函数

在一个函数的函数体内调用了该函数本身，这个函数就是递归函数



递归的组成部分

> 递归调用与递归终止条件



递归的调用过程

> 每次递归调用一次函数，都会在栈内存分配一个栈帧
>
> 每次执行完一次函数，都会释放相应的空间



> 缺点：占用内存多，效率低
>
> 优点：思路和代码简单

```py
def fac(n):
    if n==1:
        return 1
    else:
        res=n*fac(n-1)
        return  res

print(fac(3))
#3*2*1=6
```



### 异常

#### python标准异常

| 异常名称                  | 描述                                               |
| :------------------------ | :------------------------------------------------- |
|                           |                                                    |
| BaseException             | 所有异常的基类                                     |
| SystemExit                | 解释器请求退出                                     |
| KeyboardInterrupt         | 用户中断执行(通常是输入^C)                         |
| Exception                 | 常规错误的基类                                     |
| StopIteration             | 迭代器没有更多的值                                 |
| GeneratorExit             | 生成器(generator)发生异常来通知退出                |
| StandardError             | 所有的内建标准异常的基类                           |
| ArithmeticError           | 所有数值计算错误的基类                             |
| FloatingPointError        | 浮点计算错误                                       |
| OverflowError             | 数值运算超出最大限制                               |
| ZeroDivisionError         | 除(或取模)零 (所有数据类型)                        |
| AssertionError            | 断言语句失败                                       |
| AttributeError            | 对象没有这个属性                                   |
| EOFError                  | 没有内建输入,到达EOF 标记                          |
| EnvironmentError          | 操作系统错误的基类                                 |
| IOError                   | 输入/输出操作失败                                  |
| OSError                   | 操作系统错误                                       |
| WindowsError              | 系统调用失败                                       |
| ImportError               | 导入模块/对象失败                                  |
| LookupError               | 无效数据查询的基类                                 |
| IndexError                | 序列中没有此索引(index)                            |
| KeyError                  | 映射中没有这个键                                   |
| MemoryError               | 内存溢出错误(对于Python 解释器不是致命的)          |
| NameError                 | 未声明/初始化对象 (没有属性)                       |
| UnboundLocalError         | 访问未初始化的本地变量                             |
| ReferenceError            | 弱引用(Weak reference)试图访问已经垃圾回收了的对象 |
| RuntimeError              | 一般的运行时错误                                   |
| NotImplementedError       | 尚未实现的方法                                     |
| SyntaxError               | Python 语法错误                                    |
| IndentationError          | 缩进错误                                           |
| TabError                  | Tab 和空格混用                                     |
| SystemError               | 一般的解释器系统错误                               |
| TypeError                 | 对类型无效的操作                                   |
| ValueError                | 传入无效的参数                                     |
| UnicodeError              | Unicode 相关的错误                                 |
| UnicodeDecodeError        | Unicode 解码时的错误                               |
| UnicodeEncodeError        | Unicode 编码时错误                                 |
| UnicodeTranslateError     | Unicode 转换时错误                                 |
| Warning                   | 警告的基类                                         |
| DeprecationWarning        | 关于被弃用的特征的警告                             |
| FutureWarning             | 关于构造将来语义会有改变的警告                     |
| OverflowWarning           | 旧的关于自动提升为长整型(long)的警告               |
| PendingDeprecationWarning | 关于特性将会被废弃的警告                           |
| RuntimeWarning            | 可疑的运行时行为(runtime behavior)的警告           |
| SyntaxWarning             | 可疑的语法的警告                                   |
| UserWarning               | 用户代码生成的警告                                 |



#### 捕捉异常

##### try/except语句

> try/except语句用来检测try语句块中的错误，从而让except语句捕获异常信息并处理。
>
> 如果你不想在异常发生时结束你的程序，只需在try里捕获它。

语法：

以下为简单的*try....except...else*的语法：

```py
try:
<语句>        #运行别的代码
except <名字>：
<语句>        #如果在try部份引发了'name'异常
except <名字>，<数据>:
<语句>        #如果引发了'name'异常，获得附加的数据
else:
<语句>        #如果没有异常发生
```

<img src="https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024090.com%2526app%253D2002%2526size%253Df9999%252C10000%2526q%253Da80%2526n%253D0%2526g%253D0n%2526fmt%253Dauto" alt="img" style="zoom:150%;" />



```py
try:
    a=int(input('请输入第一个整数'))
    b=int(input('请输入第二个整数'))
    result=a/b
    print('结果为:',result)
except ZeroDivisionError:
    print('对不起，除数不允许为0')
except ValueError:
    print('只能输入数字串')
print('程序结束')
```

![image-20230403210143347](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024547.png)



```python
try:
    a = int(input('请输入第一个整数'))
    b = int(input('请输入第二个整数'))
    result = a / b
except BaseException as e:
    print('出错了',e)
else:
    print('计算结果为:',result)
finally:
    print('谢谢您的使用')
```

![image-20230403210717475](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024125.png)



### 对象

#### 类与对象

使用 class 语句来创建一个新类，class 之后为类的名称并以冒号结尾:

```py
class ClassName:
   '类的帮助信息'   #类文档字符串
   class_suite  #类体
```



```py
class Student:  #Student为类的名称（类名）由一个或多个单词组成，每个单词的首字母大写，其余小写
    pass

#Python中一切皆对象Student是对象吗？内存有开空间吗？
print(id(Student)) #2926222013040
print(type(Student)) #<class 'type'>
print(Student) #<class '__main__.Student'>
```



#### 类的创建

> 类的组成
>
> - 类属性
> - 实列方法
> - 静态方法
> - 类方法



> *Student为类的名称*（类名）由一个或多个单词组成，每个单词的首字母大写，其余小写
> native_pace='中国'  #直接写在类里的变量，称为*类属性*
>
> 在*类之外定义的称为函数，在类之内定义的称为方法*

```py
class Student:  #Student为类的名称（类名）由一个或多个单词组成，每个单词的首字母大写，其余小写
   native_pace='中国'  #直接写在类里的变量，称为类属性
   def __init__(self,name,age):
       self.name=name    #self.name 称为实体属性  ，进行了 一个赋值的操作，将局部变量的name的值赋给实体属性
       self.age=age

   #实例方法
   def eat(self):
       print('学生在吃饭...')

    #静态方法
   @staticmethod
   def method():
       print('我使用了statticmethod进行修饰，所以我是静态方法')

    #类方法
   @classmethod
   def cm(cls):
       print('我是类方法，因为我使用了classmethod进行修饰')

#在类之外定义的称为函数，在类之内定义的称为方法
def drink():
    print('喝水')
```



对象的创建

对象的创建（类的实列化）

> ***实列名=类名()***



```py
#创建Student类的对象
stu1=Student('张三',20)

print(id(stu1))
print(type(stu1))
print(stu1)
print('---------------------')

print(id(Student))  #Student是类的名称
print(type(Student))
print(Student)
```

![image-20230403223938954](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200024308.png)



```py
#创建Student类的对象
stu1=Student('张三',20)


stu1.eat()            #对象名.方法名()

print(stu1.name)
print(stu1.age)

print('------------------------')

Student.eat(stu1)     #stu1.eat()、Student.eat(stu1)都是调用Student中的eat方法
                      #类名.方法名(类的对象)-->实际上就是方法定义处的self
```

![image-20230403224324583](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200025242.png)



#### 类属性、类方法、静态方法

> - 类中方法外的变量称为类属性，被该类的所有对象所共享
> - 类方法：使用@classmethod修饰的方法，使用类名直接访问的方法
> - 静态方法：使用@staticmethod修饰的主法，使用类名直接访问的方法

```py
#类属性的使用方式
#print(Student.native_pace)
stu1=Student('张三',20)
stu2=Student('李四',30)

print(stu1.native_pace)
print(stu2.native_pace)
print('----------------------------------------')

Student.native_pace='美国'
print(stu1.native_pace)
print(stu2.native_pace)

print('---------类方法的使用方式------------------')
Student.cm()
print(stu1.cm())

print('---------静态方法的使用方式------------------')
Student.method()
print(stu2.method())

```

![image-20230403232117911](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200025904.png)



#### 动态绑定属性和方法

> python是动态语言，在创建对象之后，可以动态绑定属性和方法
>
> 动态绑定的属性和方法只对当前对象起作用，剩下其他对象均不起作用

```py
class Student:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def eat(self):
        print(self.name+'在吃饭')

stu1=Student('张三',20)
stu2=Student('李四',30)
print(id(stu1))
print(id(stu2))

print('------------为stu2动态绑定性别属性---------------------------')
stu1.gender='女'
#print(stu1.name,stu1.age,stu1.gender)
print(stu1.name,stu1.age,stu1.gender)
print(stu2.name,stu2.age)

print('--------------------------')
stu1.eat()
stu2.eat()

def show():
    print('定义在类之外的，称函数')
stu1.show=show
stu1.show()

#stu2.show()  #因为stu2并没有绑定show方法
```

![image-20230404001158692](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200025216.png)



#### 封装

提高程序安全性

> - 将数据（属性）和行为（方法）包装到类对象中。在方法内部对属性进行类对象的外部调用方法。这样无需关心方法内部的具体实现细节，从而隔离了复杂度。
> - 在python中没有专门的修饰符用于属性的私有，如果该*属性不希望在类对象外部被访问，前面使用两个“_”*
> - 在类的外部可以通过  _Student__age 进行访问

```py
class Student:
    def __init__(self,name,age):
        self.name=name
        self.__age=age   #年龄不希望在类的外部被使用，所以加了两个_
    def show(self):
        print(self.name,self.__age)

stu=Student('张三',20)    #张三 20
stu.show()
#在类的外使用使用name与age
print(stu.name)   #张三

#print(stu.__age)   
#print(dir(stu))
print(stu._Student__age)  #在类的外部可以通过  _Student__age 进行访问   #20
```



#### object类

> - object类是所有类的父类，因此所有类都有object类的属性和方法
> - 内置函数*dir()可以查看指定对象所有属性*
> - object有一个***_str()_***方法，用于*返回一个对于“对象的描述”*，对应于内置函数str()经常用于print()方法，帮助我们查看对象信息，所以我们经常使用***str()***进行重写

```py
class Student:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def __str__(self):
        return '我的名字是{0},今年{1}岁'.format(self.name,self.age)

stu=Student('张三',20)
print(dir(stu))  #['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__'
print(stu)  #默会调用__str__()这样的方法     #我的名字是张三,今年20岁
print(type(stu))  #<class '__main__.Student'>
 
```

![image-20230404190123198](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200025548.png)





#### 继承

提高复用性

> 如果一个类没有继承任何类，则默认继承object
>
> python支持多继承
>
> 定义子类时，必须在其构造函数中调用父类的构造函数



```py
class Person(object): #Person继承object类
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def info(self):
        print(self.name,self.age)

class Student(Person):
    def __init__(self,name,age,stu_no):
        super().__init__(name,age)
        self.stu_no=stu_no


class Teacher(Person):
    def __init__(self,name,age,teachofyear):
        super().__init__(name,age)
        self.teachofyear=teachofyear


stu=Student('张三',20,'1001')
teacher=Teacher('李四',34,10)

stu.info()   	#张三 20
teacher.info()   #李四 34
```



子类继承多个父类

```py
class A(object):
    pass

class B(object):
    pass

class C(A,B):
    pass
```



#### 方法重写

> - 如果子类对继承父类的某个属性或方法不满意，可以在子类中对其（方法体）进行重新编写
> - 子类重写后的方法中可以通过***super().xxx()***调用父类中被重写的方法。



```py
class Person(object): #Person继承object类
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def info(self):
        print(self.name,self.age)

class Student(Person):
    def __init__(self,name,age,stu_no):
        super().__init__(name,age)
        self.stu_no=stu_no

#方法重写
    def info(self):
        super().info()   #先去执行父类的输出
        print('学号',self.stu_no)  #再执行输出



class Teacher(Person):
    def __init__(self,name,age,teachofyear):
        super().__init__(name,age)
        self.teachofyear=teachofyear

#方法重写
    def info(self):
        super().info()     #先去执行父类的输出
        print('教龄',self.teachofyear)  #再执行输出



stu=Student('张三',20,'1001')
teacher=Teacher('李四',34,10)

stu.info()
print('----------------------')
teacher.info()
```

![image-20230404183943452](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200025339.png)





#### 多态

提高程序可拓展性

> 多态就是具备多种形态
>
> 多态指的是：即便不知道一个变量所引用的对象到底是什么类型，仍然可以通过这个变量调用方法，在运行中根据变量所引用对象的类型，动态调用哪个对象中的方法。

![167931eeb5464371fe0d5cdfd8e7a18](https://raw.githubusercontent.com/lrv618/python_foundation/main/images/202304200025960.png)



```py
class Animal(object):
    def eat(self):
        print('动物会吃')
class Dog(Animal):
    def eat(self):
        print('狗吃骨头...')
class Cat(Animal):
    def eat(self):
        print('猫吃鱼...')


class Person:
    def eat(self):
        print('人吃五谷杂粮')


#定义一个函数
def fun(obj):
    obj.eat()

#开始调用函数
fun(Cat())
fun(Dog())
fun(Animal())
print('----------------------')
fun(Person())
```



#### 特殊的属性

**__dict__: 获得类对象或实例对象所绑定的所有属性或方法的字典**



**__class__: 获得实例对象所属的类**

**__bases__: 获得类对象的父类元组**

**__mro__:获得类的层次结构**





#### 特殊方法









### 模块

> - Python 模块(Module)，是一个 Python 文件，以 .py 结尾，包含了 Python 对象定义和Python语句。
> - 模块让你能够有逻辑地组织你的 Python 代码段。
> - 把相关的代码分配到一个模块里能让你的代码更好用，更易懂。
> - 模块能定义函数，类和变量，模块里也能包含可执行的代码。



```py
def fun():
    pass
def fun2():
    pass

class Student:
    native_place='吉林'  #类属性
    def eat(self,name,age):
        self.name=name
        self.age=age
    @classmethod
    def cm(cls):
        pass
    @staticmethod
    def sm():
        pass



a=10
b=20
print(a+b)
```



#### 导入模块

> - **import 模块名称  [as 别名]**
> - **from 模块名称 import 函数/变量/类**

```py
import math  #关于数学运算
print(id(math))
print(type(math))
print(math)
print(math.pi)
print('----------------------------------------')
print(dir(math))
print(math.pow(2,3),type(math.pow(2,3)))
print(math.ceil(9.001))
print(math.floor(9.9999))
```

```py
from  math import  pi
from math import  pow
print(pi) 			#3.141592653589793
print(pow(2,3))  	#8.0
#print(math.pow(2,3))
```



第一个文件写模块

```py
def add(a,b):
    return a+b
def div(a,b):
    return a/b

#如何导入自定义模块
```



第二个文件导入模块

```py
#在demo5中导入calc自定义模块使用
import calc
print(calc.add(10,20))
print(calc.div(10,4))
```



#### 以主程序方式运行

​		每个模块的定义中都包括一个记录模块名称的变量_name_,程序可以检查该变量，以确定它们哪个模块执行。如果一个模块不是被导入到其他程序中执行，那么它可能在解析器的顶级模式执行，顶级模式的_name_变量的值为main

```py
def add(a,b):
    return a+b


if __name__ == '__main__':
    print(add(10,20))    #只有当点击运行calc2时，才会执行运算
```



#### 包导入

> 包和目录的区别
>
> - 包含—init—.py文件的目录称为包
> - 目录里通常不包含—init—.py文件

```py
#导入带有包的模块时注意事项
import pageage1
import  calc
#使用import方式进行导入时，只能跟包名或模块名

from pageage1 import  module_A
from pageage1.module_A import  a
#使用from ...import可以导入包，模块，函数，变量.
```



