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



