## 第二章

### 01-字面量

### 02-注释

### 03-变量

### 04-数据类型

### 05-数据类型转换

1.任何类型都可以通过str()，转换成字符串

2.字符串必须是真的数字，才可以将字符串转化为数字

浮点数转整数会丢失精度

### 06-标识符

标识符命名规则：

- 内容限定：只允许出现英文、中文、数字、下划线（_），其余皆不被允许；数字不可开头。
- 大小写敏感
- 不可使用关键字：同样大小写敏感。

变量命名规范：

- 见明知意
- 英文字母全小写
- 下划线命名法：多个单词组合变量名，要用下划线做分隔。

### 07-运算符

### 08-字符串三种定义

### 09-字符串的拼接

字符串无法和非字符串变量进行拼接

### 10-字符串格式化

例1：

~~~python
name ="传智播客":
set_up_year = 2006
stock_price = 19.99
message ="我是: %s，我成立于: %d，我今天的股价是: %f" % (name, set_up_year, stock_price)
print(message)
~~~

### 11-字符串格式化的精度控制

m . n：m控制宽度，要求是数字（很少使用），设置的宽度小于数字自身，不生效；n控制小数点精度，要求是数字，会进行小数的四舍五入。

### 12-字符串格式化2

~~~python
"""
字符串格式化的方式：f"{占位}"
"""
name = "传智播客"
set_up_year = 2006
stock_price = 19.99
# f: format
print(f"我是{name}，我成立于：{set_up_year}年，我今天的股价是：{stock_price}")
~~~

### 13-对表达式进行格式化

~~~python
"""
对表达式进行字符串格式化
"""
print("1 * 1 的结果是：%d" % (1 * 1))
print(f"1 * 2的结果是：{1 * 2}")
print("字符串在Python中的类型名是：%s" % type("字符串"))
~~~

### 14-字符串格式化练习题

股价计算小程序

定义如下变量：

- name，公司名
- stock_price，当前股价
- stock_code，股票代码
- stock_price_daily_growth_factor，股票每日增长系数，浮点数类型
- growth_days，增长天数

计算，经过growth_days天的增长后，股票达到了多少钱？

使用字符串格式化进行输出，若为浮点数，要求小数点精度2位数。

~~~python
# 定义需要的变量
name = "传智播客"
stock_price = 19.99
stock_code = "003032"
# 股票 价格 每日 增长 因子
stock_price_daily_growth_factor = 1.2
growth_days = 7

finally_stock_price = stock_price * stock_price_daily_growth_factor ** growth_days

print(f"公司：{name}，股票代码：{stock_code}，当前股价：{stock_price}")
print("每日增长系数: %.1f，经过%d天的增长后，股价达到了：%.2f" % (stock_price_daily_growth_factor, growth_days, finally_stock_price))
~~~

### 15-数据输入（input语句）

~~~python
name = input("请告诉我你是谁？")
print("我知道了，你是:%s" % name)

# 输入数字类型
num = input("请告诉我你的银行卡密码：")
# 数据类型转换
num = int(num)
print("你的银行卡密码的类型是：", type(num))

name = """黑马程序员"""
~~~

无论键盘输入什么类型的数据，获取到的数据**永远都是字符串类型**

## 第三章

### 01-布尔类型与比较运算符

~~~python
# 定义变量存储布尔类型的数据
bool_1 = True
bool_2 = False
print(f"bool_1变量的内容是：{bool_1}, 类型是：{type(bool_1)}")
print(f"bool_2变量的内容是：{bool_2}, 类型是：{type(bool_2)}")
# 比较运算符的使用
# == , !=, >, <, >=, <=
# 演示进行内容的相等比较
num1 = 10
num2 = 10
print(f"10 == 10的结果是：{num1 == num2}")

num1 = 10
num2 = 15
print(f"10 != 15的结果是：{num1 != num2}")

name1 = "itcast"
name2 = "itheima"
print(f"itcast == itheima 结果是：{name1 == name2}")

# 演示大于小于，大于等于小于等于的比较运算
num1 = 10
num2 = 5
print(f"10 > 5结果是：{num1 > num2}")
print(f"10 < 5的结果是：{num1 < num2}")

num1 = 10
num2 = 11
print(f"10 >= 11的结果是：{num1 >= num2}")
print(f"10 <= 11的结果是：{num1 <= num2}")
~~~

### 02-if语句的基本格式

