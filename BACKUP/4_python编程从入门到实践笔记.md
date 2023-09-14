# [python编程从入门到实践笔记](https://github.com/hadleysu/gitblog/issues/4)

# python编程从入门到实践笔记

## 2 变量和简单的数据类型

* [Is Python interpreted or compiled? Yes.](https://nedbatchelder.com/blog/201803/is_python_interpreted_or_compiled_yes.html)

* 变量(variable)：变量是可以被赋值的标签，也可以说变量指向特定的值(value)。
  * 变量的命名：变量名只能包含字⺟、数字和下划线 。变量名能以字⺟或下划线打头，但不能以数字打头。变量名不能包含空格，但能使⽤下划线来分隔其中的单词。
  * 注意：应使⽤⼩写的 Python 变量名。全大写定义常量。
* 字符串(string)：。在 Python 中，⽤引号引起的都是字符串，其中的引号可以是单引号，也可以是双引号.
  * 使⽤⽅法修改字符串的⼤⼩写:
  
    ```python
    name = "ada lovelace"
    print(name.title()) # title() ⽅法以⾸字⺟⼤写的⽅式显⽰每个单词
    name = "Ada Lovelace"
    print(name.upper()) # upper() 方法以全大写显示字符串
    print(name.lower()) # lower() 方法以全小写显示字符串
    ```

  * f 字符串：将要插⼊的变量放在花括号内
  
    ```python
    first_name = "ada"
    last_name = "lovelace"
    full_name = f"{first_name} {last_name}"
    print(full_name)
    print(f"Hello, {full_name.title()}!")
    # 这种字符串称为 f 字符串。f 是 format（设置格式）的简写，因为 Python 通过把花括号内的变量替换为其值来设置字符串的格式。
    ```

  * 使⽤制表符或换⾏符来添加空⽩
  
    ```python
    # 制表符 \t ; 换行符 \n ;
    >>> print("Languages:\n\tPython\n\tC\n\tJavaScript")
    Languages:
        Python
        C
        JavaScript
    ```

  * 删除空⽩
  
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

  * 删除前缀
  
    ```python
    # removeprefix() ⽅法
    >>> nostarch_url = 'https://nostarch.com'
    >>> nostarch_url.removeprefix('https://')
    'nostarch.com'
    # 如果想保留删除前缀后的值，既可将其重新赋给原来的变量，也可将其赋给另⼀个变量
    >>> simple_url = nostarch_url.removeprefix('https://')
    ```

* 数(number)
  * 整数(integer)
  
    ```python
    # Python 使⽤两个乘号（**）表⽰乘⽅运算
    >>> 3 ** 2
    9
    ```

  * 浮点数(float)
  
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

  * 数中的下划线
  
    ```python
    # 为在存储这种数时，Python 会忽略其中的下划线。在对数字位分组时，即便不是将每三位分成⼀组，也不会影响最终的值。
    >>> universe_age = 14_000_000_000
    >>> print(universe_age)
    14000000000
    # 这种表⽰法既适⽤于整数，也适⽤于浮点数。
    ```

  * 常数(constant)：是在程序的整个⽣命周期内都保持不变的变量。其变量名全⼤写。

    ```python
    MAX_CONNECTIONS = 5000
    ```

* 注释(comment)：注释⽤井号（#）标识。批量注释CTRL + /
  
## 3 列表简介

* 列表(list)：由⼀系列按特定顺序排列的元素组成。在 Python 中，⽤⽅括号（[]）表⽰列表，⽤逗号分隔其中的元素。
  * Python 为访问最后⼀个列表元素提供了⼀种特殊语法。通过将索引指定为-1，可让 Python 返回最后⼀个列表元素。

    ```python
    bicycles = ['trek', 'cannondale', 'redline', 'specialized']
    print(bicycles[-1])
    # 这些代码返回 'specialized'。
    ```

  * 这种语法很有⽤，因为你经常需要在不知道列表⻓度的情况下访问最后的元素。这种约定也适⽤于其他负数索引，例如，索引 -2 返回倒数第⼆个列表元素，索引 -3 返回倒数第三个列表元素，依此类推。

* 修改、添加和删除元素
  * 修改列表元素

    ```python
    motorcycles = ['honda', 'yamaha', 'suzuki']
    print(motorcycles)
    motorcycles[0] = 'ducati'
    print(motorcycles)
    ```

  * 在列表中添加元素
    * 在列表末尾添加元素
  
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

    * 在列表中插⼊元素

      ```python
      # 使⽤ insert() ⽅法可在列表的任意位置添加新元素。
      motorcycles = ['honda', 'yamaha', 'suzuki']
      motorcycles.insert(0, 'ducati')
      print(motorcycles)
      #这种操作将列表中的每个既有元素都右移⼀个位置。
      ['ducati', 'honda', 'yamaha', 'suzuki']
      ```

  * 从列表中删除元素
    * 使⽤ del 语句删除元素

      ```python
      #如果知道要删除的元素在列表中的位置，可使⽤ del 语句
      #使⽤ del 可删除任意位置的列表元素，只需要知道其索引即可。
      motorcycles = ['honda', 'yamaha', 'suzuki']
      print(motorcycles)
      del motorcycles[1]
      print(motorcycles)
      ```

    * 使⽤ pop() ⽅法删除元素
  
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

    * 删除列表中任意位置的元素
  
      ```python
      # 也可以使⽤ pop() 删除列表中任意位置的元素，只需要在括号中指定要删除的元素的索引即可。
      motorcycles = ['honda', 'yamaha', 'suzuki']
      first_owned = motorcycles.pop(0)
      print(f"The first motorcycle I owned was a {first_owned.title()}.")
      # ⾸先弹出列表中的第⼀款摩托⻋，然后打印⼀条有关这辆摩托⻋的消息。
      The first motorcycle I owned was a Honda.
      # 如果不确定该使⽤ del 语句还是 pop() ⽅法，下⾯是⼀个简单的判断标准：如果要从列表中删除⼀个元素，且不再以任何⽅式使⽤它，就使⽤ del 语句；如果要在删除元素后继续使⽤它，就使⽤ pop() ⽅法。
      ```
  
    * 根据值删除元素
  
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

* 管理列表
  * 使⽤ sort() ⽅法对列表进⾏永久排序
  
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

  * 使⽤ sorted() 函数对列表进⾏临时排序

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

  * 反向打印列表

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

  * 确定列表的⻓度

    ```python
    # 使⽤ len() 函数可快速获悉列表的⻓度。
    >>> cars = ['bmw', 'audi', 'toyota', 'subaru']
    >>> len(cars)
    4
    # 注意：Python 在计算列表元素数时从 1 开始，因此你在确定列表⻓度时应该不会遇到差⼀错误。
    ```

* 使⽤列表时避免索引错误
  
   ```python
    # 仅当列表为空时，这种访问最后⼀个元素的⽅式才会导致错误：
    motorcycles = []
    print(motorcycles[-1])
    # 列表 motorcycles 不包含任何元素，因此 Python 返回⼀条索引错误消息：
    Traceback (most recent call last):
      File "motorcyles.py", line 3, in <module>
        print(motorcycles[-1])
              ~~~~~~~~~~~^^^^
    IndexError: list index out of range
    # 注意：在发⽣索引错误却找不到解决办法时，请尝试将列表或其⻓度打印出来。列表可能与你以为的截然不同，在程序对其进⾏了动态处理时尤其如此。查看列表或其包含的元素数，可帮助你排查这种逻辑错误。
    ```
