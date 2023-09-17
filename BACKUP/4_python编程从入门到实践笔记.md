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
  - [管理列表 \[ sort(),sorted(),len() \]](#管理列表--sortsortedlen-)
  - [使⽤列表时避免索引错误](#使列表时避免索引错误)
- [4 操作列表](#4-操作列表)
  - [遍历整个列表（for）](#遍历整个列表for)
  - [避免缩进错误](#避免缩进错误)
  - [创建数值列表 \[ list(range()) \]](#创建数值列表--listrange-)
  - [使用列表的一部分（切片）](#使用列表的一部分切片)
  - [元组](#元组)
  - [设置代码格式](#设置代码格式)
- [5 if语句](#5-if语句)
  - [条件测试（布尔表达式）](#条件测试布尔表达式)
  - [if 语句/ if-else 语句/ if-elif-else 语句](#if-语句-if-else-语句-if-elif-else-语句)
  - [使⽤ if 语句处理列表](#使-if-语句处理列表)
- [6 字典](#6-字典)

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

### 管理列表 [ sort(),sorted(),len() ]

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

### 创建数值列表 [ list(range()) ]

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

## 5 if语句

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
  - 对于数值 0、空值 None、单引号空字符串 ''、双引号空字符串 ""、空列表 []、空元组 ()、空字典 {}，Python 都会返回 False。

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

- 