### 03-案例：成年人判断

1.通过input语句，获取键盘输入，为变量age赋值。（注意转换成数字类型）

2.通过if判断是否是成年人，满足条件则输出提示信息，如下：

~~~
欢迎来到黑马儿童游乐场，儿童免费，成人收费。
请输入你的年龄：30
您已成年，游玩需要补票10元。
祝您游玩愉快。
~~~
提示：您已成年，需要补票的信息输出来自if断

~~~python
# 获取键盘输入
age = int(input("请输入你的年龄："))

# 通过if判断是否是成年人
if age >= 18:
    print("您已成年，游玩需要买票，10元.")

print("祝您游玩愉快")
~~~

### 04-if else组合判断语句

### 05-案例：我要买票吗？

通过input语句获取键盘输入的身高。

判断身高是否超过120cm，并通过print给出提示信息。

~~~
欢迎来到黑马动物园。
请输入你的身高（cm）：130
您的身高超出120cm，游玩需要够票10元。
祝您游玩愉快。
~~~

~~~
欢迎来到黑马动物园。
请输入你的身高（cm）：111
您的身高未超出120cm，可以免费游玩。
祝您游玩愉快。
~~~

~~~python
# 定义键盘输入获取身高数据
height = int(input("请输入你的身高（cm）："))

# 通过if进行判断
if height > 120:
    print("您的身高超出120CM，需要买票，10元。")
else:
    print("您的身高低于120CM，可以免费游玩。")

print("祝您游玩愉快")

~~~

### 06-if elif else语句

### 07-案例：猜猜心里数字

1.定义一个变量，数字类型，内容随意。
2.基于input语句输入猜想的数字，通过if和多次elif的组合;判断猜想数字是否和心里数字一致。

~~~
请输入第一次猜想的数字：1
不对，再猜一次：2
不对，再猜最后一次：3
Sorry，全部猜错啦，我想的是：10
~~~

~~~python
# 定义一个变量数字
num = 5

# 通过键盘输入获取猜想的数字，通过多次if 和 elif的组合进行猜想比较
if int(input("请猜一个数字：")) == num:
    print("恭喜第一次就猜对了呢")
elif int(input("猜错了，再猜一次：")) == num:
    print("猜对了")
elif int(input("猜错了，再猜一次：")) == num:
    print("恭喜，最后一次机会，你猜对了")
else:
    print("Sorry 猜错了")
~~~

### 08-判断语句的嵌套

### 09-判断语句综合案例

定义一个数字（1~10，随机产生），通过3次判断来猜出来数字。

1.数字随机产生，范围1~10。

2.有3次机会猜测数字，通过3层嵌套判断实现。

3.每次猜不中，会提示大了小了。

~~~python
# 1. 构建一个随机的数字变量
import random
num = random.randint(1, 10)

guess_num = int(input("输入你要猜测的数字："))

# 2. 通过if判断语句进行数字的猜测
if guess_num == num:
    print("恭喜，第一次就猜中了")
else:
    if guess_num > num:
        print("你猜测的数字大了")
    else:
        print("你猜测的数字小了")

    guess_num = int(input("再次输入你要猜测的数字："))

    if guess_num == num:
        print("恭喜，第二次猜中了")
    else:
        if guess_num > num:
            print("你猜测的数字大了")
        else:
            print("你猜测的数字小了")

        guess_num = int(input("第三次输入你要猜测的数字："))

        if guess_num == num:
            print("第三次猜中了")
        else:
            print("三次机会用完了，没有猜中。")
~~~

## 第四章

### 01-while循环的基础应用

### 02-案例：求1-100的和

~~~python
sum = 0
i = 1
while i<=100:
    sum += i
    i += 1

print(f"1-100累加的和是：{sum}")
~~~

### 03-案例：while循环猜数字

~~~python
# 获取范围在1-100的随机数字
import random
num = random.randint(1, 100)
# 定义一个变量，记录总共猜测了多少次
count = 0

# 通过一个布尔类型的变量，做循环是否继续的标记
flag = True
while flag:
    guess_num = int(input("请输入你猜测的数字:"))
    count += 1
    if guess_num == num:
        print("猜中了")
        # 设置为False就是终止循环的条件
        flag = False
    else:
        if guess_num > num:
            print("你猜的大了")
        else:
            print("你猜的小了")

print(f"你总共猜测了{count}次")
~~~

### 04-while循环嵌套应用

