# [python编程从入门到实践笔记](https://github.com/hadleysu/gitblog/issues/4)

# python编程从入门到实践笔记<!-- omit in toc -->

- [Is Python interpreted or compiled? Yes.](#is-python-interpreted-or-compiled-yes)
- [2 变量和简单的数据类型](#2-变量和简单的数据类型)
  - [变量](#变量)
  - [字符串](#字符串)
  - [数](#数)
  - [注释](#注释)
- [3 列表简介](#3-列表简介)
  - [列表](#列表)
  - [管理列表 ( sort() , sorted() , len() )](#管理列表--sort--sorted--len-)
  - [使⽤列表时避免索引错误](#使列表时避免索引错误)
- [4 操作列表](#4-操作列表)
  - [遍历整个列表（for）](#遍历整个列表for)
  - [避免缩进错误](#避免缩进错误)
  - [创建数值列表 ( list ( range() ) )](#创建数值列表--list--range--)
  - [使用列表的一部分（切片）](#使用列表的一部分切片)
  - [元组](#元组)
  - [设置代码格式](#设置代码格式)
- [5 if 语句](#5-if-语句)
  - [条件测试（布尔表达式）](#条件测试布尔表达式)
  - [if 语句/ if-else 语句/ if-elif-else 语句](#if-语句-if-else-语句-if-elif-else-语句)
  - [使⽤ if 语句处理列表](#使-if-语句处理列表)
- [6 字典](#6-字典)
  - [字典定义（ { key : value , key : value } ）](#字典定义--key--value--key--value--)
  - [使⽤字典](#使字典)
  - [遍历字典](#遍历字典)
  - [嵌套](#嵌套)
- [7 ⽤户输⼊和 while 循环](#7-户输和-while-循环)
  - [使⽤ input() 来让⽤户提供信息](#使-input-来让户提供信息)
  - [控制 while 循环流程的⽅式](#控制-while-循环流程的式)
  - [使⽤ while 循环处理列表和字典](#使-while-循环处理列表和字典)
- [8 函数](#8-函数)
  - [定义函数、实参形参](#定义函数实参形参)
  - [如何传递实参](#如何传递实参)
  - [返回值](#返回值)
  - [传递列表](#传递列表)
  - [传递任意数量的实参 （\*形参 / \*\*形参）](#传递任意数量的实参-形参--形参)
  - [将函数存储在模块中，再将模块导⼊主程序](#将函数存储在模块中再将模块导主程序)
  - [函数编写指南](#函数编写指南)
- [9 类](#9-类)
  - [创建和使⽤类创建实例](#创建和使类创建实例)
  - [给类的属性指定默认值，修改实例的属性的值](#给类的属性指定默认值修改实例的属性的值)
  - [继承](#继承)
  - [导⼊类](#导类)
  - [Python 标准库](#python-标准库)
  - [类的编程⻛格](#类的编程格)
- [10 ⽂件和异常](#10-件和异常)
  - [读取⽂件（ path对象 . read\_text() ）](#读取件-path对象--read_text-)
  - [写⼊⽂件（ path对象 . write\_text() ）](#写件-path对象--write_text-)
  - [异常](#异常)
    - [使⽤ try-except 代码块](#使-try-except-代码块)
    - [else 代码块](#else-代码块)
    - [常见的异常类型有](#常见的异常类型有)
  - [使⽤模块 json 来存储数据](#使模块-json-来存储数据)
  - [重构](#重构)
- [11 使⽤ pytest 工具库测试代码](#11-使-pytest-工具库测试代码)
  - [使⽤ pip 安装 pytest](#使-pip-安装-pytest)
  - [测试函数](#测试函数)
  - [运⾏测试](#运测试)
  - [测试类](#测试类)
  - [使⽤夹具](#使夹具)

## [Is Python interpreted or compiled? Yes.](https://nedbatchelder.com/blog/201803/is_python_interpreted_or_compiled_yes.html)

## 2 变量和简单的数据类型

### 变量

- 变量(variable)：变量是可以被赋值的标签，也可以说变量指向特定的值(value)。
  - 变量的命名：变量名只能包含字⺟、数字和下划线 。变量名能以字⺟或下划线打头，但不能以数字打头。变量名不能包含空格，但能使⽤下划线来分隔其中的单词。
  - 注意：应使⽤⼩写的 Python 变量名。全大写定义常量。

### 字符串

- 字符串(string)：。在 Python 中，⽤引号引起的都是字符串，其中的引号可以是单引号，也可以是双引号.
  - 使⽤⽅法修改字符串的⼤⼩写:
  
    ```python
    name = "ada lovelace"
    print(name.title()) # title() ⽅法以⾸字⺟⼤写的⽅式显⽰每个单词
    name = "Ada Lovelace"
    print(name.upper()) # upper() 方法以全大写显示字符串
    print(name.lower()) # lower() 方法以全小写显示字符串
    ```

  - f 字符串：将要插⼊的变量放在花括号内
  
    ```python
    first_name = "ada"
    last_name = "lovelace"
    full_name = f"{first_name} {last_name}"
    print(full_name)
    print(f"Hello, {full_name.title()}!")
    # 这种字符串称为 f 字符串。f 是 format（设置格式）的简写，因为 Python 通过把花括号内的变量替换为其值来设置字符串的格式。
    ```

  - 使⽤制表符或换⾏符来添加空⽩
  
    ```python
    # 制表符 \t ; 换行符 \n ;
    >>> print("Languages:\n\tPython\n\tC\n\tJavaScript")
    Languages:
        Python
        C
        JavaScript
    ```

  - 删除空⽩
  
    ```python
    # rstrip() lstrip() strip()分别为删除字符串右端的空⽩、删除字符串左端的空⽩、同时删除字符串两端的空⽩
    >>> favorite_language = ' python '
    >>> favorite_language.rstrip()
    ' python'
    >>> favorite_language.lstrip()
    'python '
    >>> favorite_language.strip()
    'python'
    ```

  - 删除前缀
  
    ```python
    # removeprefix() ⽅法
    >>> nostarch_url = 'https://nostarch.com'
    >>> nostarch_url.removeprefix('https://')
    'nostarch.com'
    # 如果想保留删除前缀后的值，既可将其重新赋给原来的变量，也可将其赋给另⼀个变量
    >>> simple_url = nostarch_url.removeprefix('https://')
    ```

### 数

- 整数(integer)
  
  ```python
  # Python 使⽤两个乘号（**）表⽰乘⽅运算
  >>> 3 ** 2
  9
  ```

- 浮点数(float)
  
  ```python
  # 将任意两个数相除，结果总是浮点数，即便这两个数都是整数且能整除：
  >>> 4/2
  2.0
  # 在 Python 中，⽆论是哪种运算，只要有操作数是浮点数，默认得到的就总是浮点数，即便结果原本为整数。
  >>> 1 + 2.0
  3.0
  >>> 2 * 3.0
  6.0
  >>> 3.0 ** 2
  9.0
  ```

- 数中的下划线
  
  ```python
  # 为在存储这种数时，Python 会忽略其中的下划线。在对数字位分组时，即便不是将每三位分成⼀组，也不会影响最终的值。
  >>> universe_age = 14_000_000_000
  >>> print(universe_age)
  14000000000
  # 这种表⽰法既适⽤于整数，也适⽤于浮点数。
  ```

- 常数(constant)：是在程序的整个⽣命周期内都保持不变的变量。其变量名全⼤写。

  ```python
  MAX_CONNECTIONS = 5000
  ```

### 注释

- 注释(comment)：注释⽤井号（#）标识。批量注释CTRL + /
  
## 3 列表简介

### 列表

- 列表(list)：由⼀系列按特定顺序排列的元素组成。在 Python 中，⽤⽅括号（[]）表⽰列表，⽤逗号分隔其中的元素。
  - Python 为访问最后⼀个列表元素提供了⼀种特殊语法。通过将索引指定为-1，可让 Python 返回最后⼀个列表元素。

    ```python
    bicycles = ['trek', 'cannondale', 'redline', 'specialized']
    print(bicycles[-1])
    # 这些代码返回 'specialized'。
    ```

  - 这种语法很有⽤，因为你经常需要在不知道列表⻓度的情况下访问最后的元素。这种约定也适⽤于其他负数索引，例如，索引 -2 返回倒数第⼆个列表元素，索引 -3 返回倒数第三个列表元素，依此类推。

- 修改、添加和删除元素
  - 修改列表元素

    ```python
    motorcycles = ['honda', 'yamaha', 'suzuki']
    print(motorcycles)
    motorcycles[0] = 'ducati'
    print(motorcycles)
    ```

  - 在列表中添加元素
    - 在列表末尾添加元素
  
      ```python
      # 在列表中添加新元素时，最简单的⽅式是将元素追加（append）到列表末尾。
      motorcycles = ['honda', 'yamaha', 'suzuki']
      print(motorcycles)
      motorcycles.append('ducati')
      print(motorcycles)
      # append() ⽅法让动态地创建列表易如反掌。例如，你可以先创建⼀个空列表，再使⽤⼀系列函数调⽤ append() 添加元素。
      motorcycles = []
      motorcycles.append('honda')
      motorcycles.append('yamaha')
      motorcycles.append('suzuki')
      print(motorcycles)
      ```

    - 在列表中插⼊元素

      ```python
      # 使⽤ insert() ⽅法可在列表的任意位置添加新元素。
      motorcycles = ['honda', 'yamaha', 'suzuki']
      motorcycles.insert(0, 'ducati')
      print(motorcycles)
      #这种操作将列表中的每个既有元素都右移⼀个位置。
      ['ducati', 'honda', 'yamaha', 'suzuki']
      ```

  - 从列表中删除元素
    - 使⽤ del 语句删除元素

      ```python
      #如果知道要删除的元素在列表中的位置，可使⽤ del 语句
      #使⽤ del 可删除任意位置的列表元素，只需要知道其索引即可。
      motorcycles = ['honda', 'yamaha', 'suzuki']
      print(motorcycles)
      del motorcycles[1]
      print(motorcycles)
      ```

    - 使⽤ pop() ⽅法删除元素
  
      ```python
      # pop() ⽅法删除列表末尾的元素，并让你能够接着使⽤它。每当你使⽤ pop() 时，被弹出的元素就不再在列表中了。
      motorcycles = ['honda', 'yamaha', 'suzuki']
      print(motorcycles)
      popped_motorcycle = motorcycles.pop()
      print(motorcycles)
      print(popped_motorcycle)
      # 输出表明，列表末尾的值 'suzuki' 已删除，它现在被赋给了变量popped_motorcycle
      ['honda', 'yamaha', 'suzuki']
      ['honda', 'yamaha']
      suzuki
      ```

    - 删除列表中任意位置的元素
  
      ```python
      # 也可以使⽤ pop() 删除列表中任意位置的元素，只需要在括号中指定要删除的元素的索引即可。
      motorcycles = ['honda', 'yamaha', 'suzuki']
      first_owned = motorcycles.pop(0)
      print(f"The first motorcycle I owned was a {first_owned.title()}.")
      # ⾸先弹出列表中的第⼀款摩托⻋，然后打印⼀条有关这辆摩托⻋的消息。
      The first motorcycle I owned was a Honda.
      ```

      如果不确定该使⽤ del 语句还是 pop() ⽅法，下⾯是⼀个简单的判断标准：如果要从列表中删除⼀个元素，且不再以任何⽅式使⽤它，就使⽤ del 语句；如果要在删除元素后继续使⽤它，就使⽤ pop() ⽅法。

    - 根据值删除元素
  
      ```python
      # 有时候，你不知道要从列表中删除的值在哪个位置。如果只知道要删除的元素的值，可使⽤ remove() ⽅法。
      motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']
      print(motorcycles)
      motorcycles.remove('ducati')
      print(motorcycles)
      # remove() ⽅法让 Python 确定 'ducati' 出现在列表的什么地⽅，并将该元素删除：
      ['honda', 'yamaha', 'suzuki', 'ducati']
      ['honda', 'yamaha', 'suzuki']
      # 注意：remove() ⽅法只删除第⼀个指定的值。如果要删除的值可能在列表中出现多次，就需要使⽤循环，确保将每个值都删除。这将在第 7 章介绍。
      ```

### 管理列表 ( sort() , sorted() , len() )

- 使⽤ sort() ⽅法对列表进⾏永久排序
  
  ```python
  cars = ['bmw', 'audi', 'toyota', 'subaru']
  cars.sort()
  print(cars)
  # sort() ⽅法能永久地修改列表元素的排列顺序。现在，汽⻋是按字⺟顺序排列的，再也⽆法恢复到原来的排列顺序：
  ['audi', 'bmw', 'subaru', 'toyota']
  # 还可以按与字⺟顺序相反的顺序排列列表元素，只需向 sort() ⽅法传递参数 reverse=True 即可。下⾯的⽰例将汽⻋列表按与字⺟顺序相反的顺序排列：
  cars.sort(reverse=True)
  # 同样，对列表元素排列顺序的修改也是永久的：
  ['toyota', 'subaru', 'bmw', 'audi']
  ```

- 使⽤ sorted() 函数对列表进⾏临时排序

  ```python
  # 要保留列表元素原来的排列顺序，并以特定的顺序呈现它们，可使⽤sorted() 函数。
  cars = ['bmw', 'audi', 'toyota', 'subaru']
  ❶ print("Here is the original list:")
  print(cars)
  ❷ print("\nHere is the sorted list:")
  print(sorted(cars))
  ❸ print("\nHere is the original list again:")
  print(cars)
  # 注意，在调⽤ sorted() 函数后，列表元素的排列顺序并没有变:
  Here is the original list:
  ['bmw', 'audi', 'toyota', 'subaru']
  Here is the sorted list:
  ['audi', 'bmw', 'subaru', 'toyota']
  Here is the original list again:
  ['bmw', 'audi', 'toyota', 'subaru']
  # 如果要按与字⺟顺序相反的顺序显⽰列表，也可向 sorted() 函数传递参数 reverse=True。
  # 注意：在并⾮所有的值都是全⼩写的时，按字⺟顺序排列列表要复杂⼀些。在确定排列顺序时，有多种解读⼤写字⺟的⽅式，此时要指定准确的排列顺序，可能会⽐这⾥所做的更加复杂。然⽽，⼤多数排序⽅式是以本节介绍的知识为基础的。
  ```

- 反向打印列表

  ```python
  # 要反转列表元素的排列顺序，可使⽤ reverse() ⽅法。
  cars = ['bmw', 'audi', 'toyota', 'subaru']
  print(cars)
  cars.reverse()
  print(cars)
  #请注意，reverse() 不是按与字⺟顺序相反的顺序排列列表元素，只是反转列表元素的排列顺序：
  ['bmw', 'audi', 'toyota', 'subaru']
  ['subaru', 'toyota', 'audi', 'bmw']
  # reverse() ⽅法会永久地修改列表元素的排列顺序，但可随时恢复到原来的排列顺序，只需对列表再次调⽤ reverse() 即可。
  ```

- 确定列表的⻓度

  ```python
  # 使⽤ len() 函数可快速获悉列表的⻓度。
  >>> cars = ['bmw', 'audi', 'toyota', 'subaru']
  >>> len(cars)
  4
  # 注意：Python 在计算列表元素数时从 1 开始，因此你在确定列表⻓度时应该不会遇到差⼀错误。
  ```

### 使⽤列表时避免索引错误  

- 仅当列表为空时，这种访问最后⼀个元素的⽅式才会导致错误：

```python
motorcycles = []
print(motorcycles[-1])
# 列表 motorcycles 不包含任何元素，因此 Python 返回⼀条索引错误消息：
Traceback (most recent call last):
  File "motorcyles.py", line 3, in <module>
    print(motorcycles[-1])
          ~~~~~~~~~~~^^^^
IndexError: list index out of range
```

- *注意*：在发⽣索引错误却找不到解决办法时，请尝试将列表或其⻓度打印出来。列表可能与你以为的截然不同，在程序对其进⾏了动态处理时尤其如此。查看列表或其包含的元素数，可帮助你排查这种逻辑错误。

## 4 操作列表

### 遍历整个列表（for）

- for循环。在 for 循环中，想包含多少⾏代码都可以。在代码⾏ for magician inmagicians 后⾯，每⾏缩进的代码都是循环的⼀部分，将针对列表中的每个值执⾏⼀次。因此，可对列表中的每个值执⾏任意多的操作。

  ```python
  magicians = ['alice', 'david', 'carolina']
  for magician in magicians:
      print(f"{magician.title()}, that was a great trick!")
      print(f"I can't wait to see your next trick,{magician.title()}.\n")

  print("Thank you, everyone. That was a great magic show!")
  ```

- 在for 循环后⾯，没有缩进的代码都只执⾏⼀次，不会重复执⾏。

### 避免缩进错误

- 位于 for 语句后⾯且属于循环组成部分的代码⾏，⼀定要缩进。为避免意外的缩进错误，请只缩进需要缩进的代码。
- 不要遗漏*冒号*。for 语句末尾的冒号告诉 Python，下⼀⾏是循环的第⼀⾏。

### 创建数值列表 ( list ( range() ) )

- range() 函数。Python 函数 range() 能⽣成⼀系列的数。可以传一个参数、两个参数、三个参数。

  ```python
  for value in range(1, 3):
      print(value)
  # range() 函数让 Python 从指定的第⼀个值开始数，并在到达指定的第⼆个值时停⽌，因此输出不包含第⼆个值（这⾥为 3）。
  1
  2
  # 在使⽤ range() 时，如果输出不符合预期，请尝试将指定的值加 1 或减 1。
  #在调⽤ range() 函数时，也可只指定⼀个参数，这样它将从 0 开始，例如，range(6) 返回数 0〜5（含）。
  ```

- 使⽤ range() 创建数值列表  

  要创建数值列表，可使⽤ list() 函数将 range() 的结果直接转换为列表。如果将 range() 作为 list() 的参数，输出将是⼀个数值列表。

  ```python
  numbers = list(range(1, 6))
  print(numbers)
  # 结果如下：
  [1, 2, 3, 4, 5]
  # 在使⽤ range() 函数时，还可指定步⻓。为此，可以给这个函数指定第三个参数，Python 将根据这个步⻓来⽣成数。
  # 例如，下⾯的代码打印 1〜10 的偶数：
  even_numbers = list(range(2, 11, 2))
  print(even_numbers)
  # 在这个⽰例中，range() 函数从 2 开始数，然后不断地加 2，直到达到或超过终值（11）。因此输出如下：
  [2, 4, 6, 8, 10]
  # 如何将前 10 个整数的平⽅加⼊⼀个列表：
  squares = []
  for value in range(1,11):
      squares.append(value**2)
  print(squares)
  ```

- 对数值列表执⾏简单的统计计算  
  
  max(),min(),sum(),找出数值列表中的最⼤值、最⼩值和总和.

  ```python
  >>> digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
  >>> min(digits)
  0
  >>> max(digits)
  9
  >>> sum(digits)
  45
  ```

- 列表推导式（list comprehension）  
  
  列表推导式将 for 循环和创建新元素的代码合并成⼀⾏，并⾃动追加新元素。  
  要使⽤这种语法，⾸先指定⼀个描述性的列表名，如 squares。然后指定⼀个左⽅括号，并定义⼀个表达式，⽤于⽣成要存储到列表中的值。在这个⽰例中，表达式为 value** 2，它计算平⽅值。接下来，编写⼀个 for循环，⽤于给表达式提供值，再加上右⽅括号。在这个⽰例中，for 循环为 for value in range(1,11)，它将值1〜10 提供给表达式value * * 2。请注意，这⾥的 for 语句末尾没有冒号。
  
  ```python
  squares = [value**2 for value in range(1, 11)]
  print(squares)
  # 结果:
  [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
  ```

### 使用列表的一部分（切片）

- 切片（slice）  
  
  切片就是列表中的部分元素。要创建切⽚，可指定要使⽤的第⼀个元素和最后⼀个元素的索引。与range() 函数⼀样，Python 在到达指定的第⼆个索引之前的元素时停⽌。要输出列表中的前三个元素，需要指定索引 0 和 3，这将返回索引分别为0、1 和 2 的元素。

  ```python
  players = ['charles', 'martina', 'michael', 'florence', 'eli']
  print(players[0:3])
  # 这些代码打印该列表的⼀个切⽚。输出也是⼀个列表，其中包含前三名队员：
  ['charles', 'martina', 'michael']
  # 可以⽣成列表的任意⼦集。例如，如果要提取列表的第⼆、第三和第四个元素，可将起始索引指定为 1，并将终⽌索引指定为 4：
  players = ['charles', 'martina', 'michael', 'florence', 'eli']
  print(players[1:4])
  # 在⽣成的切⽚中，第⼀个元素为 'martina'，最后⼀个元素为'florence'：
  ['martina', 'michael', 'florence']
  # 如果没有指定第⼀个索引，Python 将⾃动从列表开头开始：
  players = ['charles', 'martina', 'michael', 'florence', 'eli']
  print(players[:4])
  # 由于没有指定起始索引，Python 从列表开头开始提取：
  ['charles', 'martina', 'michael', 'florence']
  # 要让切⽚终⽌于列表末尾，也可使⽤类似的语法。例如，如果要提取从第三个元素到列表末尾的所有元素，可将起始索引指定为 2，并省略终⽌索引：
  players = ['charles', 'martina', 'michael', 'florence', 'eli']
  print(players[2:])
  # Python 返回从第三个元素到列表末尾的所有元素：
  ['michael', 'florence', 'eli']
  # 负数索引返回与列表末尾有相应距离的元素，因此可以输出列表末尾的任意切⽚。如果要输出名单上最后三名队员的名字，可使⽤切⽚ players[-3:]：
  players = ['charles', 'martina', 'michael', 'florence', 'eli']
  print(players[-3:])
  ```

  注意：可在表⽰切⽚的⽅括号内指定第三个值。这个值告诉 Python 在指定范围内每隔多少元素提取⼀个。

- 遍历切片  
  
  如果要遍历列表的部分元素，可在 for 循环中使⽤切⽚。

  ```python
  players = ['charles', 'martina', 'michael', 'florence', 'eli']
  print("Here are the first three players on my team:")
  ❶for player in players[:3]:
      print(player.title())
  # ❶处的代码没有遍历整个队员列表，只遍历前三名队员：
  Here are the first three players on my team:
  Charles
  Martina
  Michael
  ```

- 复制列表  

  要复制列表，可以创建⼀个包含整个列表的切⽚，⽅法是同时省略起始索引和终⽌索引（[:]）。这让 Python 创建⼀个起始于第⼀个元素、终⽌于最后⼀个元素的切⽚，即复制整个列表。

  ```python
  my_foods = ['pizza', 'falafel', 'carrot cake']
  ❶ friend_foods = my_foods[:]
  ❷ my_foods.append('cannoli')
  ❸ friend_foods.append('ice cream')
  ###########################################
  # 这是⾏不通的：
  friend_foods = my_foods
  my_foods.append('cannoli')
  friend_foods.append('ice cream')
  # 上面❶将my_foods的切片赋给friend_foods，所以❷修改的是my_foods列表，❸修改的是friend_foods列表即my_foods的切片。
  # 而不使用切片，直接将my_foods赋值给friend_foods，意味着friend_foods和my_foods一起关联my_foods列表，因此这两个变量指向同⼀个列表。
  ```

### 元组

- 元组（tuple）  
  
  Python将不能修改的值称为不可变的，⽽不可变的列表称为元组（tuple）。如果需要存储⼀组在程序的整个⽣命周期内都不变的值，就可以使⽤元组。  
  元组看起来很像列表，但使⽤*圆括号*⽽不是⽅括号来标识。定义元组后，就可使⽤索引来访问其元素，就像访问列表元素⼀样。

  ```python
  dimensions = (200, 50)
  print(dimensions[0])
  print(dimensions[1])
  # ⾸先定义元组 dimensions，为此使⽤了圆括号⽽不是⽅括号。接下来，分别打印该元组的各个元素，使⽤的语法与访问列表元素时使⽤的语法相同
  ```

  试图修改元组的操作是被禁⽌的,一旦修改将导致Python 返回类型错误的消息。

  ```python
  dimensions = (200, 50)
  dimensions[0] = 250
  # 在代码试图修改矩形的尺⼨时，Python 会报错。
  ```  

  *注意*：严格地说，元组是由逗号标识的，圆括号只是让元组看起来更整洁、更清晰。如果你要定义只包含⼀个元素的元组，必须在这个元素后⾯加上逗号：

  ```python
  my_t = (3,)
  # 创建只包含⼀个元素的元组通常没有意义，但⾃动⽣成的元组有可能只有⼀个元素。
  ```

- fot循环遍历元组中的所有值

  ```python
  dimensions = (200, 50)
  for dimension in dimensions:
      print(dimension)
  ```

- 修改元组变量  
  
  虽然不能修改元组的元素，但可以给表⽰元组的变量赋值。例如，要修改前述矩形的尺⼨，可重新定义整个元组：

  ```python
  dimensions = (200, 50)
  dimensions = (400, 100)
  # 将⼀个新元组关联到变量 dimensions,Python 没有引发任何错误，因为给元组变量重新赋值是合法的
  ```

### 设置代码格式

- Python Enhancement Proposal，PEP(Python 增强提案)  

- 缩进  
  
  PEP 8 建议每级缩进都使⽤ 4 个空格。在编写Python代码时，混用Tab键和空格可能会导致错误。如果混合使⽤了制表符和空格，可将⽂件中的所有制表符都转换为空格，⼤多数编辑器提供了这样的功能。

- 行长  
  
  建议每⾏不超过 80 个字符。注释的⾏⻓不超过 72 个字符。

- 空行  

  将程序的不同部分分开，可使⽤空⾏。

## 5 if 语句

### 条件测试（布尔表达式）
  
- 布尔表达式的结果要么为 True，要么为 False。  
- 检查是否相等 ==
  - 在 Python 中检查是否相等时是区分⼤⼩写的。
- 检查是否不等 !=
- 数值⽐较 == / != / < / <= / > / >=
- 检查多个条件时的且或 and / or
- 检查特定的值是否在列表中 in
- 检查特定的值是否不在列表中 not in

### if 语句/ if-else 语句/ if-elif-else 语句
  
- if 语句/ if-else 语句/ if-elif-else 语句
  - if-elif-else 语句中可以使⽤多个 elif 代码块
  - Python 并不要求 if-elif 结构后⾯必须有 else 代码块。可省略 else 代码块。

  ```python
  age = 12
  if age < 4:
  price = 0
  elif age < 18:
  price = 25
  else:
  price = 40
  print(f"Your admission cost is ${price}.")
  ```

### 使⽤ if 语句处理列表  
  
- 检查特殊元素

  ```python
  requested_toppings = ['mushrooms', 'green peppers', 'extra cheese']
  for requested_topping in requested_toppings:
      if requested_topping == 'green peppers':
          print("Sorry, we are out of green peppers right now.")
      else:
          print(f"Adding {requested_topping}.")
  ```

- 确定列表⾮空

  ```python
  requested_toppings = []
  if requested_toppings:
      for requested_topping in requested_toppings:
          print(f"Adding {requested_topping}.")
      print("\nFinished making your pizza!")
  else:
      print("Are you sure you want a plain pizza?")
  # 这⾥的列表为空，因此输出如下——询问顾客是否确实要点原味⽐萨：
  Are you sure you want a plain pizza?
  ```

  - 在 if 语句中将列表名⽤作条件表达式时，Python将在列表⾄少包含⼀个元素时返回 True，在列表为空时返回 False 。
  - **对于数值 0、空值 None、单引号空字符串 ''、双引号空字符串 ""、空列表 []、空元组 ()、空字典 {}，Python 都会返回 False。**

- 使⽤多个列表

  ```python
  available_toppings = ['mushrooms', 'olives', 'green peppers','pepperoni', 'pineapple', 'extra cheese']
  requested_toppings = ['mushrooms', 'french fries', 'extra cheese']

  for requested_topping in requested_toppings:
      if requested_topping in available_toppings:
         print(f"Adding {requested_topping}.")
      else:
         print(f"Sorry, we don't have {requested_topping}.")
  print("\nFinished making your pizza!")
  # 输出
  Adding mushrooms.
  Sorry, we don't have french fries.
  Adding extra cheese.
  Finished making your pizza!
  ```

## 6 字典

### 字典定义（ { key : value , key : value } ）  

- 在 Python 中，字典（dictionary）是⼀系列**键值对**。每个**键**都与⼀个值关联，可以使⽤键来访问与之关联的值。与键相关联的值可以是数、字符串、列表乃⾄字典。事实上，可将任意 Python 对象⽤作字典中的值。
- 在 Python 中，字典⽤放在**花括号**（{}）中的⼀系列键值对表⽰。
- **键值对**包含两个相互关联的值。当你指定键时，Python 将返回与之关联的值。键和值之间⽤**冒号**分隔，⽽键值对之间⽤**逗号**分隔。在字典中，你想存储多少个键值对都可以。

```python
alien_0 = {'color': 'green', 'points': 5}
```

### 使⽤字典

- 访问字典中的值
  
  ```python
  # 要获取与键关联的值，可指定字典名并把键放在后⾯的⽅括号内，如下所⽰：
  alien_0 = {'color': 'green'}
  print(alien_0['color'])
  green
  ```

- 添加键值对
  
  ```python
  # 字典是⼀种动态结构，可随时在其中添加键值对。要添加键值对，可依次指定字典名、⽤⽅括号括起来的键和与该键关联的值。
  alien_0 = {'color': 'green', 'points': 5}
  print(alien_0)
  alien_0['x_position'] = 0
  alien_0['y_position'] = 25
  print(alien_0)
  # 字典会保留定义时的元素排列顺序。如果将字典打印出来或遍历其元素，将发现元素的排列顺序与其添加顺序相同。
  {'color': 'green', 'points': 5}
  {'color': 'green', 'points': 5, 'x_position': 0, 'y_position': 25}
  ```

- 创建⼀个空字典
  
  ```python
  alien_0 = {}
  alien_0['color'] = 'green'
  alien_0['points'] = 5
  ```

- 修改字典中的值
  
  ```python
  # 要修改字典中的值，可依次指定字典名、⽤⽅括号括起来的键和与该键关联的新值。
  alien_0 = {'color': 'green'}
  alien_0['color'] = 'yellow'
  ```

- 删除键值对
  
  ```python
  #对于字典中不再需要的信息，可使⽤ del 语句将相应的键值对彻底删除。在使⽤ del 语句时，必须指定字典名和要删除的键。
  alien_0 = {'color': 'green', 'points': 5}
  del alien_0['points']
  print(alien_0)
  # 注意：删除的键值对永远消失了。
  {'color': 'green', 'points': 5}
  {'color': 'green'}
  ```

- 由类似的对象组成的字典
  
  ```python
  # 当确定需要使⽤多⾏来定义字典时，先在输⼊左花括号后按回⻋键，再在下⼀⾏缩进 4 个空格，指定第⼀个键值对，并在它后⾯加上⼀个逗号。
  favorite_languages = {
      'jen': 'python',
      'sarah': 'c',
      'edward': 'rust',
      'phil': 'python',
      }
  # 定义好字典后，在最后⼀个键值对的下⼀⾏添加⼀个右花括号，并且也缩进 4 个空格，使其与字典中的键对⻬。
  # ⼀种不错的做法是，在最后⼀个键值对后⾯也加上逗号，为以后添加键值对做好准备。
  ```

- 使⽤ get() 来访问值
  
  - 如果指定的键有可能不存在，应考虑使⽤ get() ⽅法，⽽不要使⽤⽅括号表⽰法，因为会报错。
  - get() ⽅法在指定的键不存在时返回⼀个默认值。get() ⽅法的第⼀个参数⽤于指定键，是必不可少的；第⼆个参数为当指定的键不存在时要返回的值，是可选的。
  - 注意：在调⽤ get() 时，如果没有指定第⼆个参数且指定的键不存在，Python 将返回值 None，这个特殊的值表⽰没有相应的值。这并⾮错误，None 只是⼀个表⽰所需值不存在的特殊值，第 8 章将介绍它的其他⽤途。

    ```python
    alien_0 = {'color': 'green', 'speed': 'slow'}
    point_value = alien_0.get('points', 'No point value assigned.')
    print(point_value)
    # 如果字典中有键 'points'，将获得与之关联的值；如果没有，将获得指定的默认值。虽然这⾥没有键 'points'，但是我们将获得⼀条清晰的消息，不会引发错误：
    No point value assigned.
    ```

### 遍历字典

- 遍历所有的键值对 ( items() )  
  字典名.items()，这个⽅法返回⼀个键值对列表。  

  ```python
  favorite_languages = {
      'jen': 'python',
      'sarah': 'c',
      'edward': 'rust',
      'phil': 'python',
      }
  for name, language in favorite_languages.items():
      print(f"{name.title()}'s favorite language is {language.title()}.")
  # 这些代码让 Python 遍历字典中的每个键值对，并将键赋给变量 name，将值赋给变量 language。
  Jen's favorite language is Python.
  Sarah's favorite language is C.
  Edward's favorite language is Rust.
  Phil's favorite language is Python.
  ```

- 遍历字典中的所有键 ( keys() )

  ```python
  favorite_languages = {
      'jen': 'python',
      'sarah': 'c',
      'edward': 'rust',
      'phil': 'python',
      }
  for name in favorite_languages.keys():
      print(name.title())
  # keys() ⽅法并⾮只能⽤于遍历：实际上，它会返回⼀个列表，其中包含字典中的所有键。
  if 'erin' not in favorite_languages.keys():
      print("Erin, please take our poll!")
  # 输出
  Erin, please take our poll!
  ```

- 按特定的顺序遍历字典中的所有键 ( sorted() )
  
  ```python
  favorite_languages = {
        'jen': 'python',
        'sarah': 'c',
        'edward': 'rust',
        'phil': 'python',
        }
  for name in sorted(favorite_languages.keys()):
      print(f"{name.title()}, thank you for taking the poll.")
  # 对⽅法 dictionary.keys() 的结果调⽤了 sorted() 函数。这让 Python 获取字典中的所有键，并在遍历前对这个列表进⾏排序。输出表明，按字⺟顺序显⽰了所有被调查者的名字：
  Edward, thank you for taking the poll.
  Jen, thank you for taking the poll.
  Phil, thank you for taking the poll.
  Sarah, thank you for taking the poll.
  ```

- 遍历字典中的所有值 ( values() ，set() )

  ```python
  favorite_languages = {
      'jen': 'python',
      'sarah': 'c',
      'edward': 'rust',
      'phil': 'python',
      }
  for language in favorite_languages.values():
      print(language.title())
  # 这条 for 语句提取字典中的每个值，并将它们依次赋给变量 language。
  Python
  C
  Rust
  Python
  # 这种做法提取字典中所有的值，⽽没有考虑值是否有重复。这种做法提取字典中所有的值，⽽没有考虑值是否有重复。
  for language in set(favorite_languages.values()):
      print(language.title())
  # 通过将包含重复元素的列表传⼊ set()，可让 Python 找出列表中独⼀⽆⼆的元素，并使⽤这些元素来创建⼀个集合。
  Python
  C
  Rust
  ```

  - 注意：可以使⽤⼀对花括号直接创建集合，并在其中⽤逗号分隔元素：
  
    ```python
    >>> languages = {'python', 'rust', 'python', 'c'}
    >>> languages
    {'rust', 'python', 'c'}
    ```
  
  - 集合和字典很容易混淆，因为它们都是⽤⼀对花括号定义的。当花括号内没有键值对时，定义的很可能是集合。
  - 不同于列表和字典，集合不会以特定的顺序存储元素（集合本质上是无序的）。

### 嵌套

- 字典列表

  ```python
  # 创建⼀个⽤于存储外星⼈的空列表
  aliens = []
  # 创建 30 个绿⾊的外星⼈
  # range() 函数返回⼀个数字序列，告诉 Python 要重复这个循环多少次。
  for alien_number in range(30):
      new_alien = {'color': 'green', 'points': 5, 'speed': 'slow'}
      aliens.append(new_alien)
  # 使⽤⼀个切⽚来打印前 5 个外星⼈。
  for alien in aliens[:5]:
      print(alien)
  # 显⽰创建了多少个外星⼈
  print(f"Total number of aliens: {len(aliens)}")
  ```

- 在字典中存储列表  
  
  每当需要在字典中将⼀个键关联到多个值时，都可以在字典中嵌套⼀个列表。

  ```python
  # 在这⾥，与每个名字关联的值都是⼀个列表。请注意，有些⼈喜欢的语⾔只有⼀种，⽽有些⼈喜欢的不⽌⼀种。
  favorite_languages = {
      'jen': ['python', 'rust'],
      'sarah': ['c'],
      'edward': ['rust', 'go'],
      'phil': ['python', 'haskell'],
      }
  for name, languages in favorite_languages.items():
      print(f"\n{name.title()}'s favorite languages are:")
      for language in languages:
          print(f"\t{language.title()}")
  # 注意：列表和字典的嵌套层级不应太多。
  ```

- 在字典中存储字典

  ```python
  users = {
      'aeinstein': {
          'first': 'albert',
          'last': 'einstein',
          'location': 'princeton',
          },
      'mcurie': {
          'first': 'marie',
          'last': 'curie',
          'location': 'paris',
          },
      }
  for username, user_info in users.items():
      print(f"\nUsername: {username}")
      full_name = f"{user_info['first']} {user_info['last']}"
      location = user_info['location']
      print(f"\tFull name: {full_name.title()}")
      print(f"\tLocation: {location.title()}")
  # 输出

  Username: aeinstein
      Full name: Albert Einstein
      Location: Princeton

  Username: mcurie
      Full name: Marie Curie
      Location: Paris
  # ⾸先定义⼀个名为 users 的字典，其中包含两个键：⽤户名'aeinstein' 和 'mcurie'。与每个键关联的值都是⼀个字典，其中包含⽤户的名、姓和居住地。然后，遍历字典 users，让 Python 依次将每个键赋给变量 username，并依次将与当前键相关联的字典赋给变量 user_info。在循环内部，将⽤户名打印出来了。接下来，开始访问内部的字典。变量user_info 包含⽤户信息字典，⽽该字典包含三个键：'first'、'last' 和 'location'。对于每个⽤户，都使⽤这些键来⽣成整洁的姓名和居住地，然后打印有关⽤户的简要信息
  ```

## 7 ⽤户输⼊和 while 循环

### 使⽤ input() 来让⽤户提供信息

- input() 函数让程序暂停运⾏，等待⽤户输⼊⼀些⽂本。获取⽤户输⼊后，Python 将其赋给⼀个变量，以便使⽤。
  
  ```python
  message = input("Tell me something, and I will repeat it back to you: ")
  print(message)
  # input() 函数接受⼀个参数，即要向⽤户显⽰的提⽰（prompt），让⽤户知道该输⼊什么样的信息。
  ```

- 使⽤ int() 来获取数值输⼊（如何处理⽂本和数的输⼊）
  
  在使⽤ input() 函数时，Python 会将⽤户输⼊解读为字符串。  
  在将数值输⼊⽤于计算和⽐较前，务必将其转换为数值表⽰。

  ```python
  height = input("How tall are you, in inches? ")
  height = int(height)
  if height >= 48:
   print("\nYou're tall enough to ride!")
  else:
   print("\nYou'll be able to ride when you're a little older.")
  # 在⽐较前，height = int(height) 将输⼊转换成了数值表⽰。
  # 如果输⼊的数⼤于或等于 48，就指出⽤户满⾜⾝⾼条件：
  How tall are you, in inches? 71
  You're tall enough to ride!
  ```

- 求模运算符 ( % )  

  它将两个数相除并返回余数。求模运算符不会指出⼀个数是另⼀个数的多少倍，只指出余数是多少。

  ```python
  >>> 4 % 3
  1
  >>> 5 % 3
  2
  >>> 6 % 3
  0
  >>> 7 % 3
  1
  ```

  如果⼀个数可被另⼀个数整除，余数就为 0，因此求模运算将返回 0。可利⽤这⼀点来判断⼀个数是奇数还是偶数：

  ```python
  number = input("Enter a number, and I'll tell you if it's even or odd: ")
  number = int(number)
  if number % 2 == 0:
      print(f"\nThe number {number} is even.")
  else:
      print(f"\nThe number {number} is odd.")

  ```

### 控制 while 循环流程的⽅式

- 使⽤标志（flag）

  **注意：python 中 True 和 False 要开头大写**
  
  ```python
  # 这个变量称为标志（flag），充当程序的交通信号灯。可以让程序在标志为 True 时继续运⾏，并在任何事件导致标志的值为 False 时让程序停⽌运⾏。
  prompt = "\nTell me something, and I will repeat it back to you:"
  prompt += "\nEnter 'quit' to end the program. "
  active = True
  while active:
      message = input(prompt)
      if message == 'quit':
          active = False
      else:
          print(message)
  ```

- 使⽤ break 退出循环
  
  ```python
  # 在所有 Python 循环中都可使⽤ break 语句。例如，可使⽤break 语句来退出遍历列表或字典的 for 循环。
  prompt = "\nPlease enter the name of a city you have visited:"
  prompt += "\n(Enter 'quit' when you are finished.) "
  while True:
      city = input(prompt)
      if city == 'quit':
          break
      else:
          print(f"I'd love to go to {city.title()}!")

  ```

- 在循环中使⽤ continue
  
  ```python
  # 执⾏ continue 语句，让 Python 忽略余下的代码，并返回循环的开头。
  # 打印1-10奇数
  current_number = 0
  while current_number < 10:
      current_number += 1
      if current_number % 2 == 0:
          continue
      print(current_number)
  ```
  
### 使⽤ while 循环处理列表和字典

- for 循环是⼀种遍历列表的有效⽅式，但不应该在 for 循环中修改列表，否则将导致 Python 难以跟踪其中的元素。要在遍历列表的同时修改它，可使⽤ while 循环。

  ```python
  # 错误操作一
  a = [1, 2, 4, 4, 5]
  for i, v in enumerate(a):
      if v == 4:
          del a[i]
  # 结果为 
  a = [1, 2, 4, 5]
  # 这是因为 Python 的 for 循环存在自动填充，即在循环中自动填充列表中的下一个元素，如果在循环中修改列表的值，可能会引发错误。
  # 由于在遍历的过程中，删除了其中一个元素，导致后面的元素整体前移，导致有个元素成了漏网之鱼。
  a  0 1 2 3 4   -->     0 1 2 3
     1 2 4 4 5   -->     1 2 4 5
  ```

  ```python
  # 错误操作二
  a = [1, 2, 4, 4, 5]
  for i in range(len(a)):
      if a[i] == 4:
          del a[i]
  # 直接报错
  IndexError: list index out of range
  i 最大取值为4，但删除操作后的列表长度为4，最大下标为3，所以报错 list index out of range
  ```

  ```python
  # 正确操作
  a = [1, 2, 4, 4, 5]
  i = 0
  while i < len(a):
      if a[i] == 4:
          del a[i]
      else:
          i += 1
  ```

- 在列表之间移动元素

  ```python
  # ⾸先，创建⼀个待验证⽤户列表
  # 和⼀个⽤于存储已验证⽤户的空列表
  unconfirmed_users = ['alice', 'brian', 'candace']
  confirmed_users = []
  # 验证每个⽤户，直到没有未验证⽤户为⽌
  # 将每个经过验证的⽤户都移到已验证⽤户列表中
  # while 循环将不断地运⾏，直到列表 unconfirmed_users 变成空的。
  while unconfirmed_users:
      current_user = unconfirmed_users.pop()
      print(f"Verifying user: {current_user.title()}")
      confirmed_users.append(current_user)
  # 显⽰所有的已验证⽤户
  print("\nThe following users have been confirmed:")
  for confirmed_user in confirmed_users:
      print(confirmed_user.title())
  # 输出
  Verifying user: Candace
  Verifying user: Brian
  Verifying user: Alice
  The following users have been confirmed:
  Candace
  Brian
  Alice
  ```

- 删除为特定值的所有列表元素

  ```python
  pets = ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
  print(pets)
  while 'cat' in pets:
      pets.remove('cat')
  print(pets)
  # 输出
  ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
  ['dog', 'dog', 'goldfish', 'rabbit']
  ```

- 使⽤⽤户输⼊填充字典

  ```python
  # 可以使⽤ while 循环提⽰⽤户输⼊任意多的信息。下⾯创建⼀个调查程序，其中的循环在每次执⾏时都提⽰输⼊被调查者的名字和回答。我们将收集到的数据存储在⼀个字典中，以便将回答与被调查者关联起来：
  responses = {}
  # 设置⼀个标志，指出调查是否继续
  polling_active = True
  while polling_active:
      # 提⽰输⼊被调查者的名字和回答
      name = input("\nWhat is your name? ")
      response = input("Which mountain would you like to climb someday? ")
      # 将回答存储在字典中
      responses[name] = response
      # 看看是否还有⼈要参与调查
      repeat = input("Would you like to let another person respond? (yes/no) ")
      if repeat == 'no':
          polling_active = False
  # 调查结束，显⽰结果
  print("\n--- Poll Results ---")
  for name, response in responses.items():
      print(f"{name} would like to climb {response}.")
  # 输出

  What is your name? Eric
  Which mountain would you like to climb someday? Denali
  Would you like to let another person respond? (yes/no) yes
  What is your name? Lynn
  Which mountain would you like to climb someday? Devil's Thumb
  Would you like to let another person respond? (yes/no) no
  --- Poll Results ---
  Eric would like to climb Denali.
  Lynn would like to climb Devil's Thumb.
  ```
  
## 8 函数

### 定义函数、实参形参

- 函数（function）是带名字的代码块，⽤于完成具体的⼯作。要执⾏函数定义的特定任务，可调⽤（call）该函数。

- 使⽤关键字 def 定义函数。这是函数定义，向 Python 指出了函数名，还可以在括号内指出函数为完成任务需要什么样的信息。最后，定义以冒号结尾。

- 紧跟在 def greet_user(): 后⾯的所有缩进⾏构成了函数体。第⼆⾏的⽂本是称为⽂档字符串（docstring）的注释，描述了函数是做什么的。Python 在为程序中的函数⽣成⽂档时，会查找紧跟在函数定义后的字符串。这些字符串通常前后分别⽤三个双引号引起，能够包含多⾏。

- 函数调⽤让 Python 执⾏函数中的代码。要调⽤函数，可依次指定函数名以及⽤括号括起的必要信息。

  ```python
  def greet_user(username):
      """显⽰简单的问候语"""
      print(f"Hello, {username.title()}!")
  greet_user('jesse')
  # 输出
  Hello, Jesse!
  ```

- 在 greet_user() 函数的定义中，变量 username 是⼀个形参（parameter），即函数完成⼯作所需的信息。在代码greet_user('jesse') 中，值 'jesse' 是⼀个实参（argument），即在调⽤函数时传递给函数的信息。

### 如何传递实参

- 位置实参

  ```python
  def describe_pet(animal_type, pet_name):
      """显⽰宠物的信息"""
      print(f"\nI have a {animal_type}.")
      print(f"My {animal_type}'s name is {pet_name. title()}.")
  describe_pet('hamster', 'harry')
  describe_pet('dog', 'willie')
  # 位置实参的顺序很重要
  ```

- 关键字实参

  ```python
  def describe_pet(animal_type, pet_name):
      """显⽰宠物的信息"""
      print(f"\nI have a {animal_type}.")
      print(f"My {animal_type}'s name is {pet_name.title()}.")
  # 下⾯两个函数调⽤是等效的 
  describe_pet(animal_type='hamster', pet_name='harry')
  describe_pet(pet_name='harry', animal_type='hamster')
  # 注意：在使⽤关键字实参时，务必准确地指定函数定义中的形参名。
  ```

- 默认值

   在编写函数时，可以给每个形参指定默认值。如果在调⽤函数中给形参提供了实参，Python 将使⽤指定的实参值；否则，将使⽤形参的默认值。因此，给形参指定默认值后，可在函数调⽤中省略相应的实参。使⽤默认值不仅能简化函数调⽤，还能清楚地指出函数的典型⽤法。

  ```python
  def describe_pet(pet_name, animal_type='dog'):
   """显⽰宠物的信息"""
   print(f"\nI have a {animal_type}.")
   print(f"My {animal_type}'s name is {pet_name.title()}.")
  describe_pet(pet_name='willie')
  describe_pet('willie')
  describe_pet(pet_name='harry', animal_type='hamster')
  ```

  注意：当使⽤默认值时，必须在形参列表中先列出没有默认值的形参，再列出有默认值的形参。这让 Python 依然能够正确地解读位置实参。

- 等效的函数调⽤

  ```python
  def describe_pet(pet_name, animal_type='dog'):
  # 下⾯对这个函数的所有调⽤都可⾏：

  # ⼀条名为 Willie 的⼩狗
  describe_pet('willie')
  describe_pet(pet_name='willie')
  # ⼀只名为 Harry 的仓⿏
  describe_pet('harry', 'hamster')
  describe_pet(pet_name='harry', animal_type='hamster')
  describe_pet(animal_type='hamster', pet_name='harry')
  ```

### 返回值

- 返回简单的值

  ```python
  def get_formatted_name(first_name, last_name):
      """返回标准格式的姓名"""
      full_name = f"{first_name} {last_name}"
      return full_name.title()
  musician = get_formatted_name('jimi', 'hendrix')
  print(musician)
  ```

- 让实参变成可选的

  可以使⽤默认值来让实参变成可选的。

  ```python
  def get_formatted_name(first_name, last_name, middle_name=''):
      """返回标准格式的姓名"""
      if middle_name:  # Python 将⾮空字符串解读为 True
          full_name = f"{first_name} {middle_name} {last_name}"
      else:
          full_name = f"{first_name} {last_name}"
      return full_name.title()

  musician = get_formatted_name('jimi', 'hendrix')
  print(musician)
  musician = get_formatted_name('john', 'hooker', 'lee')
  print(musician)
  ```

- 返回字典

  ```python
  def build_person(first_name, last_name, age=None):
      """返回⼀个字典，其中包含有关⼀个⼈的信息"""
      person = {'first': first_name, 'last': last_name}
      if age:
          person['age'] = age
      return person

  musician = build_person('jimi', 'hendrix', age=27)
  print(musician)
  ```

  - 在函数定义中，新增了⼀个可选形参 age，其默认值被设置为特殊值 None（表⽰变量没有值）。可将 None 视为占位值。在条件测试中，None 相当于 False.

### 传递列表

- 在函数中修改列表

  ```python
  def print_models(unprinted_designs, completed_models):
      """
      模拟打印每个设计，直到没有未打印的设计为⽌
      打印每个设计后，都将其移到列表 completed_models 中
      """
      while unprinted_designs:
          current_design = unprinted_designs.pop()
          print(f"Printing model: {current_design}")
          completed_models.append(current_design)

  def show_completed_models(completed_models):
      """显⽰打印好的所有模型"""
      print("\nThe following models have been printed:")
      for completed_model in completed_models:
          print(completed_model)

  unprinted_designs = ['phone case', 'robot pendant', 'dodecahedron']
  completed_models = []

  print_models(unprinted_designs, completed_models)
  show_completed_models(completed_models)
  ```

- 禁⽌函数修改列表（ 切片 [ : ] ）

  有时候，需要禁⽌函数修改列表。可向函数传递列表的副本⽽不是原始列表。这样，函数所做的任何修改都只影响副本，⽽丝毫不影响原始列表。

  ```python
  # 要将列表的副本传递给函数，可以像下⾯这样做：
  function_name(list_name[:])
  # 切⽚表⽰法 [:] 创建列表的副本。
  print_models(unprinted_designs[:], completed_models)
  # 在上面的例子中，如果不想清空未打印的设计列表，可像下⾯这样调⽤ print_models()
  ```

  虽然向函数传递列表的副本可保留原始列表的内容，但除⾮有充分的理由，否则还是应该将原始列表传递给函数。这是因为，让函数使⽤现成的列表可避免花时间和内存创建副本，从⽽提⾼效率，在处理⼤型列表时尤其如此。

### 传递任意数量的实参 （*形参 / **形参）

```python
# 下⾯的函数只有⼀个形参 *toppings，不管调⽤语句提供了多少实参，这个形参都会将其收⼊囊中。
def make_pizza(*toppings):
    """打印顾客点的所有配料"""
    print(toppings)
make_pizza('pepperoni')
make_pizza('mushrooms', 'green peppers', 'extra cheese')
# 形参名 *toppings 中的星号让 Python 创建⼀个名为 toppings 的元组，该元组包含函数收到的所有值。

```

- 结合使⽤位置实参和任意数量的实参  
  
  如果要让函数接受不同类型的实参，必须在函数定义中将接纳任意数量实参的形参放在最后。Python 先匹配位置实参和关键字实参，再将余下的实参都收集到最后⼀个形参中。

  ```python
  def make_pizza(size, *toppings):
      """概述要制作的⽐萨"""
      print(f"\nMaking a {size}-inch pizza with the following toppings:")
      for topping in toppings:
          print(f"- {topping}")

  make_pizza(16, 'pepperoni')
  make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
  ```

  注意：你经常会看到通⽤形参名 *args，它也这样收集任意数量的位置实参。

- 使⽤任意数量的关键字实参

  ```python
  def build_profile(first, last, **user_info):
      """创建⼀个字典，其中包含我们知道的有关⽤户的⼀切"""
    ❶ user_info['first_name'] = first
      user_info['last_name'] = last
      return user_info
  user_profile = build_profile('albert', 'einstein',
                               location='princeton',
                               field='physics')
  print(user_profile)
  # 输出
  {'location': 'princeton', 'field': 'physics',
  'first_name': 'albert', 'last_name': 'einstein'}
  ```

  你需要接受任意数量的实参，但预先不知道传递给函数的会是什么样的信息。在这种情况下，可将函数编写成能够接受任意数量的键值对——调⽤语句提供了多少就接受多少。  
  
  形参 **user_info 中的两个星号让 Python 创建⼀个名为 user_info 的字典，该字典包含函数收到的其他所有名对。

  注意：你经常会看到形参名 **kwargs，它⽤于收集任意数量的关键字实参。

### 将函数存储在模块中，再将模块导⼊主程序

- 导⼊整个模块  
  
  只需编写⼀条 import 语句并在其中指定模块名，就可在程序中使⽤该模块中的所有函数。如果使⽤这种 import 语句导⼊了名为 module_name.py 的整个模块，就可使⽤下⾯的语法来使⽤其中的任意⼀个函数。

  ```python
  import module_name
  module_name.function_name()
  ```

  要让函数是可导⼊的，得先创建模块。模块是扩展名为 .py 的⽂件，包含要导⼊程序的代码。下⾯来创建⼀个包含 make_pizza() 函数的模块。

  pizza.py

  ```python
  def make_pizza(size, *toppings):
      """概述要制作的⽐萨"""
      print(f"\nMaking a {size}-inch pizza with the following toppings:")
      for topping in toppings:
          print(f"- {topping}")
  ```

  making_pizzas.py

  ```python
  import pizza

  pizza.make_pizza(16, 'pepperoni')
  pizza.make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')

  ```

  当 Python 读取这个⽂件时，代码⾏ import pizza 会让 Python 打开⽂件pizza.py，并将其中的所有函数都复制到这个程序中。

- 导⼊模块中的特定函数
  
  ```python
  from module_name import function_name
  ```

  ⽤逗号分隔函数名，可根据需要从模块中导⼊任意数量的函数：

  ```python
  from module_name import function_0, function_1, function_2
  ```

  ```python
  from pizza import make_pizza
  make_pizza(16, 'pepperoni')
  make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
  ```
  
  如果使⽤这种语法，在调⽤函数时则⽆须使⽤句点。由于在 import 语句中显式地导⼊了 make_pizza() 函数，因此在调⽤时只需指定其名称即可。

- 使⽤ as 给函数指定别名（alias）
  
  ```python
  from module_name import function_name as fn
  ```

  如果要导⼊的函数的名称太⻓或者可能与程序中既有的名称冲突，可指定简短⽽独⼀⽆⼆的别名。

  ```python
  from pizza import make_pizza as mp
  mp(16, 'pepperoni')
  mp(12, 'mushrooms', 'green peppers', 'extra cheese')
  ```

- 使⽤ as 给模块指定别名
  
  ```python
  import module_name as mn
  ```

  ```python
  import pizza as p
  p.make_pizza(16, 'pepperoni')
  p.make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
  ```

- 导⼊模块中的所有函数（ * ）

  ```python
  from pizza import *
  make_pizza(16, 'pepperoni')
  make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
  ```

  import 语句中的星号让 Python 将模块 pizza 中的每个函数都复制到这个程序⽂件中。由于导⼊了每个函数，可通过名称来调⽤每个函数，⽆须使⽤点号（dot notation）。  
  最好不要用这种发放导入。最佳的做法是，要么只导⼊需要使⽤的函数，要么导⼊整个模块并使⽤点号。

### 函数编写指南

- 应给函数指定描述性名称，且只使⽤⼩写字⺟和下划线。。在给模块命名时也应遵循上述约定。
- 每个函数都应包含简要阐述其功能的注释。该注释应紧跟在函数定义后⾯，并采⽤⽂档字符串的格式。
- 在给形参指定默认值时，等号两边不要有空格：
  
  ```python
  def function_name(parameter_0, parameter_1='default value')

  ```

- 函数调⽤中的关键字实参也应遵循这种约定：

  ```python
  function_name(value_0, parameter_1='value')
  ```

- 如果形参很多，导致函数定义的⻓度超过了 79 个
字符，可在函数定义中输⼊左括号后按回⻋键，并在下⼀⾏连按两次制表符键，从⽽将形参列表和只缩进⼀层的函数体区分开来。

  ```python
  def function_name(
          parameter_0, parameter_1, parameter_2,
          parameter_3, parameter_4, parameter_5):
      function body...
  ```

- 如果程序或模块包含多个函数，可使⽤两个空⾏将相邻的函数分开。
- 所有的 import 语句都应放在⽂件开头。

## 9 类

### 创建和使⽤类创建实例

```python
# 使⽤属性在类中存储信息，编写⽅法让类具备所需的⾏为
class Dog:
    """⼀次模拟⼩狗的简单尝试"""
    def __init__(self, name, age):
    """初始化属性 name 和 age"""
        self.name = name
        self.age = age
    def sit(self):
    """模拟⼩狗收到命令时坐下"""
        print(f"{self.name} is now sitting.")
    def roll_over(self):
    """模拟⼩狗收到命令时打滚"""
        print(f"{self.name} rolled over!")

# 创建实例
my_dog = Dog('Willie', 6)
# 访问属性 my_dog.name
print(f"My dog's name is {my_dog.name}.")
print(f"My dog is {my_dog.age} years old.")
# 调⽤⽅法
my_dog.sit()
my_dog.roll_over()
# 创建多个实例
my_dog = Dog('Willie', 6)
your_dog = Dog('Lucy', 3)
```

```python
__init__() ⽅法  

1.  __init__() 是⼀个特殊⽅法，每当你根据 Dog 类创建新实例时，Python 都会⾃动运⾏它。  
2.  在这个⽅法的名称中，开头和末尾各有两个下划线。  
3.  这个⽅法的定义中，形参 self 必不可少，⽽且必须位于其他形参的前⾯。  
4.  当 Python 调⽤这个⽅法来创建 Dog 实例时，将⾃动传⼊实参 self。每个与实例相关联的⽅法调⽤都会⾃动传递实参 self，该实参是⼀个指向实例本⾝的引⽤，让实例能够访问类中的属性和⽅法。  
5.  在 __init__() ⽅法内定义的两个变量都有前缀 self 。以self 为前缀的变量可供类中的所有⽅法使⽤，可以通过类的任意实例来访问。像这样可通过实例访问的变量称为属性（attribute）。
```  

### 给类的属性指定默认值，修改实例的属性的值

- 给属性指定默认值

  ```python
  # 有些属性⽆须通过形参来定义，可以在 __init__() ⽅法中为其指定默认值
  class Car:
      def __init__(self, make, model, year):
      """初始化描述汽⻋的属性"""
          self.make = make
          self.model = model
          self.year = year
          self.odometer_reading = 0
  ```

- 修改实例的属性的值
  
  - 直接修改属性的值
  
    ```python
    class Car:
        --snip--

    my_new_car = Car('audi', 'a4', 2024)

    my_new_car.odometer_reading = 23
    ```

  - 通过⽅法修改属性的值

    ```python
    class Car:
        --snip--
        def update_odometer(self, mileage):
            """将⾥程表读数设置为指定的值"""
            self.odometer_reading = mileage

    my_new_car = Car('audi', 'a4', 2024)
    my_new_car.update_odometer(23)
    ```

  - 通过⽅法让属性的值递增

    ```python
    class Car:
        --snip--
        def update_odometer(self, mileage):
        --snip--
        def increment_odometer(self, miles):
            """让⾥程表读数增加指定的量"""
            self.odometer_reading += miles
    ```

### 继承  

当⼀个类继承（inheritance）另⼀个类时，将⾃动获得后者的所有属性和⽅法。原有的类称为⽗类（parent class），⽽新类称为⼦类（child class）。⼦类不仅继承了⽗类的所有属性和⽅法，还可定义⾃⼰的属性和⽅法

- ⼦类的 init() ⽅法

  ```python
  class Car:
      """⼀次模拟汽⻋的简单尝试"""

      def __init__(self, make, model, year):
          """初始化描述汽⻋的属性"""
          self.make = make
          self.model = model
          self.year = year
          self.odometer_reading = 0

      def get_descriptive_name(self):
          """返回格式规范的描述性名称"""
          long_name = f"{self.year} {self.make} {self.model}"
          return long_name.title()

      def read_odometer(self):
          """打印⼀个句⼦，指出汽⻋的⾏驶⾥程"""
          print(f"This car has {self.odometer_reading} miles on it.")

      def update_odometer(self, mileage):
          """将⾥程表读数设置为给定的值"""
          if mileage >= self.odometer_reading:
              self.odometer_reading = mileage
          else:
              print("You can't roll back an odometer!")

      def increment_odometer(self, miles):
          """让⾥程表读数增加给定的量"""
          self.odometer_reading += miles

  class ElectricCar(Car):
      """电动汽⻋的独特之处"""

      def __init__(self, make, model, year):
          """初始化⽗类的属性"""
          super().__init__(make, model, year)

  my_leaf = ElectricCar('nissan', 'leaf', 2024)
  print(my_leaf.get_descriptive_name()) 
  ```

  - 在创建⼦类时，⽗类必须包含在当前⽂件中，且位于⼦类前⾯。
  - 定义⼦类 ElectricCar。在定义⼦类时，必须在括号内指定⽗类的名称。
  - super() 是⼀个特殊的函数，让你能够调⽤⽗类的⽅法.⽗类也称为超类（superclass）。

- 给⼦类定义属性和⽅法

  ```python
  # 下⾯添加⼀个电动汽⻋特有的属性（电池）
  class Car:
      --snip--

  class ElectricCar(Car):
      """电动汽⻋的独特之处"""
      def __init__(self, make, model, year):
          """
          先初始化⽗类的属性，再初始化电动汽⻋特有的属性
          """
          super().__init__(make, model, year)
          self.battery_size = 40

      def describe_battery(self):
          """打印⼀条描述电池容量的消息"""
          print(f"This car has a {self.battery_size}-kWh battery.")

  my_leaf = ElectricCar('nissan', 'leaf', 2024)
  print(my_leaf.get_descriptive_name())
  my_leaf.describe_battery()
  ```

- 重写⽗类中的⽅法

  - 在⼦类中定义⼀个与要重写的⽗类⽅法同名的⽅法。这样，Python 将忽略这个⽗类⽅法，只关注你在⼦类中定义的相应⽅法。

- 将⼀个类的实例⽤作另⼀个类的属性

  ```python
  class Car:
      --snip--

  class Battery:
      """⼀次模拟电动汽⻋电池的简单尝试"""
  ❶    def __init__(self, battery_size=40):
            """初始化电池的属性"""
            self.battery_size = battery_size

  ❷     def describe_battery(self):
            """打印⼀条描述电池容量的消息"""
            print(f"This car has a {self.battery_size}-kWh battery.")

  class ElectricCar(Car):
      """电动汽⻋的独特之处"""
      def __init__(self, make, model, year):
          """
          先初始化⽗类的属性，再初始化电动汽⻋特有的属性
          """
          super().__init__(make, model, year)
  ❸       self.battery = Battery()

   my_leaf = ElectricCar('nissan', 'leaf', 2024)
   print(my_leaf.get_descriptive_name())
   my_leaf.battery.describe_battery()
  ```

  - 将⼤型类拆分成多个协同⼯作的⼩类，这种⽅法称为组合（composition）。
  - 在 ElectricCar 类中，添加⼀个名为 self.battery 的属性（⻅❸）。这⾏代码让 Python 创建⼀个新的 Battery 实例（因为没有指定容量，所以为默认值 40），并将该实例赋给属性 self.battery。
  - 每当__init__() ⽅法被调⽤时，都将执⾏该操作，因此现在每个ElectricCar 实例都包含⼀个⾃动创建的 Battery 实例。

  ```python
  my_leaf.battery.describe_battery()
  ```

  - 这⾏代码让 Python 在实例 my_leaf 中查找属性 battery，并对存储在该属性中的 Battery 实例调⽤ describe_battery() ⽅法。

### 导⼊类

- 导⼊单个类

  my_car.py

  ```python
  from car import Car

  my_new_car = Car('audi', 'a4', 2024)
  print(my_new_car.get_descriptive_name())

  my_new_car.odometer_reading = 23
  my_new_car.read_odometer()
  ```

- 从⼀个模块中导⼊多个类  
  
  在⼀个模块中能存储多个类，可根据需要导入所需的类。
  
  ```python
   from car import Car, ElectricCar
  ```

- 导⼊整个模块  
  
  还可以先导⼊整个模块，再使⽤点号访问需要的类。  
  由于创建类实例的代码都包含模块名，因此不会与当前⽂件使⽤的任何名称发⽣冲突。

  ```python
  import car
  # 使⽤语法module_name.classname 访问需要的类
  my_mustang = car.Car('ford', 'mustang', 2024)
  print(my_mustang.get_descriptive_name())

  my_leaf = car.ElectricCar('nissan', 'leaf', 2024)
  print(my_leaf.get_descriptive_name())
  ```

- 导⼊模块中的所有类
  
  ```python
  # 不推荐这种导⼊⽅式
  from module_name import *
  ```

- 在⼀个模块中导⼊另⼀个模块
  
  在将类存储在多个模块中时，你可能会发现⼀个模块中的类依赖于另⼀个模块中的类。在这种情况下，可在前⼀个模块中导⼊必要的类。

  car.py

  ```python
  """⼀个可⽤于表⽰汽⻋的类"""
  class Car:
      --snip--
  ```

  electric_car.py

  ```python
  """⼀组可⽤于表⽰电动汽⻋的类"""
  from car import Car
  class Battery:
      --snip--
  class ElectricCar(Car):
      --snip--
  # ElectricCar 类需要访问其⽗类 Car，因此直接将 Car 类导⼊该模块。
  ```

  my_cars.py

  ```python
  from car import Car
  from electric_car import ElectricCar

  my_mustang = Car('ford', 'mustang', 2024)
  print(my_mustang.get_descriptive_name())

  my_leaf = ElectricCar('nissan', 'leaf', 2024)
  print(my_leaf.get_descriptive_name())
  # 输出
  2024 Ford Mustang
  2024 Nissan Leaf
  ```

- 使⽤别名

  ```python
  # 给类指定别名。
  from electric_car import ElectricCar as EC

  my_leaf = EC('nissan', 'leaf', 2024)
  ```

  ```python
  # 给模块指定别名。
  import electric_car as ec

  my_leaf = ec.ElectricCar('nissan', 'leaf', 2024)
  ```

### Python 标准库  

  Python 标准库是⼀组模块，在安装 Python 时已经包含在内。你可以使⽤标准库中的任何函数和类，只需在程序开头添加⼀条简单的 import 语句即可。

### 类的编程⻛格

- 类名应采⽤驼峰命名法，即将类名中的每个单词的⾸字⺟都⼤写，并且不使⽤下划线。
- 实例名和模块名都采⽤全⼩写格式，并在单词之间加上下划线。
- 在类中，可以使⽤⼀个空⾏来分隔⽅法；⽽在模块中，可以使⽤两个空⾏来分隔类。

## 10 ⽂件和异常

### 读取⽂件（ path对象 . read_text() ）

```python
# 读取⽂件的全部内容
from pathlib import Path

path = Path('pi_digits.txt')
contents = path.read_text()
print(contents)
# 相⽐于原始⽂件，该输出唯⼀不同的地⽅是末尾多了⼀个空⾏。因为 read_text() 在到达⽂件末尾时会返回⼀个空字符串，⽽这个空字符串会被显⽰为⼀个空⾏。
# 要删除这个多出来的空⾏，可对字符串变量 contents 调⽤ rstrip()：
contents = path.read_text().rstrip()
# 这⾏代码先让 Python 对当前处理的⽂件调⽤ read_text() ⽅法，再对read_text() 返回的字符串调⽤ rstrip() ⽅法，然后将整理好的字符串赋给变量 contents。这种做法称为⽅法链式调⽤（method chaining）
```

- 相对⽂件路径让 Python 到相对于当前运⾏的程序所在⽬录的指定位置去查找。

  ```python
  # 由于⽂件夹 text_files 位于⽂件夹 python_work 中，因此需要创建⼀个以 text_files 打头并以⽂件名结尾的路径，如下所⽰：
  path = Path('text_files/filename.txt')
  # 绝对路径通常⽐相对路径⻓，因为它们以系统的根⽂件夹为起点
  path = Path('/home/eric/data_files/text_files/filename.txt')
  ```

- 访问⽂件中的各⾏

  使⽤ splitlines() ⽅法返回⼀个列表，其中包含⽂件中所有的⾏，再使⽤for 循环以每次⼀⾏的⽅式检查⽂件中的各⾏。

  ```python
  from pathlib import Path

  path = Path('pi_digits.txt')
  contents = path.read_text()
  lines = contents.splitlines()
  for line in lines:
      print(line)
  ```

- 使⽤⽂件的内容
  
  ```python
  from pathlib import Path

  path = Path('pi_digits.txt')
  contents = path.read_text()

  lines = contents.splitlines()
  pi_string = ''
  for line in lines:
      pi_string += line

  print(pi_string)
  print(len(pi_string))
  ```

  - 注意：在读取⽂本⽂件时，Python 将其中的所有⽂本都解释为字符串。如果读取的是数，并且要将其作为数值使⽤，就必须使⽤ int()函数将其转换为整数，或者使⽤ float() 函数将其转换为浮点数。

### 写⼊⽂件（ path对象 . write_text() ）

- 写⼊⼀⾏

  ```python
  from pathlib import Path
  # write_text() ⽅法接受单个实参，即要写⼊⽂件的字符串。
  path = Path('programming.txt')
  path.write_text("I love programming.")
  ```

  - 注意：Python 只能将字符串写⼊⽂本⽂件。如果要将数值数据存储到⽂本⽂件中，必须先使⽤函数 str() 将其转换为字符串格式。

- 写⼊多⾏

  ```python
  from pathlib import Path
  # 可以通过添加空格、制表符和空⾏来设置输出的格式
  contents = "I love programming.\n"
  contents += "I love creating new games.\n"
  contents += "I also love working with data.\n"

  path = Path('programming.txt')
  path.write_text(contents)

  # 文本文件内容：
  I love programming.
  I love creating new games.
  I also love working with data.
  ```

  - 注意：在对 path 对象调⽤ write_text() ⽅法时，务必谨慎。如果指定的⽂件已存在， write_text() 将删除其内容，并将指定的内容写⼊其中。本章后⾯将介绍如何使⽤ pathlib 检查指定的⽂件是否存在。

### 异常
  
- Python 使⽤称为异常（exception）的特殊对象来管理程序执⾏期间发⽣的错误。
  
- 每当发⽣让 Python 不知所措的错误时，它都会创建⼀个异常对象。如果你编写了处理该异常的代码，程序将继续运⾏；如果你未对异常进⾏处理，程序将停⽌，并显⽰⼀个 traceback，其中包含有关异常的报告。
  
- 异常是使⽤ try-except 代码块处理的。
  
- try-except 代码块让 Python执⾏指定的操作，同时告诉 Python 在发⽣异常时应该怎么办。在使⽤try-except 代码块时，即便出现异常，程序也将继续运⾏：显⽰你编写的友好的错误消息，⽽不是令⽤户迷惑的 traceback。

#### 使⽤ try-except 代码块

只有可能引发异常的代码才需要放在 try 语句中。except 代码块告诉 Python，如果在尝试运⾏ try 代码块中的代码时引发了指定的异常该怎么办。

```python
try:
    print(5/0)
except ZeroDivisionError:
    print("You can't divide by zero!")
# 这⾥将导致错误的代码⾏ print(5/0) 放在⼀个 try 代码块中。
#如果 try 代码块中的代码运⾏起来没有问题，Python 将跳过 except 代码块；
#如果try 代码块中的代码导致错误，Python 将查找与之匹配的 except 代码块并运⾏其中的代码。
```

#### else 代码块

只有 try代码块成功执⾏才需要继续执⾏的代码，都应放到 else 代码块中。

```python
--snip--
while True:
    --snip--
    if second_number == 'q':
        break
    try:
        answer = int(first_number) / int(second_number)
    except ZeroDivisionError:
        print("You can't divide by 0!")
    else:
        print(answer)
```

- 静默失败 （ pass ）

  出现异常时，虽然仍将执⾏except 代码块中的代码，但什么都不会发⽣。。当这种错误发⽣时，既不会出现 traceback，也没有任何输出。

  ```python
  def count_words(path):
      """计算⼀个⽂件⼤致包含多少个单词"""
      try:
          --snip--
      except FileNotFoundError:
          pass
      else:
          --snip--
  ```

#### 常见的异常类型有

- StopIteration - 迭代器没有更多的值
- ImportError - 导入模块失败
- IndexError - 序列中找不到给定的索引
- KeyError - 映射中找不到给定的键
- ValueError - 传入无效的参数
- TypeError - 对类型无效的操作
- FileNotFoundError - 未找到文件
- KeyboardInterrupt - 用户中断执行

### 使⽤模块 json 来存储数据

- 模块 json 让你能够将简单的 Python 数据结构转换为 JSON 格式的字符串，并在程序再次运⾏时从⽂件中加载数据。
  
- 使⽤ json.dumps() 和 json.loads()
  
  number_writer.py

  ```python
  # json.dumps() 函数接受⼀个实参，即要转换为 JSON 格式的数据。这个函数返回⼀个字符串，这样你就可将其写⼊数据⽂件了
  from pathlib import Path
  import json

  numbers = [2, 3, 5, 7, 11, 13]

  path = Path('numbers.json')
  contents = json.dumps(numbers)
  path.write_text(contents)
  #输出
  [2, 3, 5, 7, 11, 13]
  ```

  number_reader.py

```python
from pathlib import Path
import json

path = Path('numbers.json')
contents = path.read_text()
numbers = json.loads(contents)

print(numbers)
#输出
[2, 3, 5, 7, 11, 13]
```

### 重构

remember_me.py

```python
from pathlib import Path
import json

def greet_user():
    """问候⽤户，并指出其名字"""
    path = Path('username.json')
    if path.exists():
        contents = path.read_text()
        username = json.loads(contents)
        print(f"Welcome back, {username}!")
    else:
        username = input("What is your name? ")
        contents = json.dumps(username)
        path.write_text(contents)
        print(f"We'll remember you when you come back, {username}!")

greet_user()
```

remember_me.py 最终版（每个函数都执⾏单⼀⽽清晰的任务）

```python
from pathlib import Path
import json

def get_stored_username(path):
    """如果存储了⽤户名，就获取它"""
    --snip--

def get_new_username(path):
    """提⽰⽤户输⼊⽤户名"""
    username = input("What is your name? ")
    contents = json.dumps(username)
    path.write_text(contents)
    return username

def greet_user():
    """问候⽤户，并指出其名字"""
    path = Path('username.json')
    username = get_stored_username(path)
    if username:
        print(f"Welcome back, {username}!")
    else:
        username = get_new_username(path)
        print(f"We'll remember you when you come back, {username}!")

 greet_user()
```

## 11 使⽤ pytest 工具库测试代码

### 使⽤ pip 安装 pytest

- 更新 pip

  ```python
  python -m pip install --upgrade pip
  # 这个命令的第⼀部分（python -m pip）让 Python 运⾏ pip 模块；
  #第⼆部分（install --upgrade）让 pip 更新⼀个已安装的包；
  #⽽最后⼀部分（pip）指定要更新哪个第三⽅包。
  ```

  可使⽤下⾯的命令更新系统中安装的任何包：

  ```python
   python -m pip install --upgrade package_name
  ```

- 安装 pytest

  ```python
  python -m pip install --user pytest
  # --user 这个标志让 Python 只为当前⽤户安装指定的包。
  ```

  可使⽤下⾯的命令安装众多的第三⽅包：

  ```python
   python -m pip install --user package_name
  ```

  注意：如果在执⾏这个命令时遇到⿇烦，可尝试在不指定标志 --user 的情况下再次执⾏它。

### 测试函数

name_function.py

```python
def get_formatted_name(first, last):
    """⽣成格式规范的姓名"""
    full_name = f"{first} {last}"
    return full_name.title()
```

names.py

```python
from name_function import get_formatted_name

print("Enter 'q' at any time to quit.")
while True:
    first = input("\nPlease give me a first name: ")
    if first == 'q':
        break
    last = input("Please give me a last name: ")
    if last == 'q':
        break
    formatted_name = get_formatted_name(first, last)
    print(f"\tNeatly formatted name: {formatted_name}.")
```

测试⽤例（test case）是⼀组单元测试（unit test）。  
全覆盖（full coverage）测试⽤例包含⼀整套单元测试，涵盖了各种可能的函数使⽤⽅式。

test_name_function.py（测试）

```python
# 编写⼀个测试函数，它会调⽤要测试的函数，并做出有关返回值的断⾔。
# 如果断⾔正确，表⽰测试通过；如果断⾔不正确，表⽰测试未通过。
from name_function import get_formatted_name

def test_first_last_name():
    """能够正确地处理像 Janis Joplin 这样的姓名吗？"""
    formatted_name = get_formatted_name('janis', 'joplin')
    assert formatted_name == 'Janis Joplin'
```

- 测试⽂件的名称很重要，必须以test_打头。当你让 pytest 运⾏测试时，它将查找以 test_打头的⽂件，并运⾏其中的所有测试。
- 测试函数必须以 test_打头。在测试过程中，pytest 将找出并运⾏所有以 test_ 打头的函数。且函数名要具有描述性。

### 运⾏测试

打开⼀个终端窗⼝，并切换到这个测试⽂件所在的⽂件夹。如果你使⽤的是 VS Code，可打开测试⽂件所在的⽂件夹，并使⽤该编辑器内嵌的终端。在终端窗⼝中执⾏命令 pytest，你将看到如下输出：

```python
$ pytest
 ========================= test session starts
=========================
❶ platform darwin -- Python 3.x.x, pytest-7.x.x, pluggy-1.x.x
❷ rootdir: /.../python_work/chapter_11
❸ collected 1 item
❹ test_name_function.py . 
[100%]
 ========================== 1 passed in 0.00s
==========================
```

### 测试类

- 测试中常⽤的断⾔语句
  
  | 断⾔                        |   ⽤途                    |
  |-----------------------------|--------------------------|
  | assert a == b               | 断⾔两个值相等            |
  | assert a != b               | 断⾔两个值不等            |
  | assert a                    | 断⾔ a 的布尔求值为 True  |
  | assert not a                | 断⾔ a 的布尔求值为 False |
  | assert element in list      | 断⾔元素在列表中          |
  | assert element not in list  | 断⾔元素不在列表中        |

survey.py

```python
class AnonymousSurvey:
    """收集匿名调查问卷的答案"""

    def __init__(self, question):
        """存储⼀个问题，并为存储答案做准备"""
        self.question = question
        self.responses = []

    def show_question(self):
        """显⽰调查问卷"""
        print(self.question)

    def store_response(self, new_response):
        """存储单份调查答卷"""
        self.responses.append(new_response)

    def show_results(self):
        """显⽰收集到的所有答卷"""
        print("Survey results:")
        for response in self.responses:
        print(f"- {response}")
```

test_survey.py

```python
from survey import AnonymousSurvey

def test_store_single_response():
    """测试单个答案会被妥善地存储"""
    question = "What language did you first learn to speak?"
    language_survey = AnonymousSurvey(question)
    language_survey.store_response('English')
    assert 'English' in language_survey.responses

def test_store_three_responses():
    """测试三个答案会被妥善地存储"""
    question = "What language did you first learn to speak?"
    language_survey = AnonymousSurvey(question)
    responses = ['English', 'Spanish', 'Mandarin']

    for response in responses:
        language_survey.store_response(response)

    for response in responses:
        assert response in language_survey.responses
```

如果在执⾏命令 pytest 时没有指定任何参数，pytest 将运⾏它在当前⽬录中找到的所有测试。为了专注于⼀个测试⽂件，可将该测试⽂件的名称作为参数传递给 pytest。

```python
$ pytest test_survey.py
========================= test session starts =========================
--snip--
test_survey.py .. [100%]
========================== 2 passed in 0.01s ==========================
```

### 使⽤夹具

```python
import pytest
from survey import AnonymousSurvey

@pytest.fixture
def language_survey():
    """⼀个可供所有测试函数使⽤的 AnonymousSurvey 实例"""
    question = "What language did you first learn to speak?"
    language_survey = AnonymousSurvey(question)
    return language_survey

def test_store_single_response(language_survey):
    """测试单个答案会被妥善地存储"""
    language_survey.store_response('English')
    assert 'English' in language_survey.responses

def test_store_three_responses(language_survey):
    """测试三个答案会被妥善地存储"""
    responses = ['English', 'Spanish', 'Mandarin']
    for response in responses:
        language_survey.store_response(response)

    for response in responses:
        assert response in language_survey.responses
```

- 在测试中，夹具（fixture）可帮助我们搭建测试环境。这通常意味着创建供多个测试使⽤的资源。
- 在 pytest 中，要创建夹具，可编写⼀个使⽤装饰器 @pytest.fixture 装饰的函数。装饰器（decorator）是放在函数定义前⾯的指令。在运⾏函数前，Python 将该指令应⽤于函数，以修改函数代码的⾏为。
- 当测试函数的⼀个形参与应⽤了装饰器 @pytest.fixture 的函数（夹具）同名时，将⾃动运⾏夹具，并将夹具返回的值传递给测试函数。
- 在这个⽰例中，language_survey() 函数向 test_store_single_response() 和 test_store_three_responses() 提供了⼀个 language_survey 实例。
- 在想要使⽤夹具时，可编写⼀个函数来⽣成供多个测试函数使⽤的资源，再对这个函数应⽤装饰器 @pytest.fixture，并让使⽤该资源的每个测试函数都接受⼀个与该函数同名的形参。这样，测试将更简洁，编写和维护起来也将更容易。