### 05-案例：while循环九九乘法表

~~~python
# 定义外层循环的控制变量
i = 1
while i <= 9:

    # 定义内层循环的控制变量
    j = 1
    while j <= i:
        # 内层循环的print语句，不要换行，通过\t制表符进行对齐
        print(f"{j} * {i} = {j * i}\t", end='')
        j += 1

    i += 1
    print()     # print空内容，就是输出一个换行
~~~

### 06-for循环基础语法

~~~python
name = "itheima"

for x in name:
    # 将name的内容，挨个取出赋予x临时变量
    # 就可以在循环体内对x进行处理
    print(x)
~~~

### 07-案例：for循环数一数有几个a

~~~python
# 统计如下字符串中，有多少个字母a
name = "itheima is a brand of itcast"

# 定义一个变量，用来统计有多少个a
count = 0

# for 循环统计
# for 临时变量 in 被统计的数据:
for x in name:
    if x == "a":
        count += 1

print(f"被统计的字符串中有{count}个a")
~~~

### 08-range语句

~~~python
# range语法1 range(num)
# for x in range(10):
#     print(x)

# range 语法2 range(num1, num2)
# for x in range(5, 10):
#     # 从5开始，到10结束（不包含10本身）的一个数字序列，数字之间间隔是1
#     print(x)

# range 语法3 range(num1, num2, step)
# for x in range(5, 10, 2):
#     # 从5开始，到10结束（不包含10本身）的一个数字序列，数字之间的间隔是2
#     print(x)

for x in range(10):
    print("送玫瑰花")
~~~

### 09-for循环临时变量作用域

在for循环外部访问临时变量：

- 实际上是可以访问到的；

- 在编程规范上，是不允许、不建议这么做的。

### 10-for循环嵌套使用

### 11-案例：for循环九九乘法表

~~~python
# 通过外层循环控制行数
for i in range(1, 10):
    # 通过内层循环控制每一行的数据
    for j in range(1, i + 1):
        # 在内层循环中输出每一行的内容
        print(f"{j} * {i} = {j * i}\t", end='')

    # 外层循环可以通过print输出一个回车符
    print()
~~~

### 12-continue和break

### 13-综合案例：发工资

某公司，账户余额有1W元，给20名员工发工资。

- 员工编号从1到20，从编号1开始，依次领取工资，每人可领取1000元。

- 领工资时，财务判断员工的绩效分（1-10）（随机生成），如果低于5，不发工资，换下一位。

- 如果工资发完了，结束发工资。

提示：

- continue用于跳过员工，break直接结束发工资。

- if判断余额，不要忘记发完工资后，余额减少1000哦。

~~~python
money=1000
for i in range(1, 21):
    import random
    score = random.randint(1, 10)
    if score < 5:
        print(f"员工{i}，绩效分{score}，低于5，不发工资，下一位。")
        continue
    else:
        money -= 1000
        print(f"向员工{i}发放工资1000元，账户余额还剩余{money}元")
        if money == 0:
            print("工资发完了，下个月领取吧。")
            break
~~~

## 第五章

### 01-函数的初体验

### 02-函数的基础定义语法

参数如不需要，可以省略。

返回值如不需要，可以省略。

函数必须先定义后使用。

~~~python
# 定义一个函数，输出相关信息
def say_hi():
    print("Hi 我是黑马程序员，学Python来黑马")

# 调用函数，让定义的函数开始工作
say_hi()
~~~

### 03-案例：自动查核酸

~~~python
# 定义函数
def check():
    # 编写函数体输出信息
    print("欢迎来到黑马程序员！\n请出示您的健康码以及72小时核酸证明！")

# 调用函数
check()
~~~

### 04-函数的传入参数

~~~python
# 定义3数相加的函数，通过参数接收被计算的3个数字
def add(x, y, z):
    result = x + y + z
    print(f"{x} + {y} + {z}的计算结果是：{result}")

# 调用函数，传入被计算的2个数字
add(5, 6, 7)
~~~

### 05-案例：升级版自动查核酸

~~~python
# 定义函数，接收1个形式参数，数字类型，表示体温
def check(num):
    # 在函数体内进行判断体温
    print("欢迎来到黑马程序员！请出示您的健康码以及72小时核酸证明，并配合测量体温！")
    if num <= 37.5:
        print(f"体温测量中，您的体温是：{num}度，体温正常请进！")
    else:
        print(f"体温测量中，您的体温是：{num}度，需要隔离！")

# 调用函数，传入实际参数
check(37.6)
~~~

### 06-函数的返回值定义语法

函数体在遇到return后就结束了，写在return后的代码不会执行。

~~~python
# 定义一个函数，完成2数相加功能
def add(a, b):
    result = a + b
    # 通过返回值，将相加的结果返回给调用者
    return result
    # 返回结果后，还想输出一句话
    print("我完事了")

# 函数的返回值，可以通过变量去接收
r = add(5, 6)
print(r)
~~~

### 07-函数返回值之None类型

None：<class 'NoneType'>

无返回值的函数实际上是返回了None这个字面量。

None作为一个特殊的字面量，用于表示：空、无意义，其有非常多的应用场景。

- 用在函数无返回值上

- 用在if判断上

  - **在if判断中，None等同于False**

  - **一般用于在函数中主动返回None，配合if判断做相关处理**

- 用于声明无内容的变量上

  - **定义变量，但暂时不需要变量有具体值，可以用None来代替**

~~~python
# 无return语句的函数返回值
def say_hi():
    print("你好呀")

result = say_hi()
print(f"无返回值函数，返回的内容是：{result}")
print(f"无返回值函数，返回的内容类型是：{type(result)}")

# 主动返回None的函数
def say_hi2():
    print("你好呀")
    return None

result = say_hi2()
print(f"无返回值函数，返回的内容是：{result}")
print(f"无返回值函数，返回的内容类型是：{type(result)}")
# None用于if判断
def check_age(age):
    if age > 18:
        return "SUCCESS"
    else:
        return None

result = check_age(16)
if not result:
    # 进入if表示result是None值 也就是False
    print("未成年，不可以进入")
~~~

### 08-函数的说明文档

~~~python
# 定义函数，进行文档说明
def add(x, y):
    """
    add函数可以接收2个参数，进行2数相加的功能
    :param x: 形参x表示相加的其中一个数字
    :param y: 形参y表示相加的另一个数字
    :return: 返回值是2数相加的结果
    """
    result = x + y
    print(f"2数相加的结果是：{result}")
    return result

add(5, 6)
~~~

### 09-函数的嵌套调用

~~~python
# 定义函数func_b
def func_b():
    print("---2---")
# 定义函数func_a，并在内部调用func_b
def func_a():
    print("---1---")

    # 嵌套调用func_b
    func_b()

    print("---3---")
# 调用函数func_a
func_a()
~~~

### 10-变量在函数中的作用域

变量作用域指的是变量的作用范围（变量在哪里可用，在哪里不可用）。

主要分为两类：**局部变量**和**全局变量**。

所谓局部变量是**定义在函数体内部的变量，即只在函数体内部生效**。

局部变量的作用：在函数体内部，临时保存数据，即当函数调用完成后，则销毁局部变量。

所谓全局变量，指的是**在函数体内、外都能生效的变量**。

若有一个数据，在函数A和函数B中都要使用，该将这个数据存储在一个全局变量里面。

使用 **global关键字** 可以在**函数内部声明变量为全局变量**。

~~~python
# 演示局部变量
# def test_a():
#     num = 100
#     print(num)
#
#
# test_a()
# 出了函数体，局部变量就无法使用了
# print(num)

# 演示全局变量
# num = 200
#
# def test_a():
#     print(f"test_a: {num}")
#
# def test_b():
#     print(f"test_b: {num}")
#
# test_a()
# test_b()
# print(num)

# 在函数内修改全局变量
# num = 200
#
# def test_a():
#     print(f"test_a: {num}")
#
# def test_b():
#     num = 500       # 局部变量
#     print(f"test_b: {num}")
#
# test_a()
# test_b()
# print(num)

# global关键字，在函数内声明变量为全局变量
num = 200

def test_a():
    print(f"test_a: {num}")

def test_b():
    global num      # 设置内部定义的变量为全局变量
    num = 500
    print(f"test_b: {num}")

test_a()
test_b()
print(num)
~~~

### 11-案例：黑马ATM

主菜单效果

~~~
-----------------主菜单-----------------
周杰伦，您好，欢迎来到黑马银行ATM。请选择操作：
查询余额 [输入1]
存款 [输入2]
取款 [输入3]
退出 [输入4]
请输入您的选择：
~~~

查询余额效果

~~~
-----------------查询余额-----------------
周杰伦，您好，您的余额剩余：5000000元
~~~

存、取款效果

~~~
-----------------存款-----------------
周杰伦，您好，您存款50000元成功
周杰伦，您好，您的余额剩余：5050000元
-----------------取款-----------------
周杰伦，您好，您取款50000元成功
周杰伦，您好，您的余额剩余：4950000元
~~~

~~~python
# 定义全局变量money name
money = 5000000
name = None
# 要求客户输入姓名
name = input("请输入您的姓名：")
# 定义查询函数
def query(show_header):
    if show_header:
        print("-------------查询余额------------")
    print(f"{name}，您好，您的余额剩余：{money}元")


# 定义存款函数
def saving(num):
    global money    # money在函数内部定义为全局变量
    money += num
    print("-------------存款------------")
    print(f"{name}，您好，您存款{num}元成功。")

    # 调用query函数查询余额
    query(False)

# 定义取款函数
def get_money(num):
    global money
    money -= num
    print("-------------取款------------")
    print(f"{name}，您好，您取款{num}元成功。")

    # 调用query函数查询余额
    query(False)
# 定义主菜单函数
def main():
    print("-------------主菜单------------")
    print(f"{name}，您好，欢迎来到黑马银行ATM。请选择操作：")
    print("查询余额\t[输入1]")
    print("存款\t\t[输入2]")
    print("取款\t\t[输入3]")    # 通过\t制表符对齐输出
    print("退出\t\t[输入4]")
    return input("请输入您的选择：")

# 设置无限循环，确保程序不退出
while True:
    keyboard_input = main()
    if keyboard_input == "1":
        query(True)
        continue    # 通过continue继续下一次循环，一进来就是回到了主菜单
    elif keyboard_input == "2":
        num = int(input("您想要存多少钱？请输入："))
        saving(num)
        continue
    elif keyboard_input == "3":
        num = int(input("您想要取多少钱？请输入："))
        get_money(num)
        continue
    else:
        print("程序退出啦")
        break       # 通过break退出循环
~~~

## 第六章

### 01-数据容器入门

list（列表）

tuple（元组）

str（字符串）

set（集合）

dict（字典）

### 02-列表的定义语法

基本语法：

~~~python
# 字面量
[元素1, 元素2, 元素3, 元素4, ...]

# 定义变量
变量名称 = [元素1, 元素2, 元素3, 元素4, ...]

# 定义空列表
变量名称 = []
变量名称 = list[]
~~~

列表内的**每一个数据，称之为元素。**

列表可以一次存储多个数据，且**可以为不同的数据类型，支持嵌套。**

~~~python
# 定义一个列表 list
my_list = ["itheima", "itcast", "python"]
print(my_list)
print(type(my_list))

my_list = ["itheima", 666, True]
print(my_list)
print(type(my_list))

# 定义一个嵌套的列表
my_list = [ [1, 2, 3], [4, 5, 6]]
print(my_list)
print(type(my_list))
~~~

### 03-列表的下标索引

~~~python
# 通过下标索引取出对应位置的数据
my_list = ["Tom", "Lily", "Rose"]
# 列表[下标索引], 从前向后从0开始，每次+1，  从后向前从-1开始，每次-1
print(my_list[0])
print(my_list[1])
print(my_list[2])
# 错误示范；通过下标索引取数据，一定不要超出范围
# print(my_list[3])

# 通过下标索引取出数据（倒序取出）
print(my_list[-1])
print(my_list[-2])
print(my_list[-3])


# 取出嵌套列表的元素
my_list = [ [1, 2, 3], [4, 5, 6]]
print(my_list[1][1])
~~~

### 04-列表的常用操作方法

#### 列表的查询功能（方法）

- 查找某元素的下标

  功能：查找指定元素在列表的下标，若找不到，报错ValueError。

  **语法：列表. index(元素)**

  index就是列表对象（变量）内置的方法（函数）。

~~~python
mylist = ["itcast", "itheima", "python"]
# 1.1 查找某元素在列表内的下标索引
index = mylist.index("itheima")
print(f"itheima在列表中的下标索引值是：{index}")
# 1.2如果被查找的元素不存在，会报错
# index = mylist.index("hello")
# print(f"hello在列表中的下标索引值是：{index}")
~~~

#### 列表的修改功能（方法）

- 修改特定位置（索引）的元素值：

  **语法：列表[下标] = 值**

  可以使用如上语法，直接对指定下标（正向、反向下标均可）的值进行：重新赋值（修改）。

~~~python
mylist = ["itcast", "itheima", "python"]
# 2. 修改特定下标索引的值
mylist[0] = "传智教育"
print(f"列表被修改元素值后，结果是：{mylist}")
~~~

- 插入元素：

  **语法：列表. insert(下标, 元素)**，在指定的下标位置，插入指定的元素。

~~~python
mylist = ["itcast", "itheima", "python"]
# 3. 在指定下标位置插入新元素
mylist.insert(1, "best")
print(f"列表插入元素后，结果是：{mylist}")
~~~

- 追加元素：

  **语法：列表. append(元素)**，将指定元素，追加到列表的尾部。

~~~python
mylist = ["itcast", "itheima", "python"]
# 4. 在列表的尾部追加```单个```新元素
mylist.append("黑马程序员")
print(f"列表在追加了元素后，结果是：{mylist}")
~~~

- 追加元素方式2：

  **语法：列表. extend(其他数据容器)**，将其他数据容器的内容取出，依次追加到列表尾部。

~~~python
mylist = ["itcast", "itheima", "python"]
# 5. 在列表的尾部追加```一批```新元素
mylist2 = [1, 2, 3]
mylist.extend(mylist2)
print(f"列表在追加了一个新的列表后，结果是：{mylist}")
~~~

- 删除元素：

  **语法1：del列表{下标}**

  **语法2：列表. pop(下标)**
  
~~~python
mylist = ["itcast", "itheima", "python"]
# 6. 删除指定下标索引的元素（2种方式）
mylist = ["itcast", "itheima", "python"]

# 6.1 方式1：del 列表[下标]
del mylist[2]
print(f"列表删除元素后结果是：{mylist}")
# 6.2 方式2：列表.pop(下标)
mylist = ["itcast", "itheima", "python"]
element = mylist.pop(2)
print(f"通过pop方法取出元素后列表内容：{mylist}, 取出的元素是：{element}")
~~~

- 删除某元素在列表中的第一个匹配项：

  **语法：列表. remove(元素)**

~~~python
# 7. 删除某元素在列表中的第一个匹配项
mylist = ["itcast", "itheima", "itcast", "itheima", "python"]
mylist.remove("itheima")
print(f"通过remove方法移除元素后，列表的结果是：{mylist}")
~~~

- 清空列表内容：

  **语法：列表. clear()**

~~~python
# 8. 清空列表
mylist.clear()
print(f"列表被清空了，结果是：{mylist}")
~~~

- 统计某元素在列表内的数量:

  **语法：列表. count(元素)**

~~~python
# 9. 统计列表内某元素的数量
mylist = ["itcast", "itheima", "itcast", "itheima", "python"]
count = mylist.count("itheima")
print(f"列表中itheima的数量是：{count}")
~~~

- 统计列表内，有多少元素

  **语法：len(列表)**

  可以得到一个int数字，表示列表内的元素数量

~~~python
# 10. 统计列表中全部的元素数量
mylist = ["itcast", "itheima", "itcast", "itheima", "python"]
count = len(mylist)
print(f"列表的元素数量总共有：{count}个")
~~~

#### 总结

| 编号 |         使用方法         |                      作用                      |
| :--: | :----------------------: | :--------------------------------------------: |
|  1   |    列表. append(元素)    |              向列表中追加一个元素              |
|  2   |    列表. extend(容器)    |    将数据容器的内容依次取出，追加到列表尾部    |
|  3   | 列表. insert(下标, 元素) |          在指定下标处，插入指定的元素          |
|  4   |      del 列表[下标]      |              删除列表指定下标元素              |
|  5   |     列表. pop(下标)      |              删除列表指定下标元素              |
|  6   |    列表. remove(元素)    |        从前向后，删除此元素第一个匹配项        |
|  7   |      列表. clear()       |                    清空列表                    |
|  8   |    列表. count(元素)     |          统计此元素在列表中出现的次数          |
|  9   |    列表. index(元素)     | 查找指定元素在列表的下标，找不到报错ValueError |
|  10  |        len(列表)         |              统计容器内有多少元素              |

特点：

- 可以容纳多个元素（上限为2^63-1、9223372036854775807个）
- 可以容纳不同类型的元素（混装）
- 数据是有序存储的（有下标序号）
- 允许重复数据存在
- 可以修改（增加或删除元素等）

### 05-案例：常用功能练习

有一个列表，内容是：[21, 25, 21, 23, 22, 20]，记录的是一批学生的年龄

请通过列表的功能（方法），对其进行：

1. 定义这个列表，并用变量接收它
2. 追加一个数字31，到列表的尾部
3. 追加一个新列表[29, 33, 30]，到列表的尾部
4. 取出第一个元素（应是：21）
5. 取出最后一个元素（应是：30）
6. 查找元素31，在列表中的下标位置

~~~python
# 1. 定义这个列表，并用变量接收它， 内容是：[21, 25, 21, 23, 22, 20]
mylist = [21, 25, 21, 23, 22, 20]

# 2. 追加一个数字31，到列表的尾部
mylist.append(31)

# 3. 追加一个新列表[29, 33, 30]，到列表的尾部
mylist.extend([29, 33, 30])
# 4. 取出第一个元素（应是：21）
num1 = mylist[0]
print(f"从列表中取出来第一个元素，应该是21，实际上是：{num1}")

# 5. 取出最后一个元素（应是：30）
num2 = mylist[-1]
print(f"从列表中取出来最后一个元素，应该是30，实际上是：{num2}")

# 6. 查找元素31，在列表中的下标位置
index = mylist.index(31)
print(f"元素31在列表的下标位置是：{index}")
print(f"最后列表的内容是：{mylist}")
~~~

### 06-列表的循环遍历

#### while循环

~~~python
def list_while_func():
    """
    使用while循环遍历列表的演示函数
    :return: None
    """
    mylist = ["传智教育", "黑马程序员", "Python"]
    # 循环控制变量：通过下标索引来控制，默认是0
    # 每一次循环，将下标索引变量+1
    # 循环条件：下标索引变量 < 列表的元素数量

    # 定义一个变量，用来标记列表的下标
    index = 0       # 初始下标为0
    while index < len(mylist):
        # 通过index变量取出对应下标的元素
        element = mylist[index]
        print(f"列表的元素：{element}")

        # 至关重要：将循环变量（index）每一次循环都+1
        index += 1
~~~~

#### for循环

~~~python
def list_for_func():
    """
    使用for循环遍历列表的演示函数
    :return:
    """
    mylist = [1, 2, 3, 4, 5]
    # for 临时变量 in 数据容器:
    for element in mylist:
        print(f"列表的元素有：{element}")
~~~

#### while循环和for循环的对比

while循环和for循环，都是循环语句，但细节不同：

- 在循环控制上：

1. while循环可以自定循环条件，并自行控制。
2. for循环不可以自定循环条件，只可以一个个从容器内取出数据。

- 在无限循环上：

1. while循环可以通过条件控制做到无限循环。
2. for循环理论上不可以，因为被遍历的容器容量不是无限的。

- 在使用场景上：

1. while循环适用于任何想要循环的场景。
2. for循环适用于，遍历数据容器的场景或简单的固定次数循环场景。

#### 案例：取出列表内的偶数

定义一个列表，内容是：[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

- 遍历列表，取出列表内的偶数，并存入一个新的列表对象中
- 使用while循环和for循环各操作一次

提示：

- 通过if判断来确认偶数
- 通过列表的append方法，来增加元素

~~~python
original_list = [1,2,3,4,5,6,7,8,9,10]
even_list_while = []
i = 0
while i < len(original_list):
    if original_list[i] % 2 == 0:
        even_list_while.append(original_list[i])
    i += 1
print("通过while循环，从列表：", original_list, "中取出偶数，组成新列表：", even_list_while)

even_list_for = []
for num in original_list:
    if num % 2 == 0:
        even_list_for.append(num)
print("通过for循环，从列表：", original_list, "中取出偶数，组成新列表：", even_list_for)
~~~

### 07-元组的定义和操作

#### 定义元组

元组一旦定义完成，就不可修改。

元组定义：定义元组使用**小括号**，且使用**逗号**隔开各个数据，**数据可以是不同的数据类型**。

注意：元组只有一个数据，这个数据后面要添加逗号

元组也支持嵌套。

~~~python
# 定义元组
t1 = (1, "Hello", True)
t2 = ()
t3 = tuple()
print(f"t1的类型是：{type(t1)}, 内容是：{t1}")
print(f"t2的类型是：{type(t2)}, 内容是：{t2}")
print(f"t3的类型是：{type(t3)}, 内容是：{t3}")

# 定义单个元素的元素
t4 = ("hello", )
print(f"t4的类型是：{type(t4)}, t4的内容是：{t4}")

# 元组的嵌套
t5 = ( (1, 2, 3), (4, 5, 6) )
print(f"t5的类型是：{type(t5)}, 内容是：{t5}")

# 下标索引去取出内容
num = t5[1][2]
print(f"从嵌套元组中取出的数据是：{num}")
~~~

#### 元组的相关操作

| 编号 |   方法    |                        作用                        |
| :--: | :-------: | :------------------------------------------------: |
|  1   |  index()  | 查找某个数据，如果数据存在返回对应的下标，否则报错 |
|  2   |  count()  |          统计某个数据在当前元组出现的次数          |
|  3   | len(元组) |                统计元组内的元素个数                |

元组由于不可修改的特性，所以其操作方法非常少。

~~~python
# 元组的操作：index查找方法
t6 = ("传智教育", "黑马程序员", "Python")
index = t6.index("黑马程序员")
print(f"在元组t6中查找黑马程序员，的下标是：{index}")
# 元组的操作：count统计方法
t7 = ("传智教育", "黑马程序员", "黑马程序员", "黑马程序员", "Python")
num = t7.count("黑马程序员")
print(f"在元组t7中统计黑马程序员的数量有：{num}个")
# 元组的操作：len函数统计元组元素数量
t8 = ("传智教育", "黑马程序员", "黑马程序员", "黑马程序员", "Python")
num = len(t8)
print(f"t8元组中的元素有：{num}个")
~~~

注意事项：

- 不可以修改元组的内容，否则会直接报错。
- 可以修改元组内的list的内容（修改元素、增加、删除、反转等）。
- 不可以替换list为其它list或其它类型。

#### 元组的遍历

~~~python
# 元组的遍历：while
index = 0
while index < len(t8):
    print(f"元组的元素有：{t8[index]}")
    # 至关重要
    index += 1

# 元组的遍历：for
for element in t8:
    print(f"2元组的元素有：{element}")
~~~

#### 元组的特点

特点：

- 可以容纳多个数据
- 可以容纳不同类型的数据（混装）
- 数据是有序存储的（下标索引）
- 允许重复数据存在
- **不可以修改**（增加或删除元素等）
- 支持for循环

多数特性和list一致，不同点在于不可修改的特性。

#### 案例：元组的基本操作

定义一个元组，内容是：（'周杰轮', 11, ['football', 'music']），记录的是一个学生的信息（姓名、年龄、爱好）

请通过元组的功能（方法），对其进行：

1. 查询其年龄所在的下标位置
2. 查询学生的姓名
3. 删除学生爱好中的football
4. 增加爱好：coding到爱好list内

~~~python
# 定义一个元组 student，包含学生的信息：姓名、年龄和爱好列表
student = ('周杰伦', 11, ['football', 'music'])

# 查找元素 11（年龄）在元组 student 中的索引位置，并将结果存储在 age 变量中
age = student.index(11)
print(age)

# 获取元组 student 的第一个元素（姓名），并存储在 name 变量中
name = student[0]
print(name)

# 将元组中存储爱好的列表（索引为 2）取出，并将其转换为列表，存储在 hobbies 变量中
hobbies = list(student[2])
# 从 hobbies 列表中移除元素 'football'
hobbies.remove('football')
# 重新构建元组 student，将修改后的爱好列表替换原来的爱好列表，保持姓名和年龄不变
student = (student[0], student[1], hobbies)
print(student)

# 再次将元组中存储爱好的列表（索引为 2）取出，并将其转换为列表，存储在 hobbies 变量中
hobbies = list(student[2])
# 向 hobbies 列表中添加元素 'coding'
hobbies.append('coding')
# 再次重新构建元组 student，将更新后的爱好列表替换原来的爱好列表，保持姓名和年龄不变
student = (student[0], student[1], hobbies)
print(student)
~~~

### 08-字符串的定义和操作

### 09-案例：

### 10-数据容器（序列）的切片

### 11-案例：

### 12-集合的定义和操作

### 13-案例：

### 14-字典的定义

### 15-字典的常用操作

### 16-案例：

### 17-5类数据容器的总结对比

### 18-数据容器的通用操作

### 19-拓展-字符串大小比较的方式

## 第七章