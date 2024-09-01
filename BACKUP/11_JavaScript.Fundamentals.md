# [JavaScript Fundamentals](https://github.com/hadleysu/gitblog/issues/11)

# JavaScript Fundamentals

- [JavaScript Fundamentals](#javascript-fundamentals)
  - [**WHAT IS JAVASCRIPT?**](#what-is-javascript)
  - [**THE ROLE OF JAVASCRIPT IN WEB DEVELOPMENT**](#the-role-of-javascript-in-web-development)
  - [**WHAT CAN WE DO WITH JAVASCRIPT**](#what-can-we-do-with-javascript)
  - [**JAVASCRIPT RELEASES**](#javascript-releases)
  - [**Values and Variables**](#values-and-variables)
    - [**1. 概念**](#1-概念)
    - [**2. 变量的声明与赋值**](#2-变量的声明与赋值)
    - [**3. 命名规则**](#3-命名规则)
    - [**4. 常见错误**](#4-常见错误)
    - [**5. 变量作用域**](#5-变量作用域)
    - [**6. 深入理解**](#6-深入理解)
    - [**7. 相关练习题**](#7-相关练习题)
    - [**8. 复习小结**](#8-复习小结)
  - [**Data Types**](#data-types)
    - [**1. 概念**](#1-概念-1)
    - [**2. 原始数据类型（Primitive Data Types）**](#2-原始数据类型primitive-data-types)
    - [**3. 引用数据类型（Reference Data Types）**](#3-引用数据类型reference-data-types)
    - [**4. 数据类型的特性**](#4-数据类型的特性)
    - [**5. 动态类型（Dynamic Typing）**](#5-动态类型dynamic-typing)
    - [**6. 与 Java 的对比**](#6-与-java-的对比)
    - [**7. "Value has type, NOT variable!" 的理解**](#7-value-has-type-not-variable-的理解)
    - [**8. 类型检测**](#8-类型检测)
    - [**9. 常见错误**](#9-常见错误)
    - [**10. 相关练习题**](#10-相关练习题)
    - [**11. 复习小结**](#11-复习小结)
  - [**let, const and var**](#let-const-and-var)
    - [**1. 概念**](#1-概念-2)
    - [**2. 作用域（Scope）**](#2-作用域scope)
    - [**3. 变量提升（Hoisting）**](#3-变量提升hoisting)
    - [**4. 可变性和不可变性（Mutability / Immutability）**](#4-可变性和不可变性mutability--immutability)
    - [**5. 选择使用 `let`、`const` 还是 `var`**](#5-选择使用-letconst-还是-var)
    - [**6. 注意事项与常见错误**](#6-注意事项与常见错误)
    - [**7. 代码示例总结**](#7-代码示例总结)
    - [**8. 复习与总结**](#8-复习与总结)
  - [**Basic Operators**](#basic-operators)
    - [**1. 概念**](#1-概念-3)
    - [**2. 算术运算符（Arithmetic Operators）**](#2-算术运算符arithmetic-operators)
    - [**3. 字符串与数字混合运算**](#3-字符串与数字混合运算)
    - [**4. 赋值运算符（Assignment Operators）**](#4-赋值运算符assignment-operators)
    - [**5. 比较运算符（Comparison Operators）**](#5-比较运算符comparison-operators)
    - [**6. 逻辑运算符（Logical Operators）**](#6-逻辑运算符logical-operators)
    - [**7. 字符串运算符（String Operators）**](#7-字符串运算符string-operators)
    - [**8. 其他常见操作符**](#8-其他常见操作符)
    - [**9. 运算符优先级（Operator Precedence）**](#9-运算符优先级operator-precedence)
    - [**10. 注意事项与常见错误**](#10-注意事项与常见错误)
    - [**11. 练习题与总结**](#11-练习题与总结)
  - [**Operator Precedence**](#operator-precedence)
    - [**1. 概念介绍**](#1-概念介绍)
    - [**2. 操作符优先级表**](#2-操作符优先级表)
    - [**3. 示例代码**](#3-示例代码)
    - [**4. 注意事项**](#4-注意事项)
    - [**5. 练习题**](#5-练习题)
    - [**6. 复习小结**](#6-复习小结)
  - [**Strings and Template Literals**](#strings-and-template-literals)
    - [**1. 概念简介**](#1-概念简介)
    - [**2. 字符串的创建和操作**](#2-字符串的创建和操作)
    - [**3. 模板字面量（Template Literals）**](#3-模板字面量template-literals)
    - [**4. 常见操作**](#4-常见操作)
    - [**5. 注意事项**](#5-注意事项)
    - [**6. 相关练习题**](#6-相关练习题)
    - [**7. 复习小结**](#7-复习小结)
  - [**Taking Decisions: if / else Statements**](#taking-decisions-if--else-statements)
    - [**1. 概念介绍**](#1-概念介绍-1)
    - [**2. 注意事项**](#2-注意事项)
    - [**3. 复习小结**](#3-复习小结)
  - [**Type Conversion and Coercion**](#type-conversion-and-coercion)
    - [**1.  概念简介**](#1--概念简介)
    - [**2. Type Conversion（显式类型转换）**](#2-type-conversion显式类型转换)
    - [**3. Type Coercion（隐式类型强制转换）**](#3-type-coercion隐式类型强制转换)
    - [**4. 实践示例**](#4-实践示例)
    - [**5.  注意事项**](#5--注意事项)
    - [**6. 练习题**](#6-练习题)
    - [**7. 复习小结**](#7-复习小结-1)
  - [**Truthy and Falsy Values**](#truthy-and-falsy-values)
    - [**1. 概念**](#1-概念-4)
    - [**2. 常见的 Falsy 值**](#2-常见的-falsy-值)
    - [**3. 常见的 Truthy 值**](#3-常见的-truthy-值)
    - [**4. Boolean的隐式转换和使用场景**](#4-boolean的隐式转换和使用场景)
      - [**When exactly does JavaScript do type coercion to booleans?**](#when-exactly-does-javascript-do-type-coercion-to-booleans)
    - [**5. 实践示例**](#5-实践示例)
    - [**6. 注意事项**](#6-注意事项)
    - [**7. 练习题**](#7-练习题)
    - [**8. 复习小结**](#8-复习小结-1)
    - [**9. 适用场景**](#9-适用场景)
  - [**Equality Operators: == vs. ===**](#equality-operators--vs-)
    - [**1. 概念**](#1-概念-5)
    - [**2. 操作符的区别**](#2-操作符的区别)
    - [**3. 适用场景**](#3-适用场景)
    - [**4. 实践练习**](#4-实践练习)
    - [**5. 复习小结**](#5-复习小结)
  - [**The switch Statement**](#the-switch-statement)
    - [**1. 概念理解**](#1-概念理解)
    - [**2. 基本语法**](#2-基本语法)
    - [**3. 实践例子**](#3-实践例子)
    - [**4. 注意事项**](#4-注意事项-1)
    - [**5. 适用场景**](#5-适用场景)
    - [**6. 与 `if...else` 的对比**](#6-与-ifelse-的对比)
    - [**7. 常见错误**](#7-常见错误)
    - [**8. 复习小结**](#8-复习小结-2)
  - [**The Conditional (Ternary) Operator**](#the-conditional-ternary-operator)
    - [**1. 概念理解**](#1-概念理解-1)
    - [**2. 基本语法**](#2-基本语法-1)
    - [**3. Ternary Operator 与 Template Literals 的结合**](#3-ternary-operator-与-template-literals-的结合)
    - [**4. Statements 与 Expressions 的区别**](#4-statements-与-expressions-的区别)
    - [**5. 常见错误**](#5-常见错误)
    - [**6. 相关练习题**](#6-相关练习题-1)
    - [**7. 复习小结**](#7-复习小结-2)
  - [**Activating Strict Mode**](#activating-strict-mode)
    - [**1. 概念理解**](#1-概念理解-2)
    - [**2. 启用 Strict Mode**](#2-启用-strict-mode)
    - [**3. 严格模式的优势**](#3-严格模式的优势)
    - [**4. 注意事项**](#4-注意事项-2)
    - [**5. 实践例子**](#5-实践例子)
    - [**6. 相关练习题**](#6-相关练习题-2)
    - [**7. 复习小结**](#7-复习小结-3)
  - [**Functions**](#functions)
    - [**1. 概念理解**](#1-概念理解-3)
    - [**2. 函数的声明与表达式**](#2-函数的声明与表达式)
      - [2.1. **函数声明（Function Declaration）**](#21-函数声明function-declaration)
      - [2.2. **函数表达式（Function Expression）**](#22-函数表达式function-expression)
      - [2.3. **箭头函数（Arrow Function）**](#23-箭头函数arrow-function)
    - [**3. 函数参数**](#3-函数参数)
      - [3.1. **默认参数（Default Parameters）**](#31-默认参数default-parameters)
      - [3.2. **参数解构（Destructuring Parameters）**](#32-参数解构destructuring-parameters)
    - [**4. 函数的返回值**](#4-函数的返回值)
    - [**5. 函数的作用域与闭包**](#5-函数的作用域与闭包)
      - [5.1. **作用域（Scope）**](#51-作用域scope)
      - [5.2. **闭包（Closure）**](#52-闭包closure)
    - [**6. 常见问题与注意事项**](#6-常见问题与注意事项)
    - [**7. 相关练习题**](#7-相关练习题-1)
    - [**8. 复习小结**](#8-复习小结-3)
  - [**Basic Array Operations (Methods)**](#basic-array-operations-methods)
    - [1. **概念概述**](#1-概念概述)
    - [2. **创建数组**](#2-创建数组)
    - [3. **基本数组操作**](#3-基本数组操作)
      - [**3.1. 添加和删除元素**](#31-添加和删除元素)
      - [**3.2. 查找和索引操作**](#32-查找和索引操作)
      - [**3.3. 数组遍历**](#33-数组遍历)
    - [4. **数组方法的应用场景**](#4-数组方法的应用场景)
    - [5. **实际案例**](#5-实际案例)
    - [6. **练习题**](#6-练习题-1)
    - [7. **复习总结**](#7-复习总结)
  - [**Objects**](#objects)
    - [1. **概念概述**](#1-概念概述-1)
    - [2. **创建对象**](#2-创建对象)
    - [3. **对象属性操作**](#3-对象属性操作)
    - [4. **对象的方法**](#4-对象的方法)
    - [5. **对象的遍历**](#5-对象的遍历)
    - [6. **对象的复制与合并**](#6-对象的复制与合并)
    - [7. **实际应用场景**](#7-实际应用场景)
    - [8. **练习题**](#8-练习题)
    - [9. **复习总结**](#9-复习总结)
  - [**Object Methods**](#object-methods)
    - [**1. 定义：**](#1-定义)
    - [**2. 创建方法：**](#2-创建方法)
    - [**3. `this` 关键字：**](#3-this-关键字)
    - [**4. 简写方法语法：**](#4-简写方法语法)
    - [**5. 使用对象方法：**](#5-使用对象方法)
    - [**6. 常见应用场景：**](#6-常见应用场景)
    - [**7. 复习小结：**](#7-复习小结-4)
    - [**8. 相关练习题：**](#8-相关练习题)
  - [**Loops**](#loops)
    - [**1. 概念概述**](#1-概念概述-2)
    - [**2. 常见的循环类型**](#2-常见的循环类型)
      - [**2.1. `for` 循环**](#21-for-循环)
      - [**2.2. `while` 循环**](#22-while-循环)
      - [**2.3. `do...while` 循环**](#23-dowhile-循环)
      - [**2.4. `for...in` 循环**](#24-forin-循环)
      - [**2.5. `for...of` 循环**](#25-forof-循环)
    - [**3. 循环控制**](#3-循环控制)
      - [**3.1. `break` 语句**](#31-break-语句)
      - [**3.2. `continue` 语句**](#32-continue-语句)
    - [**4. 嵌套循环**](#4-嵌套循环)
    - [**5. 循环中的作用域和性能**](#5-循环中的作用域和性能)
    - [**6. 实际案例**](#6-实际案例)
    - [**7. 练习题**](#7-练习题-1)
    - [**8. 复习总结**](#8-复习总结)

## **WHAT IS JAVASCRIPT?**

JAVASCRIPT IS A HIGH-LEVEL, OBJECT-ORIENTED, MULTI-PARADIGM PROGRAMMING LANGUAGE.

- `PROGRAMMING LANGUAGE` --> Instruct computer to do things

- `HIGH-LEVEL` --> We don’t have to worry about complex stuff like memory management
  
- `OBJECT-ORIENTED` --> Based on objects, for storing most kinds of data

- `MULTI-PARADIGM` --> We can use different styles of programming

## **THE ROLE OF JAVASCRIPT IN WEB DEVELOPMENT**

- `HTML` --> CONTENT --> `NOUNS`
  
  ```HTML
  <p></p>
  ```

- `CSS` --> PRESENTATION --> `ADJECTIVES`

  ```CSS
  p {color : red}
  ```

- `JS` --> PROGRAMMING LANGUAGE : BUILDING WEB APPLICATIONS --> `VERBS`

  ```javascript
  p.hide();
  ```
  
## **WHAT CAN WE DO WITH JAVASCRIPT**

- Dynamic effects and web applications in the browser
- Web applications on web servers ( through Node.js )
- Native mobile applications
- Native desktop applications

## **JAVASCRIPT RELEASES**

ES5 --> ES6/ES2015 --> ES7/ES2016 ... -->ES11/ES2020 ... -->ES2024

ES6 发布于2015年，增加了重要的新特性。从 ES6 开始，ECMAScript 规范改为每年发布一次，每次都将增加新特性。

## **Values and Variables**

### **1. 概念**

- **Value（值）** 是程序中存储的数据，可以是数字、字符串、布尔值等。
- **Variable（变量）** 是用来存储值的容器，值可以在程序执行过程中改变。

### **2. 变量的声明与赋值**

JavaScript 中变量可以使用 `let`、`const` 和 `var` 来声明。[**let, const and var**](#let-const-and-var)

```javascript
let age = 30;         // 声明一个可以改变的变量
const birthYear = 1993; // 声明一个不可改变的变量
var job = 'programmer'; // 使用 var 声明变量（老式写法）
```

### **3. 命名规则**

- 变量名必须以字母、下划线 `_` 或美元符号 `$` 开头。
- 不能以数字开头。
- 驼峰命名法（例如 `herFirstName`）。
- 变量名应该具有描述性（例如 `firstName`），以便代码更易读。

### **4. 常见错误**

- **使用未声明的变量**: 在使用变量前必须先声明，否则会抛出 `ReferenceError`。
  
    ```javascript
    console.log(name); // ReferenceError: name is not defined
    ```

- **重新赋值 `const` 变量**: `const` 声明的变量一旦赋值后不能再更改。

    ```javascript
    const birthYear = 1993;
    birthYear = 1990; // TypeError: Assignment to constant variable.
    ```

- **变量名区分大小写**: `firstName` 和 `firstname` 是不同的变量。
  
    ```javascript
    let firstName = 'John';
    let firstname = 'Jane';
    console.log(firstName); // John
    console.log(firstname); // Jane
    ```

### **5. 变量作用域**

- **局部变量**: 在函数或代码块中声明的变量只在该范围内有效。
  
    ```javascript
    function greet() {
        let message = 'Hello!';
        console.log(message); // 'Hello!'
    }
    console.log(message); // ReferenceError: message is not defined
    ```

- **全局变量**: 在函数外部声明的变量可以在整个程序中访问。
  
    ```javascript
    let greeting = 'Hi!';
    function greet() {
        console.log(greeting); // 'Hi!'
    }
    greet();
    ```

### **6. 深入理解**

- **Hoisting（提升）**: `var` 声明的变量会被提升到作用域的顶部，但只有声明会被提升，赋值不会。因此，可能会导致意外行为。
  
    ```javascript
    console.log(job); // undefined
    var job = 'developer';
    ```

    使用 `let` 和 `const` 的变量不会被提升，因此最好使用它们来避免 `hoisting` 带来的潜在问题。

### **7. 相关练习题**

```javascript
// 练习题 1: 结果是什么？
let country = 'Japan';
country = 'France';
console.log(country); // ?

// 练习题 2: 结果是什么？
const city = 'Tokyo';
city = 'Osaka'; // ?

// 练习题 3: 结果是什么？
console.log(year);
var year = 2024; // ?
```

### **8. 复习小结**

- 使用 `let` 和 `const` 来声明变量，避免使用 `var` 。
- 确保变量名具有描述性，以提高代码可读性。
- 注意 `hoisting` 行为，避免在声明前使用变量。

## **Data Types**

### **1. 概念**

**Data Types（数据类型）** 是指不同种类的值在编程语言中的表示方式。JavaScript 中的数据类型分为两大类：原始类型（Primitive Data Types）和引用类型（Reference Data Types）。

### **2. 原始数据类型（Primitive Data Types）**

原始类型是不可变的，主要包括以下几种：

- **Number**: 用于表示整数和浮点数。

    ```javascript
    let age = 25;
    let temperature = 36.6;
    ```

- **String**: 用于表示文本数据，用单引号 `'`、双引号 `"` 或反引号 `` ` `` 包裹。

    ```javascript
    let firstName = 'John';
    let greeting = "Hello, world!";
    let multiLine = `This is
    a multiline string.`;
    ```

- **Boolean**: 用于表示真（`true`）或假（`false`）。
  
    ```javascript
    let isJavaScriptFun = true;
    ```

- **Undefined**: 当变量声明了但未赋值时，值为 `undefined`。
  
    ```javascript
    let year;
    console.log(year); // undefined
    ```

- **Null**: 表示一个空值，手动赋值为 `null` 以表示“无”。
  
    ```javascript
    let emptyValue = null;
    ```

- **Symbol**: 用来创建独一无二的值，通常用于对象属性的标识符。
  
    ```javascript
    let uniqueId = Symbol('id');
    ```

- **BigInt**: 用于表示大整数，可以超出 `Number` 类型的最大安全整数限制。
  
    ```javascript
    let bigNumber = 1234567890123456789012345678901234567890n;
    ```

### **3. 引用数据类型（Reference Data Types）**

引用类型主要包括对象、数组和函数，它们是可变的。

- **Object**: 一组键值对的集合，可以包含任意类型的数据。
  
    ```javascript
    let person = {
        name: 'Alice',
        age: 30,
        job: 'Developer'
    };
    ```

- **Array**: 有序的值的集合，可以包含不同类型的数据。
  
    ```javascript
    let colors = ['red', 'green', 'blue'];
    ```

- **Function**: 用来封装可复用的代码块。
  
    ```javascript
    function greet(name) {
        return `Hello, ${name}!`;
    }
    ```

### **4. 数据类型的特性**

- **原始类型的不可变性**: 原始类型的值一旦创建，就不能被改变。即使修改了变量的值，实际上是将变量指向了一个新的值，而不是修改了原始的值。例如：

    ```javascript
    let greeting = 'Hello';
    greeting[0] = 'h'; // 尝试修改字符串的第一个字符（无效）
    console.log(greeting); // 'Hello'

    greeting = 'Hi'; // 重新赋值，这是创建了一个新的字符串，而不是修改原来的 'Hello'
    ```

    这里的关键是，**变量的类型** 并不固定，但**值的类型** 是固定的。当你改变 `greeting` 变量的值时，实际上是重新分配了一个新的字符串给这个变量，而不是修改原有的字符串。
  
- **引用类型的可变性**: 引用类型的数据可以在创建后被修改。
  
    ```javascript
    let arr = [1, 2, 3];
    arr[0] = 10; // 修改数组的第一个元素
    ```

### **5. 动态类型（Dynamic Typing）**

JavaScript 是一种动态类型语言，变量的数据类型可以在运行时改变。虽然变量本身没有固定的类型，但变量当前所持有的值是有类型的。例如：

```javascript
let dynamicVar = 'Hello'; // 现在是字符串
dynamicVar = 42; // 现在是数字
dynamicVar = true; // 现在是布尔值
```

这里的重点是，**变量是动态的**，可以在不同的时间点持有不同类型的值。这种灵活性是 JavaScript 的一个特性，但也可能导致类型错误，因此要谨慎使用。

### **6. 与 Java 的对比**

在 Java 中，**变量的类型是固定的**，即在声明时就必须指定，并且在整个生命周期内不会改变。例如：

```java
int number = 42;
number = "Hello"; // 错误：不能将字符串赋值给 int 类型的变量
```

这里的 `number` 变量一开始是 `int` 类型，所以它只能存储 `int` 类型的值，不能存储其他类型的值。这与 JavaScript 的动态类型形成了鲜明的对比。

### **7. "Value has type, NOT variable!" 的理解**

这句话的意思是，在 JavaScript 中，**值的类型是固定的**，而**变量的类型是动态的**。即使变量可以随时改变所持有的值的类型，但一旦某个值被创建，它的类型就是确定的，不可改变的。例如：

```javascript
let value = 10; // 10 是一个 number 类型的值
value = 'Hello'; // 'Hello' 是一个 string 类型的值
```

在这个例子中，`value` 这个变量可以先保存 `number` 类型的值，然后再保存 `string` 类型的值。但 **10** 一直是 `number` 类型，而 **'Hello'** 一直是 `string` 类型。

### **8. 类型检测**

使用 `typeof` 操作符来检查变量的数据类型。

```javascript
console.log(typeof 42);        // 'number'
console.log(typeof 'hello');   // 'string'
console.log(typeof true);      // 'boolean'
console.log(typeof undefined); // 'undefined'
console.log(typeof null);      // 'object' (JavaScript的一个bug)
console.log(typeof {});        // 'object'
console.log(typeof Symbol());  // 'symbol'
console.log(typeof 123n);      // 'bigint'
```

### **9. 常见错误**

- 原始类型的不可变性和动态类型并不冲突。它们是两个不同的概念，分别解决不同的问题：
  
  - **不可变性** 是关于具体值的性质，即这些值本身一旦创建就不能被修改。例如，一个字符串 `'Hello'` 不能通过修改其内容变成 `'Hella'`。

  - **动态类型** 是关于变量的性质，指的是变量可以在不同类型的值之间切换。例如，一个变量可以先存储数字，再存储字符串，最后存储布尔值。
  
  - **总结：** 原始类型的不可变性意味着你不能直接修改这些类型的值，但你可以通过重新赋值来改变变量存储的值。动态类型则意味着变量可以存储不同类型的值。这两者之间并不矛盾，而是各自独立的概念。
  
- **null 和 undefined 的区别**: `null` 是手动赋值的空值，`undefined` 是变量未赋值时的默认值。
- **NaN 的来源**: 执行无法解析为数值的数学操作会产生 `NaN` (Not a Number)。
  
    ```javascript
    let result = 'hello' * 2;
    console.log(result); // NaN
    ```

### **10. 相关练习题**

通过练习题进一步理解数据类型。

```javascript
// 练习题 1: 结果是什么？
console.log(typeof null); // ?

// 练习题 2: 结果是什么？
let value;
console.log(typeof value); // ?

// 练习题 3: 结果是什么？
let bigNum = 123456789012345678901234567890n;
console.log(typeof bigNum); // ?
```

### **11. 复习小结**

- 理解原始类型和引用类型的区别，知道何时使用何种类型。
- 了解 JavaScript 的动态类型特性及其带来的灵活性和潜在问题。
- 熟练使用 `typeof` 操作符进行类型检测。
- 理解“Value has type, NOT variable!” 的含义，即值的类型是固定的，而变量的类型是动态的。
- NaN的来源。

## **let, const and var**

### **1. 概念**

- **`var`**: 最早引入的变量声明方式，具有函数作用域和变量提升特性。
- **`let`**: ES6 中引入的块级作用域变量声明方式，取代 `var` 的使用。
- **`const`**: ES6 中引入的块级作用域常量声明方式，声明后不能重新赋值。

### **2. 作用域（Scope）**

- **`var` 的函数作用域**: `var` 声明的变量仅在函数内部有效，如果在函数外部声明，则是全局变量。
  
    ```javascript
    function example() {
        var x = 10;
        if (true) {
            var x = 20; // 这里的 var x 与外面的 var x 是同一个变量
            console.log(x); // 20
        }
        console.log(x); // 20
    }
    ```
  
- **`let` 和 `const` 的块级作用域**: `let` 和 `const` 声明的变量仅在它们声明的块（如 `{}` 内）中有效。
  
    ```javascript
    function example() {
        let y = 10;
        if (true) {
            let y = 20; // 这里的 y 是一个新的变量，作用范围只在这个块内
            console.log(y); // 20
        }
        console.log(y); // 10
    }
    ```

### **3. 变量提升（Hoisting）**

- **`var` 的变量提升**: 使用 `var` 声明的变量会在作用域顶部被提升，但不会初始化。
  
    ```javascript
    console.log(z); // undefined
    var z = 5;
    console.log(z); // 5
    ```

- **`let` 和 `const` 的暂时性死区（Temporal Dead Zone）**: `let` 和 `const` 声明的变量不会被提升，在声明之前使用会导致错误。
  
    ```javascript
    console.log(a); // ReferenceError: a is not defined
    let a = 5;
    ```

### **4. 可变性和不可变性（Mutability / Immutability）**

- **`const` 的不可变性**: `const` 声明的变量一旦被赋值，就不能再被重新赋值。但如果变量保存的是一个对象或数组，这个对象或数组本身是可以改变的。
  
    ```javascript
    const num = 42;
    num = 50; // TypeError: Assignment to constant variable.
    
    const arr = [1, 2, 3];
    arr.push(4); // 合法：可以修改数组内容
    console.log(arr); // [1, 2, 3, 4]
    ```

- **let 和 var 的可变性**:`let` 、 `var` 声明的变量是可变的，可以随时重新赋值。

### **5. 选择使用 `let`、`const` 还是 `var`**

- **推荐使用 `let` 和 `const`**: 由于 `var` 存在作用域和变量提升问题，通常推荐使用 `let` 和 `const`。其中，`const` 用于声明不会改变的常量，而 `let` 用于声明会重新赋值的变量。
- **变量声明习惯**: 开发中尽量使用 `const`，只有在需要重新赋值的情况下使用 `let`。

### **6. 注意事项与常见错误**

- **避免使用 `var`**: 使用 `var` 可能引入难以追踪的作用域问题，因此应尽量避免。
- **理解 `const` 的不可变性**: 仅禁止重新赋值，允许对象内部修改，因此要小心使用对象或数组。

### **7. 代码示例总结**

- `var` 的变量提升和函数作用域：
  
    ```javascript
    var x = 10;
    function example() {
        console.log(x); // undefined
        var x = 20;
        console.log(x); // 20
    }
    example();
    ```

- `let` 和 `const` 的块级作用域和暂时性死区：
  
    ```javascript
    let y = 10;
    if (true) {
        let y = 20;
        console.log(y); // 20
    }
    console.log(y); // 10
    
    console.log(a); // ReferenceError
    let a = 5;
    ```

- `const` 的对象内部可变性：
  
    ```javascript
    const person = { name: 'Alice' };
    person.name = 'Bob'; // 合法
    console.log(person.name); // 'Bob'

    person = {}; // TypeError: Assignment to constant variable.
    ```

### **8. 复习与总结**

- 尽量避免使用 `var`，推荐使用 `let` 和 `const`。
- 在需要重新赋值时使用 `let`，而在不可变的情况下使用 `const`。
- 理解变量提升的行为以及不同作用域带来的影响，写出更安全的代码。

## **Basic Operators**

### **1. 概念**

**运算符（Operators）** 是用于在程序中执行某种操作的符号。JavaScript 中的基本运算符可以分为以下几类：算术运算符、赋值运算符、比较运算符、逻辑运算符、字符串运算符和条件运算符（也称三元运算符）等。

### **2. 算术运算符（Arithmetic Operators）**

用于执行数学计算的运算符。

- **加法（`+`）**: 用于两个数值相加，也可用于字符串拼接。

- **减法（`-`）**: 用于减去两个数值。

- **乘法（`*`）**: 用于两个数值相乘。

- **除法（`/`）**: 用于两个数值相除。
  
- **取模（`%`）**: 用于取两个数值相除后的余数。

- **幂运算（`**`）**: 用于计算一个数值的幂次方。

### **3. 字符串与数字混合运算**

```javascript
//加法运算 --> 当操作数之一是字符串时，JavaScript 会将另一个操作数也转换为字符串，然后进行连接。
let result1 = '5' + 3;
console.log(result1); // '53' (数字 3 被转换为字符串 '3')

let result2 = 3 + '5';
console.log(result2); // '35' (数字 3 被转换为字符串 '3')

let result3 = '5' + 3 + 2;
console.log(result3); // '532' (从左到右，'5' + 3 变成 '53'，然后 '53' + 2 变成 '532')

//减法 --> 都会将字符串转换为数字，然后进行运算。乘法、除法、指数运算、取余运算同上。
let result1 = '5' - 3;
console.log(result1); // 2 (字符串 '5' 被转换为数字 5)

let result2 = '10' - '2';
console.log(result2); // 8 (两个字符串都被转换为数字)

let result3 = '5' - 'hello';
console.log(result3); // NaN (字符串 'hello' 无法转换为数字)
```

- **总结**：在 JavaScript 中，字符串与数字混合运算时，通常会将字符串尝试转换为数字进行运算。如果字符串不能被成功转换为数字，结果通常会是 `NaN`（Not a Number）。唯一的例外是 `+` 操作符，因为它也可以用于字符串连接，因此会优先进行字符串连接而不是数值计算。

### **4. 赋值运算符（Assignment Operators）**

用于将值赋给变量。

- **基本赋值（`=`）**: 将右边的值赋给左边的变量。

- **复合赋值**: 。
  
    ```javascript
    x += 5; // 等同于 x = x + 5; 现在 x 的值是 15
    x -= 2; // 等同于 x = x - 2; 现在 x 的值是 13
    x *= 3; // 等同于 x = x * 3; 现在 x 的值是 39
    x /= 3; // 等同于 x = x / 3; 现在 x 的值是 13
    x %= 2; // 等同于 x = x % 2; 现在 x 的值是 1
    x **= 2; // 等同于 x = x ** 2; 现在 x 的值是 1
    ```

### **5. 比较运算符（Comparison Operators）**

用于比较两个值并返回布尔值（`true` 或 `false`）。

- **等于（`==`）和严格等于（`===`）**:
  
    ```javascript
    let isEqual = (5 == '5'); // true（仅比较值，允许类型转换）
    let isStrictEqual = (5 === '5'); // false（比较值和类型，不允许类型转换）
    ```

- **不等于（`!=`）和严格不等于（`!==`）**:
  
    ```javascript
    let isNotEqual = (5 != '5'); // false
    let isStrictNotEqual = (5 !== '5'); // true
    ```

- **大于（`>`）**、**小于（`<`）**、**大于等于（`>=`）**、**小于等于（`<=`）**: 用于数值比较。

### **6. 逻辑运算符（Logical Operators）**

用于布尔值的组合。

- **与（`&&`）**: 仅当两个操作数都为 `true` 时返回 `true`。
  
- **或（`||`）**: 只要有一个操作数为 `true` 就返回 `true`。
  
- **非（`!`）**: 取反运算符，将布尔值反转。
  
### **7. 字符串运算符（String Operators）**

- **拼接运算符（`+`）**: 用于连接字符串。
  
    ```javascript
    let fullName = 'John' + ' ' + 'Doe'; // "John Doe"
    ```

- **赋值拼接（`+=`）**: 将字符串拼接并赋值给变量。
  
    ```javascript
    let text = 'Hello';
    text += ' world'; // "Hello world"
    ```

### **8. 其他常见操作符**

- 条件运算符/三元运算符（`? :`）: 用于根据条件返回不同的值。

  - **语法**: `condition ? expr1 : expr2`
  
    ```javascript
    let age = 18;
    let isAdult = age >= 18 ? 'Yes' : 'No'; // "Yes"
    ```

- 类型操作符 (`typeof`):
  
  ```javascript
  let type = typeof 42; // 'number'
  ```

- 删除操作符 (`delete`):
  
  ```javascript
  let person = { name: 'John', age: 30 };
  delete person.age; // 删除对象的 age 属性
  ```

### **9. 运算符优先级（Operator Precedence）**

运算符的优先级决定了表达式中各运算符的计算顺序。可以通过括号明确优先顺序。[Operator Precedence](#operator-precedence)

### **10. 注意事项与常见错误**

- **相等和严格相等的区别**: `==` 允许类型转换，而 `===` 不允许，因此通常推荐使用 `===` 来避免意外的类型转换。
  
- **运算符优先级**: 在复杂表达式中，运算符的优先级可能导致意外结果，建议使用括号明确优先级。

### **11. 练习题与总结**

- **练习题**:
  
    ```javascript
    // 练习题 1: 结果是什么？
    let result = 5 + '1'; // ?
    
    // 练习题 2: 结果是什么？
    let isEven = 4 % 2 === 0; // ?
    
    // 练习题 3: 结果是什么？
    let x = true || false && !true; // ?
    ```

- **总结**:
  - 理解并熟练使用各种基本运算符。
  - 理解运算符优先级，合理使用括号控制运算顺序。
  - 注意 `==` 和 `===` 的区别，避免不必要的类型转换。
  - 避免常见的字符串与数字混合运算中的错误。

## **Operator Precedence**

### **1. 概念介绍**

**Operator Precedence（操作符优先级）** 是指在表达式中多个操作符共存时，操作符的执行顺序。优先级较高的操作符会比优先级较低的操作符先执行。

- 操作符优先级决定了表达式中各个部分的计算顺序。
- 操作符还可以结合使用，其中有结合性（Associativity）的概念，指的是在相同优先级下，操作符的计算顺序（从左至右或从右至左）。

### **2. 操作符优先级表**

- [MDN Operator Precedence Table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence)

| **优先级** | **操作符**                   | **描述**                              | **结合性**      |
| ---------- | ----------------------------| ------------------------------------- | --------------- |
| 1          | `()`                        | 括号：显式地指定运算顺序                | N/A             |
| 2          | `!`、`++`、`--`             | 单目运算符：逻辑非、递增、递减等操作符   | N/A             |
| 3          | `**`                        | 指数运算                              | 右到左 (RTL)     |
| 4          | `*`、`/`、`%`               | 乘法、除法、取余                       | 左到右 (LTR)    |
| 5          | `+`、`-`                    | 加法、减法                            | 左到右 (LTR)    |
| 6          | `<`、`<=`、`>`、`>=`         | 比较操作符：用于比较大小               | 左到右 (LTR)    |
| 7          | `==`、`!=`、`===`、`!==`     | 等值/非等值操作符：用于比较相等性       | 左到右 (LTR)    |
| 8          | `&&`                        | 逻辑与：当且仅当两个操作数均为 `true` 时，结果为 `true` | 左到右 (LTR)    |
| 9          | `\|\|`                     | 逻辑或：只要有一个操作数为 `true`，结果就为 `true` | 左到右 (LTR)    |
| 10          | `=`                        | 赋值操作符：优先级最低，用于赋值        | 右到左 (RTL)    |

### **3. 示例代码**

在理解操作符优先级时，使用具体的代码示例可以帮助巩固知识。

```javascript
let a = 10 > 5 && 8 < 7;
console.log(a); // 11，因为比较运算符的优先级高于逻辑 &&

let b = (5 + 3) * 2;
console.log(b); // 16，因为括号改变了运算顺序

let c = 5 + 3 > 7;
console.log(c); // true，因为加法的优先级高于比较运算

let d = true || false && !false;
console.log(d); // true，因为逻辑非 (!false) 先执行，然后逻辑与 (&&)，最后是逻辑或 (||)
```

### **4. 注意事项**

- **使用圆括号**：当表达式变得复杂时，为了避免优先级错误，建议使用圆括号明确指示运算顺序。
- **结合性**：当多个操作符优先级相同时，理解结合性能够帮助正确评估表达式的结果。

### **5. 练习题**

通过练习题进一步理解操作符优先级。

```javascript
// 练习题 1: 结果是什么？
let x = 10 + 5 * 2 > 20 || false;
console.log(x); // ?

// 练习题 2: 结果是什么？
let y = !true && false || true;
console.log(y); // ?

// 练习题 3: 结果是什么？
let z = 3 + 4 * 2 / (1 - 5) ** 2;
console.log(z); // ?
```

### **6. 复习小结**

- 理解操作符优先级和结合性对准确评估复杂表达式至关重要。
- 熟练使用圆括号以明确表达式的运算顺序。

## **Strings and Template Literals**

### **1. 概念简介**

**字符串（Strings**）是用于表示文本的基本数据类型。JavaScript 中的字符串可以使用单引号 `'`、双引号 `"` 或反引号 `` ` `` 来定义。

**模板字面量（Template Literals**）是一种新的字符串字面量，用反引号 `` ` `` 包裹，支持多行字符串和嵌入表达式。

```javascript
`string text ${expression} string text`
```

### **2. 字符串的创建和操作**

- **字符串创建**：可以使用单引号、双引号或反引号创建字符串。
  
    ```javascript
    let singleQuote = 'Hello';
    let doubleQuote = "World";
    let templateLiteral = `Hello, World!`;
    ```

- **字符串连接**：使用 `+` 操作符将字符串连接在一起。
  
    ```javascript
    let greeting = 'Hello' + ' ' + 'World';
    console.log(greeting); // "Hello World"
    ```

- **字符串长度**：通过 `.length` 属性获取字符串的长度。
  
    ```javascript
    let name = 'JavaScript';
    console.log(name.length); // 10
    ```

### **3. 模板字面量（Template Literals）**

- **多行字符串**：模板字面量支持多行字符串，无需使用转义字符 `\n`。

    ```javascript
    let multiLine = `This is a
    multiline string`;
    console.log(multiLine);
    // 输出：
    // This is a
    // multiline string
    ```

- **嵌入表达式**：模板字面量支持嵌入 JavaScript 表达式，使用 `${}` 语法。
  
    ```javascript
    let name = 'John';
    let greeting = `Hello, ${name}!`;
    console.log(greeting); // "Hello, John!"
    ```

- **嵌入表达式中的计算**：在 `${}` 中可以直接进行计算或调用函数。

    ```javascript
    let a = 5;
    let b = 10;
    console.log(`The sum of a and b is ${a + b}`); // "The sum of a and b is 15"
    ```

### **4. 常见操作**

- **字符串方法**：如 `.toUpperCase()`、`.toLowerCase()`、`.includes()`、`.startsWith()` 等。
  
    ```javascript
    let str = 'JavaScript';
    console.log(str.toUpperCase()); // "JAVASCRIPT"
    console.log(str.includes('Script')); // true
    ```

- **模板字面量中的函数调用**：你可以在模板字面量中直接调用函数并插入返回值。
  
    ```javascript
    function greet(name) {
        return `Hello, ${name}!`;
    }
    let message = `${greet('Alice')}`;
    console.log(message); // "Hello, Alice!"
    ```

### **5. 注意事项**

- **区别单引号、双引号与反引号**：使用模板字面量（反引号）时，不需要像使用单引号或双引号那样手动转义特殊字符或插入变量。
  
    ```javascript
    let escaped = 'It\'s a nice day';
    let template = `It's a nice day`;
    ```

- **性能考虑**：模板字面量提供了更简洁的语法，但在某些情况下，使用连接操作符 `+` 可能会稍微快一些。

### **6. 相关练习题**

通过练习题进一步理解字符串与模板字面量的使用。

```javascript
// 练习题 1: 使用模板字面量创建一个包含多行文字的字符串。
let multiLineStr = `This is line 1
This is line 2
This is line 3`;

// 练习题 2: 在模板字面量中插入一个表达式，计算 10 + 20 并输出结果。
let result = `The result of 10 + 20 is ${10 + 20}`;
console.log(result); // "The result of 10 + 20 is 30"

// 练习题 3: 使用字符串方法将字符串 "hello" 转换为大写并在模板字面量中输出。
let str = `HELLO`.toLowerCase();
console.log(`The lowercase of HELLO is ${str}`); // "The lowercase of HELLO is hello"
```

### **7. 复习小结**

- 理解字符串的基本操作，包括创建、连接、获取长度等。
- 掌握模板字面量的语法，特别是多行字符串和嵌入表达式的使用方法。

## **Taking Decisions: if / else Statements**

### **1. 概念介绍**

**`if / else` 语句**是用于控制程序流程的基本结构，根据条件的真假来决定是否执行某段代码。它通常用于当需要根据不同条件执行不同代码块时。

### **2. 注意事项**

- **三元运算符**：对于简单的 `if / else` 语句，可以使用三元运算符 `? :` 进行简化。

    ```javascript
    let age = 18;
    let message = age >= 18 ? 'You are an adult.' : 'You are a minor.';
    console.log(message);
    ```

### **3. 复习小结**

- 了解嵌套条件语句和逻辑运算符的应用场景，并熟练使用三元运算符进行简化判断。

## **Type Conversion and Coercion**

### **1.  概念简介**

**Type Conversion（类型转换）** 和 **Type Coercion（类型强制转换）** 是指在 JavaScript 中将一种数据类型转换为另一种类型的过程。

- **Type Conversion**: 是显式的，由开发者手动进行的类型转换。
- **Type Coercion**: 是隐式的，由 JavaScript 在需要时自动进行的类型转换。

### **2. Type Conversion（显式类型转换）**

显式类型转换是指开发者使用内置函数或方法手动将数据从一种类型转换为另一种类型。

- **将数字转换为字符串**：

    ```javascript
    let num = 42;
    let str = String(num); // '42'
    ```

- **将字符串转换为数字**：

    ```javascript
    let str = '3.14';
    let num = Number(str); // 3.14
    let intNum = parseInt(str); // 3
    let floatNum = parseFloat(str); // 3.14
    ```

- **将布尔值转换为字符串**：

    ```javascript
    let bool = true;
    let str = String(bool); // 'true'
    ```

- **将其他类型转换为布尔值**：

    ```javascript
    let num = 0;
    let isZero = Boolean(num); // false
    ```

### **3. Type Coercion（隐式类型强制转换）**

隐式类型强制转换是指 JavaScript 在表达式中自动将不同类型的数据转换为相同类型，以便进行运算或比较。或[在许多情况下会自动将不同类型的值转换为布尔值](#4-boolean的隐式转换和使用场景)，例如，在条件判断中。

- **字符串与数字的混合运算**：

    ```javascript
    let result = '5' + 10; // '510' (数字被转换为字符串)
    let result2 = '5' * 2; // 10 (字符串被转换为数字)
    ```

- **布尔值与数字的混合运算**：

    ```javascript
    let result = true + 2; // 3 (true 被转换为 1)
    let result2 = false + 10; // 10 (false 被转换为 0)
    ```

- **比较操作中的类型强制转换**：

    ```javascript
    let result = '10' == 10; // true (字符串被转换为数字)
    let result2 = '10' === 10; // false (不同类型，不转换)
    ```

### **4. 实践示例**

- **显式类型转换**：

    ```javascript
    let inputYear = '1991';
    let birthYear = Number(inputYear); // 1991
    console.log(birthYear + 10); // 2001
    ```

- **隐式类型强制转换**：

    ```javascript
    console.log('I am ' + 23 + ' years old'); // 'I am 23 years old'
    console.log('23' - '10' - 3); // 10
    console.log('23' * '2'); // 46
    console.log('23' / '2'); // 11.5
    ```

### **5.  注意事项**

- **避免混淆类型**：使用 `==` 时要小心，因为它会进行类型强制转换，可能导致意外结果。建议使用 `===` 来避免类型强制转换。
  
    ```javascript
    console.log('0' == 0); // true
    console.log('0' === 0); // false
    ```

- **了解 `NaN` 的来源**：执行无法解析为数值的操作会导致 `NaN`（Not a Number）。

    ```javascript
    let result = 'hello' * 2;
    console.log(result); // NaN
    ```

### **6. 练习题**

通过练习题进一步理解类型转换和强制转换的应用。

```javascript
// 练习题 1: 结果是什么？
console.log('5' + 10); // ?

// 练习题 2: 结果是什么？
console.log('5' - '2'); // ?

// 练习题 3: 结果是什么？
console.log(true + '1'); // ?
```

### **7. 复习小结**

- 理解并掌握显式和隐式类型转换的区别及应用场景。
- 注意类型强制转换带来的潜在问题，尤其是在比较操作中。
- 通过练习加深对字符串、数字、布尔值等类型之间的转换理解。

## **Truthy and Falsy Values**

### **1. 概念**

在 JavaScript 中，任何值都可以被转换为布尔值 `true` 或 `false`。

- **Truthy 值**: 在布尔上下文中会被认为是 `true` 的值。
- **Falsy 值**: 在布尔上下文中会被认为是 `false` 的值。

### **2. 常见的 Falsy 值**

JavaScript 中有以下 6 种 Falsy 值：

- **`false`**: 布尔值 `false` 本身。

- **`0`**: 数字零。

- **`''` 或 `""`**: 空字符串。

- **`null`**: 表示空值或无效的对象引用。

- **`undefined`**: 当变量未定义或未赋值时的默认值。

- **`NaN`**: 表示“不是一个数字”的特殊数值。

### **3. 常见的 Truthy 值**

除了以上列出的 Falsy 值，所有其他值都被认为是 Truthy，包括：

- **非空字符串**：任何包含字符的字符串。

- **非零数字**：正数、负数、浮点数等。

- **`true`**: 布尔值 `true` 本身。

- **对象和数组**：即使是空对象 `{}` 和空数组 `[]` 也是 Truthy 值。

### **4. Boolean的隐式转换和使用场景**

在实际操作中，JavaScript 中的布尔值转换通常是[隐式](#type-conversion-and-coercion)的（无需使用 `Boolean()` 函数进行显式类型转换），即 JavaScript 会自动将不同类型的值转换为布尔值（例如，在条件判断中）. (So in practice,the conversion to boolean is always implicit,not explixit,or in other words is always typed coercion that JavaScript does automatically behind the scenes.)

#### **When exactly does JavaScript do type coercion to booleans?**

- **使用逻辑操作符时**:
  - 例如在使用 `&&`（逻辑与）、`||`（逻辑或）、`!`（逻辑非）时，JavaScript 会自动将值转换为布尔值。
  
- **在逻辑上下文中**:
  - 例如在 `if / else` 语句的条件中，JavaScript 会将条件表达式隐式地转换为布尔值。

### **5. 实践示例**

- **判断值是否为 Falsy**：

    ```javascript
    let values = [0, '', null, undefined, NaN, false];
    values.forEach(value => {
        if (!value) {
            console.log(`${value} is Falsy`);
        }
    });
    ```

- **JavaScript强制类型转换为Boolean**：

    ```javascript
    let value = '0';
    console.log(!!value); // true
    ```

### **6. 注意事项**

- **避免 Falsy 值误判**: 某些值（如 `0` 和 `''`）虽然是有效数据，但在布尔上下文中会被视为 `false`。要注意在条件判断中使用这些值时可能出现的逻辑错误。
  
    ```javascript
    let height = 0; 
    if (height){
        console.log("Height is defined");
    }else{
        console.log("Height is UNDEFINED);
    }
    //当height 赋值 0 时，这是一个有效的数据，但因为数字 0 是falsy值，将直接执行else语句，导致bug.
    ```

- **严格等于 (`===`) 的使用**：使用严格等于运算符可以避免类型强制转换带来的潜在问题。

    ```javascript
    let value = '0';
    if (value === 0) {
        console.log('This will not print.');
    }
    ```

### **7. 练习题**

通过练习题进一步理解 Truthy 和 Falsy 值的应用。

```javascript
// 练习题 1: 结果是什么？
let value = ' ';
console.log(!!value); // ?

// 练习题 2: 结果是什么？
let value = [];
console.log(!!value); // ?

// 练习题 3: 结果是什么？
let value = '0';
console.log(!!value); // ?
```

### **8. 复习小结**

- 牢记 JavaScript 中的 6 种 Falsy 值。熟练判断哪些值为 Truthy。

- 认识到布尔值的转换在 JavaScript 中通常是隐式进行的，即 JavaScript 会在后台自动进行这种类型转换。

- 熟悉 if / else 语句和逻辑操作符中的类型强制转换行为，知道何时 JavaScript 会自动将值转换为布尔值。

- 通过实战练习加深理解，避免潜在的逻辑错误。

### **9. 适用场景**

- 业务场景

  - **1. 表单验证场景**

    **使用 `Truthy` 和 `Falsy` 值**

    在表单验证中，通常需要检查输入是否为空。如果输入为空字符串、`null` 或 `undefined`，我们可以直接使用 `if (inputValue)` 来判断：

    ```javascript
    let inputValue = ""; // 用户未填写内容

    if (inputValue) {
      console.log("Valid input");
    } else {
      console.log("Input is empty");
    }
    ```

    **没有 `Truthy` 和 `Falsy` 值时的代码**

    如果 JavaScript 没有 `Truthy` 和 `Falsy` 值的概念，我们就需要显式地检查所有可能的空值情况：

    ```javascript
    let inputValue = ""; // 用户未填写内容

    if (inputValue !== "" && inputValue !== null && inputValue !== undefined) {
      console.log("Valid input");
    } else {
      console.log("Input is empty");
    }
    ```

    **对比分析**

    有了 `Truthy` 和 `Falsy` 值的机制后，代码更加简洁，只需要一个简单的 `if` 语句即可。而如果没有这一机制，则需要对所有可能的“空”值进行显式判断，代码更加冗长，也更容易出错。

  - **2. 用户认证场景**

    **使用 `Truthy` 和 `Falsy` 值**

    在用户认证时，通常需要检查用户对象是否存在：

    ```javascript
    let user = null; // 用户未登录

    if (user) {
      console.log("User is logged in");
    } else {
      console.log("User is not logged in");
    }
    ```

    **没有 `Truthy` 和 `Falsy` 值时的代码**

    如果没有 `Truthy` 和 `Falsy` 值，我们需要显式检查 `user` 是否为 `null` 或 `undefined`：

    ```javascript
    let user = null; // 用户未登录

    if (user !== null && user !== undefined) {
      console.log("User is logged in");
    } else {
      console.log("User is not logged in");
    }
    ```

    **对比分析**

    有了 `Truthy` 和 `Falsy` 值的机制后，用户认证的代码逻辑变得更加简洁，减少了显式检查 `null` 和 `undefined` 的复杂性。

- 技术场景

  - **1. 默认参数场景**

    **使用 `Truthy` 和 `Falsy` 值**

    在函数中为参数设置默认值时，可以利用 `||` 运算符来简化代码：

    ```javascript
    function greet(name) {
      name = name || "Guest";
      console.log(`Hello, ${name}!`);
    }

    greet(); // "Hello, Guest!"
    ```

    **没有 `Truthy` 和 `Falsy` 值时的代码**

    如果没有 `Truthy` 和 `Falsy` 值，我们需要显式检查参数是否为 `undefined`：

    ```javascript
    function greet(name) {
      if (name === undefined) {
        name = "Guest";
      }
      console.log(`Hello, ${name}!`);
    }

    greet(); // "Hello, Guest!"
    ```

    **对比分析**

    利用 `Truthy` 和 `Falsy` 值的机制，可以在一行代码中完成默认值的设置，而没有这一机制时，则需要进行显式检查，代码变得更加繁琐。

  - **2. 循环终止条件场景**

    **使用 `Truthy` 和 `Falsy` 值**

    在遍历链表时，可以利用 `Truthy` 和 `Falsy` 值来简化循环条件：

    ```javascript
    let node = null; // 假设链表为空

    while (node) {
      console.log(node.value);
      node = node.next;
    }
    ```

    **没有 `Truthy` 和 `Falsy` 值时的代码**

    如果没有 `Truthy` 和 `Falsy` 值，我们需要显式检查 `node` 是否为 `null` 或 `undefined`：

    ```javascript
    let node = null; // 假设链表为空

    while (node !== null && node !== undefined) {
      console.log(node.value);
      node = node.next;
    }
    ```

    **对比分析**

    有了 `Truthy` 和 `Falsy` 值的机制后，循环条件的判断变得更加简洁，不需要显式检查 `null` 和 `undefined`。

  - **总结：`Truthy` 和 `Falsy` 值的目的**

      通过对比这些代码示例，我们可以看到 `Truthy` 和 `Falsy` 值的机制极大地简化了 JavaScript 代码的编写。这一机制减少了显式的类型检查，使得条件判断、参数设置、循环等常见操作更加直观和高效，帮助开发者编写出更简洁、易于维护的代码。

      这种简化是 `Truthy` 和 `Falsy` 值诞生的主要目的，它们使 JavaScript 在处理不同数据类型时更具灵活性，避免了冗长的类型判断逻辑，从而提高了开发效率。

## **Equality Operators: == vs. ===**

### **1. 概念**

**Equality Operators** 是用来比较两个值是否相等的操作符，主要包括以下两种：

- **`==` (Abstract Equality, 抽象相等)**: 进行类型转换后再比较两个值是否相等。
- **`===` (Strict Equality, 严格相等)**: 在不进行类型转换的情况下直接比较两个值是否相等。

### **2. 操作符的区别**

- **`==` 操作符**
  - 当使用 `==` 进行比较时，如果两个值类型不同，JavaScript 会在比较之前尝试进行类型转换。
  - 适用场景：当你明确知道并希望 JavaScript 在比较时自动进行类型转换。

    ```javascript
    console.log(2 == '2'); // true，字符串 '2' 被转换为数字 2
    console.log(true == 1); // true，布尔值 true 被转换为数字 1
    ```

- **`===` 操作符**
  - 当使用 `===` 进行比较时，JavaScript 不会进行任何类型转换，只有在值和类型都相同时才会返回 `true`。
  - 适用场景：当你需要严格比较两个值，并避免自动类型转换带来的潜在问题。

    ```javascript
    console.log(2 === '2'); // false，不同类型的值
    console.log(true === 1); // false，不同类型的值
    ```

### **3. 适用场景**

- **业务场景**: 在用户输入数据时，可能需要宽松的类型判断（`==`），例如检查用户输入的数字或字符串。
- **技术场景**: 在 API 调用中，为了确保数据一致性，需要严格比较两个值（`===`），避免因类型不一致导致的错误。

### **4. 实践练习**

```javascript
// 练习题 1: 结果是什么？
console.log('0' == false); // true，因为 '0' 被转换为 0，再与 false 比较

// 练习题 2: 结果是什么？
console.log('' === false); // false，因为空字符串和 false 类型不同

// 练习题 3: 结果是什么？
let value = 42;
console.log(value == '42'); // true，字符串 '42' 被转换为数字 42
console.log(value === '42'); // false，不同类型的值
```

### **5. 复习小结**

- **`==` vs. `===`**: 理解它们之间的差异及适用场景非常重要，尽量在代码中使用 `===` 以确保比较的准确性。
- **常见误区**: 注意 `==` 操作符在类型转换中的潜在风险，避免因自动转换导致的错误。

## **The switch Statement**

### **1. 概念理解**

**`switch` 语句** 是一种条件控制语句，用于基于不同的表达式值执行不同的代码块。它类似于多个 `if...else if` 的结构，但在某些情况下，`switch` 语句可以使代码更简洁和易读。

### **2. 基本语法**

```javascript
switch (expression) {
    case value1: //expression === value1
        // 当 expression 的值等于 value1 时执行的代码
        break;
    case value2:
        // 当 expression 的值等于 value2 时执行的代码
        break;
    // 你可以有任意多个 case 语句
    default:
        // 如果没有匹配到任何 case，执行此代码
}
```

### **3. 实践例子**

```javascript
let day = 3;

switch (day) {
    case 1:
        console.log('Monday');
        break;
    case 2:
        console.log('Tuesday');
        break;
    case 3:
        console.log('Wednesday');
        break;
    case 4:
        console.log('Thursday');
        break;
    case 5:
        console.log('Friday');
        break;
    case 6:
        console.log('Saturday');
        break;
    case 7:
        console.log('Sunday');
        break;
    default:
        console.log('Invalid day');
}
```

**解释**: 在这个例子中，`day` 的值为 `3`，因此控制台将输出 `'Wednesday'`。每个 `case` 块以 `break` 语句结束，防止执行后续的 `case` 块。

### **4. 注意事项**

- **`break` 语句**: 如果省略 `break`，代码会继续执行后续的 `case` 块，直到遇到 `break` 或 `switch` 语句结束。
- **`default` 块**: 是可选的，但建议使用，确保在没有匹配到任何 `case` 时有合理的处理。
- **多 `case` 合并**: 如果多个 `case` 共享相同的逻辑，可以将它们合并。

  ```javascript
  let fruit = 'apple';

  switch (fruit) {
      case 'apple':
      case 'pear':
      case 'plum':
          console.log('This is a pome fruit.');
          break;
      case 'orange':
      case 'lemon':
          console.log('This is a citrus fruit.');
          break;
      default:
          console.log('Unknown fruit.');
  }
  ```

**解释**: `apple`、`pear` 和 `plum` 共享相同的处理逻辑，因此可以合并到一起。

### **5. 适用场景**

- 当需要基于单一变量的多个可能值执行不同代码块时，`switch` 语句通常比 `if...else` 更清晰。
- 尤其适用于根据数值、字符串等离散值进行条件判断的情况。

### **6. 与 `if...else` 的对比**

- **可读性**: 当有大量 `case` 需要判断时，`switch` 语句使得代码更易于阅读。
- **性能**: 对于简单的条件判断，两者性能差异不大；但在复杂判断中，`switch` 可能更高效。

### **7. 常见错误**

- 忘记 `break` 语句：导致“fall-through”行为，即代码会继续执行下一个 `case`。
- 忘记 `default` 块：没有考虑到所有可能的情况，导致错误处理。

### **8. 复习小结**

- 理解 `switch` 语句的结构和基本用法。
- 知道如何使用 `break` 和 `default` 块进行流程控制。
- 了解 `switch` 在多值判断中的优势和适用场景。

## **The Conditional (Ternary) Operator**

### **1. 概念理解**

**The Conditional (Ternary) Operator** 是 JavaScript 中唯一的三元运算符，它提供了一种简洁的方式来替代简单的 `if...else` 语句。三元运算符的语法非常紧凑，可以将一个条件判断和两个可能的结果压缩到一行代码中。

### **2. 基本语法**

```javascript
condition ? exprIfTrue : exprIfFalse;
```

- **`condition`**: 布尔表达式。如果条件为 `true`，则返回 `exprIfTrue`；如果条件为 `false`，则返回 `exprIfFalse`。
- **`exprIfTrue`**: 当 `condition` 为 `true` 时执行的表达式或返回的值。
- **`exprIfFalse`**: 当 `condition` 为 `false` 时执行的表达式或返回的值。

### **3. Ternary Operator 与 Template Literals 的结合**

在实际开发中，`ternary operator` 和 [`template literals`](#strings-and-template-literals) 经常结合使用，特别是在构建字符串时。

```javascript
let user = {
  name: 'Alice',
  age: 25
};

let message = `Hello, ${user.name}. You are ${user.age >= 18 ? 'an adult' : 'not an adult'}.`;
console.log(message); // 输出: "Hello, Alice. You are an adult."
```

**解释**: 在这个例子中，我们将三元运算符嵌入到模板字符串（template literals）中，使得根据条件动态生成字符串变得非常直观。

### **4. Statements 与 Expressions 的区别**

- **Statements**: 是执行某些动作的代码块，通常不会返回值。例如，`if...else` 语句就是一个典型的 statement。

  ```javascript
  if (age >= 18) {
      console.log('You are an adult');
  } else {
      console.log('You are not an adult');
  }
  ```

- **Expressions**: 是产生值的代码片段，它们总会返回一个值。例如变量、运算、函数调用等。`ternary operator` 就是一个典型的 expression。

  ```javascript
  let message = age >= 18 ? 'You are an adult' : 'You are not an adult';
  ```

**关键区别**: Statements 不能用作模板字符串中的内嵌逻辑，而 expressions 可以。因此，在需要返回一个值的情况下，尤其是在模板字符串中，使用 expressions 更为合适。

### **5. 常见错误**

- **误用三元运算符**: 将三元运算符用于复杂逻辑时，容易导致代码难以理解，应该避免。

  ```javascript
  // 不推荐的写法
  let result = condition1 ? value1 : condition2 ? value2 : value3;

  // 推荐的写法
  let result;
  if (condition1) {
      result = value1;
  } else if (condition2) {
      result = value2;
  } else {
      result = value3;
  }
  ```

### **6. 相关练习题**

通过练习题巩固对三元运算符及其与模板字符串结合使用的理解。

```javascript
// 练习题 1: 结果是什么？
let score = 85;
let gradeMessage = `Your grade is ${score > 90 ? 'A' : score > 75 ? 'B' : 'C'}`;
console.log(gradeMessage); // 输出: "Your grade is B"

// 练习题 2: 结果是什么？
let number = 10;
let resultMessage = `The number is ${number % 2 === 0 ? 'Even' : 'Odd'}`;
console.log(resultMessage); // 输出: "The number is Even"
```

### **7. 复习小结**

- 理解 ternary operator 和 template literals 的基本用法，并掌握二者结合使用的场景。
- 熟悉 statements 和 expressions 的区别，知道何时应该使用哪种结构。

## **Activating Strict Mode**

### **1. 概念理解**

**Strict Mode（严格模式）** 是 JavaScript 的一种运行模式，通过在代码中添加特定的声明，可以更严格地检查代码质量并消除潜在的错误。

### **2. 启用 Strict Mode**

要启用严格模式，可以在脚本或函数的开头添加 `"use strict";` 声明：

```javascript
"use strict"; // 整个脚本启用严格模式

function myFunction() {
    "use strict"; // 仅在该函数内部启用严格模式
    // 代码块
}
```

### **3. 严格模式的优势**

- **避免意外全局变量**: 在严格模式下，所有变量必须先声明再使用，否则会抛出错误。
  
  ```javascript
  "use strict";
  x = 3.14; // 抛出 ReferenceError: x is not defined
  ```

- **消除静默错误**: 在非严格模式下，某些代码错误不会抛出异常，而在严格模式下，这些错误会被检测到并抛出异常。
  
  ```javascript
  "use strict";

  let hasCard = false;
  let isAdult = true;

  if (isAdult) hacard = true;
  if (hasCard) console("hah");// 严格模式下将抛出 ReferenceError: hacard is not defined 而非静默错误。
  ```

- **禁用某些功能**: 禁用了一些可能导致代码混淆或不安全的功能，例如 `with` 语句。

  ```javascript
  "use strict";
  with (Math) { x = cos(2); } // 抛出 SyntaxError: Strict mode code may not include a with statement
  ```

- **提前检测错误**: 在开发过程中更早地发现错误，使得代码更健壮。

### **4. 注意事项**

- **兼容性**: 严格模式不向后兼容，启用后可能导致老代码无法正常运行，因此在启用前应确保代码符合严格模式的要求。
  
- **结合模块**: 在 ES6 模块中，严格模式是默认启用的，因此无需额外声明。
的检查，但总体上对大多数应用程序的性能影响可以忽略不计。

### **5. 实践例子**

```javascript
"use strict";

function strictFunction() {
    "use strict";
    let y = 3.14; // 正确：严格模式下变量必须声明
}

function nonStrictFunction() {
    x = 3.14; // 错误：严格模式下会抛出 ReferenceError: x is not defined
}

strictFunction();
nonStrictFunction();
```

**解释**: 代码中 `strictFunction` 启用了严格模式，因此未声明的变量 `y` 会导致错误。而 `nonStrictFunction` 如果没有启用严格模式，允许未声明的变量 `x` 直接赋值。

### **6. 相关练习题**

通过练习题进一步理解严格模式的应用场景和限制。

```javascript
// 练习题 1: 结果是什么？
"use strict";
a = 10;
console.log(a); // ?

// 练习题 2: 结果是什么？
function strictTest() {
    "use strict";
    var obj = {};
    Object.defineProperty(obj, "x", { value: 42, writable: false });
    obj.x = 9; // ?
}

strictTest();
```

### **7. 复习小结**

- 理解严格模式的用途及其在提升代码质量方面的作用。
- 了解如何在脚本或函数中启用严格模式，并认识到其局限性。

## **Functions**

### **1. 概念理解**

**函数（Function）** 是一段可以被重复调用的代码块，它可以接受输入（参数），执行特定操作，并返回输出（结果）。

### **2. 函数的声明与表达式**

#### 2.1. **函数声明（Function Declaration）**

函数声明是定义函数的一种方式，它可以在定义之前调用，具有提升特性。

```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

console.log(greet('Alice')); // 输出: Hello, Alice!
```

**特点**:

- 提升特性：函数声明会在代码执行前被提升，因此可以在函数声明之前调用。
- 可读性高：通常用于定义独立的、通用的功能。

#### 2.2. **函数表达式（Function Expression）**

函数表达式是将函数作为一个值赋给变量的一种方式。与函数声明不同，函数表达式不会被提升。

```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
};

console.log(greet('Bob')); // 输出: Hello, Bob!
```

**特点**:

- 无提升特性：必须在函数表达式之后才能调用。
- 灵活性高：常用于回调函数或将函数作为参数传递的场景。

#### 2.3. **箭头函数（Arrow Function）**

箭头函数是 ES6 引入的语法，更加简洁，并且没有自己的 `this` 值。

```javascript
const greet = (name) => `Hello, ${name}!`;

console.log(greet('Charlie')); // 输出: Hello, Charlie!
```

**特点**:

- 简洁语法：适合简单的函数定义。
- 没有 `this` 值：适合在不需要 `this` 绑定的场景使用。

**总结**：Three different ways of writing functions, but they all work in a
similar way: receive input data, transform data, and then output data.

### **3. 函数参数**

#### 3.1. **默认参数（Default Parameters）**

在函数定义时，可以为参数指定默认值，当调用时未传递该参数时会使用默认值。

```javascript
function greet(name = 'stranger') {
    return `Hello, ${name}!`;
}

console.log(greet()); // 输出: Hello, stranger!
```

#### 3.2. **参数解构（Destructuring Parameters）**

可以通过解构赋值直接在函数参数中拆解对象或数组。

```javascript
function display({name, age}) {
    console.log(`Name: ${name}, Age: ${age}`);
}

const person = { name: 'David', age: 25 };
display(person); // 输出: Name: David, Age: 25
```

### **4. 函数的返回值**

函数可以通过 `return` 语句返回一个值。如果没有 `return`，则返回 `undefined`。return statement to output a value from the function and terminate execution.

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(2, 3)); // 输出: 5
```

### **5. 函数的作用域与闭包**

#### 5.1. **作用域（Scope）**

作用域决定了变量的可访问范围。在 JavaScript 中，函数内部定义的变量在函数外部是不可访问的。

```javascript
function scopeTest() {
    let x = 10;
    console.log(x); // 输出: 10
}
console.log(x); // 抛出 ReferenceError: x is not defined
```

#### 5.2. **闭包（Closure）**

闭包是指函数可以访问其定义时所在的作用域中的变量，即使这个函数是在该作用域外部执行的。

```javascript
function outer() {
    let outerVar = 'I am from outer function';

    function inner() {
        console.log(outerVar); // 输出: I am from outer function
    }

    return inner;
}

const innerFunc = outer();
innerFunc();
```

### **6. 常见问题与注意事项**

- **函数提升**: 函数声明会被提升，但函数表达式不会。使用时需注意函数的定义顺序。
- **`this` 绑定**: 箭头函数没有自己的 `this`，它的 `this` 值由外层作用域决定，适用于需要继承外部 `this` 的情况。
- **过度参数**: 如果传递的参数多于函数定义的参数，多余的参数会被忽略。

### **7. 相关练习题**

通过练习题进一步理解函数的概念与应用。

```javascript
// 练习题 1: 结果是什么？
function multiply(x, y = 5) {
    return x * y;
}

console.log(multiply(2)); // ?

// 练习题 2: 结果是什么？
const sayHello = function(name) {
    return `Hello, ${name}`;
};

console.log(sayHello('Alice')); // ?

// 练习题 3: 结果是什么？
const double = x => x * 2;
console.log(double(3)); // ?
```

### **8. 复习小结**

- 理解函数声明与表达式的差异，以及它们在代码中的适用场景。
- 掌握函数参数的使用方式，包括默认参数和解构赋值。
- 理解函数的作用域与闭包的概念，了解它们在 JavaScript 中的重要性。

## **Basic Array Operations (Methods)**

### 1. **概念概述**

**数组（Array）** 是一种数据结构，用于存储多个值的有序集合。JavaScript 中的数组是动态的，可以包含不同类型的元素。

```javascript
const numbers = [10, 20, 30, 40];
const mixedArray = [10, 'hello', true, null];
```

### 2. **创建数组**

记录几种常用的创建数组的方式。

- **字面量创建**：
  
  ```javascript
  const arr = [1, 2, 3];
  ```

- **使用 `Array` 构造函数**：
  
  ```javascript
  const arr = new Array(5); // 创建一个长度为5的空数组
  const arr2 = new Array(1, 2, 3); // 创建一个包含元素1, 2, 3的数组
  ```

### 3. **基本数组操作**

记录数组中常见的操作方法及其使用场景。

#### **3.1. 添加和删除元素**

- **`push()`**: 在数组末尾添加一个或多个元素，并返回新数组的长度。
  
  ```javascript
  const fruits = ['apple', 'banana'];
  fruits.push('orange'); // ['apple', 'banana', 'orange']
  ```

- **`pop()`**: 删除数组末尾的一个元素，并返回该元素。
  
  ```javascript
  const lastFruit = fruits.pop(); // 'orange', 剩余 ['apple', 'banana']
  ```

- **`unshift()`**: 在数组开头添加一个或多个元素，并返回新数组的长度。
  
  ```javascript
  fruits.unshift('strawberry'); // ['strawberry', 'apple', 'banana']
  ```

- **`shift()`**: 删除数组开头的一个元素，并返回该元素。
  
  ```javascript
  const firstFruit = fruits.shift(); // 'strawberry', 剩余 ['apple', 'banana']
  ```

#### **3.2. 查找和索引操作**

- **`indexOf()`**: 返回数组中某个元素的第一个匹配项的索引，如果没有找到则返回 `-1`。

  ```javascript
  const index = fruits.indexOf('banana'); // 1
  ```

- **`includes()`**: 判断数组是否包含某个元素，返回布尔值。

  ```javascript
  const hasApple = fruits.includes('apple'); // true
  ```

#### **3.3. 数组遍历**

- **`forEach()`**: 对数组中的每个元素执行一次提供的函数。

  ```javascript
  fruits.forEach(fruit => console.log(fruit));
  ```

- **`map()`**: 创建一个新数组，其结果是该数组中的每个元素调用提供的函数的返回值。

  ```javascript
  const uppercasedFruits = fruits.map(fruit => fruit.toUpperCase());
  // ['APPLE', 'BANANA']
  ```

### 4. **数组方法的应用场景**

- **`push()` 和 `pop()`**: 常用于管理栈（LIFO，后进先出）数据结构。
  
- **`unshift()` 和 `shift()`**: 常用于管理队列（FIFO，先进先出）数据结构。

- **`map()` 和 `forEach()`**: 常用于对数组中的元素进行批量操作，比如格式化数据、创建新数组等。

### 5. **实际案例**

结合业务需求记录一些实际使用数组操作的方法：

**示例：从一个用户列表中获取所有用户的名字并转换为大写字母：**

```javascript
const users = [
  { name: 'Alice', age: 30 },
  { name: 'Bob', age: 25 },
  { name: 'Charlie', age: 35 }
];

const userNames = users.map(user => user.name.toUpperCase());
console.log(userNames); // ['ALICE', 'BOB', 'CHARLIE']
```

### 6. **练习题**

```javascript
// 练习题 1: 给定一个数组 [3, 5, 7, 9]，使用数组方法删除最后一个元素，并在开头添加一个元素 1。

// 练习题 2: 使用 map() 方法将以下数组 [2, 4, 6, 8] 中的每个数字乘以 2，生成一个新数组。
```

### 7. **复习总结**

- 了解数组的基本概念和创建方法。
- 熟悉常见数组操作方法的使用场景及其区别。

## **Objects**

### 1. **概念概述**

**对象（Object）** 是一种数据结构，用于存储键值对（key-value pairs）。在JavaScript中，对象是一种重要的数据类型，几乎所有非原始值都是对象，包括数组、函数等。

```javascript
const person = {
  name: 'John',
  age: 30,
  job: 'Engineer'
};
```

### 2. **创建对象**

记录几种常用的创建对象的方式。

- **对象字面量**：
  
  ```javascript
  const car = {
    brand: 'Toyota',
    model: 'Camry',
    year: 2020
  };
  ```

- **使用 `new Object()` 构造函数**：

  ```javascript
  const car = new Object();
  car.brand = 'Toyota';
  car.model = 'Camry';
  car.year = 2020;
  ```

### 3. **对象属性操作**

记录对象的属性访问、修改和删除方法。

- **访问属性**：
  
  - 点表示法：

    仅在你知道属性的确切名称且不包含特殊字符时有效。

  - 方括号表示法：
  
    当属性名存储在变量中或属性名包含不适合点表示法的字符（如空格或连字符）时使用。

    ```javascript
    console.log(car['brand']); // 输出: Toyota

    // 使用变量访问
    let prop = 'year';
    console.log(person[prop]); // 输出: 2020
    ```

- **添加或修改属性**：
  
  ```javascript
  person.job = 'Developer'; // 修改现有属性
  person.country = 'USA'; // 添加新属性
  ```

- **删除属性**：
  
  ```javascript
  delete person.age; // 删除 age 属性
  ```

### 4. **对象的方法**

记录如何在对象中定义和使用方法。

- **定义对象方法**：
  
  ```javascript
  const calculator = {
    add: function(a, b) {
      return a + b;
    },
    subtract(a, b) {
      return a - b;
    }
  };
  
  console.log(calculator.add(5, 3)); // 8
  console.log(calculator.subtract(5, 3)); // 2
  ```

### 5. **对象的遍历**

记录如何遍历对象的属性。

- **`for...in` 循环**：
  
  ```javascript
  for (let key in person) {
    console.log(`${key}: ${person[key]}`);
  }
  ```

- **`Object.keys()` 和 `Object.values()`**：
  
  ```javascript
  const keys = Object.keys(person); // ['name', 'job', 'country']
  const values = Object.values(person); // ['John', 'Developer', 'USA']
  ```

### 6. **对象的复制与合并**

记录对象复制和合并的方法。

- **浅拷贝**：
  
  - 使用 `Object.assign()`：
  
    ```javascript
    const newPerson = Object.assign({}, person);
    ```

  - 使用展开运算符 `...`：
  
    ```javascript
    const newPerson = { ...person };
    ```

- **对象合并**：
  
  ```javascript
  const car = { brand: 'Toyota' };
  const details = { model: 'Camry', year: 2020 };
  const fullCar = { ...car, ...details };
  ```

### 7. **实际应用场景**

记录一些结合业务需求的实际对象使用案例：

**示例：在用户管理系统中存储和操作用户信息：**

```javascript
const user = {
  id: 1,
  name: 'Alice',
  email: 'alice@example.com',
  login() {
    console.log(`${this.name} has logged in.`);
  }
};

user.login(); // 'Alice has logged in.'
```

### 8. **练习题**

为巩固学习效果，加入一些练习题：

```javascript
// 练习题 1: 创建一个对象，该对象代表一本书，并包含书名、作者和出版年份属性。

// 练习题 2: 向已创建的书对象添加一个新的属性 'genre'，并将其值设置为 'Fiction'。
```

### 9. **复习总结**

- 了解对象的基本概念和创建方式。
- 熟悉对象属性的访问、修改和删除方法。
- 通过遍历和合并操作掌握对对象的全面控制。
  
## **Object Methods**

### **1. 定义：**

- **Object Methods** 是对象的属性，其值为函数。方法允许对象执行操作，并能够访问和操作对象的数据。

### **2. 创建方法：**

- 在对象中，可以直接将函数定义为属性，这个属性就称为方法。

  ```javascript
  const person = {
    firstName: 'John',
    lastName: 'Doe',
    age: 30,
    job: 'Developer',
    
    // 定义方法
    fullName: function() {
      return `${this.firstName} ${this.lastName}`;
    }
  };

  console.log(person.fullName()); // 输出: John Doe
  ```

### **3. `this` 关键字：**

- 在方法中，`this` 关键字引用的是调用该方法的对象本身。这使得方法可以访问对象的其他属性。

  ```javascript
  const person = {
    firstName: 'John',
    lastName: 'Doe',
    age: 30,
    job: 'Developer',

    fullName: function() {
      return `${this.firstName} ${this.lastName}`;
    },
    
    isAdult: function() {
      return this.age >= 18;
    }
  };

  console.log(person.isAdult()); // 输出: true
  ```

### **4. 简写方法语法：**

- ES6 引入了简写语法，可以使方法定义更加简洁。

  ```javascript
  const person = {
    firstName: 'John',
    lastName: 'Doe',
    age: 30,
    
    // 简写方法
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    }
  };

  console.log(person.fullName()); // 输出: John Doe
  ```

### **5. 使用对象方法：**

- 对象方法可以在代码中被调用来执行特定的操作。方法通常用于处理与对象相关的数据。

  **示例：**

  ```javascript
  const car = {
    brand: 'Toyota',
    model: 'Camry',
    year: 2020,

    getCarInfo() {
      return `${this.brand} ${this.model}, ${this.year}`;
    }
  };

  console.log(car.getCarInfo()); // 输出: Toyota Camry, 2020
  ```

### **6. 常见应用场景：**

- **数据验证：** 使用方法来检查对象属性的值是否有效。
- **数据格式化：** 使用方法来格式化或组合对象中的多个属性。
- **业务逻辑：** 方法可以封装对象相关的业务逻辑，如计算或决策。

### **7. 复习小结：**

- **Object Methods** 是对象中功能强大的组成部分，可以对对象数据进行操作和处理。
- 理解 `this` 关键字在方法中的作用至关重要，因为它决定了方法如何访问对象属性。

### **8. 相关练习题：**

- 创建一个 `book` 对象，包含 `title`、`author` 和 `year` 属性，以及一个 `getSummary` 方法，返回一本书的摘要信息。
  
  **示例：**

  ```javascript
  const book = {
    title: '1984',
    author: 'George Orwell',
    year: 1949,

    getSummary() {
      return `${this.title} by ${this.author}, published in ${this.year}.`;
    }
  };

  console.log(book.getSummary()); // 输出: 1984 by George Orwell, published in 1949.
  ```

## **Loops**

### **1. 概念概述**

**循环（Loop）** 是一种控制结构，用于重复执行一段代码，直到满足特定条件为止。循环在处理需要重复操作的数据集或任务时尤为有用，例如遍历数组、处理用户输入等。

### **2. 常见的循环类型**

#### **2.1. `for` 循环**

**语法：**

```javascript
for (初始化; 条件; 更新) {
    // 循环体
}
```

**示例：**

```javascript
for (let i = 0; i < 5; i++) {
    console.log(`当前循环次数: ${i}`);
}
// 输出:
// 当前循环次数: 0
// 当前循环次数: 1
// 当前循环次数: 2
// 当前循环次数: 3
// 当前循环次数: 4
```

**应用场景：**

- 已知循环次数时使用，例如遍历数组的索引。

#### **2.2. `while` 循环**

**语法：**

```javascript
while (条件) {
    // 循环体
}
```

**示例：**

```javascript
let i = 0;
while (i < 5) {
    console.log(`当前循环次数: ${i}`);
    i++;
}
// 输出同上
```

**应用场景：**

- 循环次数未知，需要根据某个条件来决定何时停止。

#### **2.3. `do...while` 循环**

**语法：**

```javascript
do {
    // 循环体
} while (条件);
```

**示例：**

```javascript
let i = 0;
do {
    console.log(`当前循环次数: ${i}`);
    i++;
} while (i < 5);
// 输出同上
```

**特点：**

- 至少执行一次循环体，因为条件在循环体之后判断。

#### **2.4. `for...in` 循环**

**语法：**

```javascript
for (let key in object) {
    // 循环体
}
```

**示例：**

```javascript
const person = { name: 'Alice', age: 25, city: 'New York' };
for (let key in person) {
    console.log(`${key}: ${person[key]}`);
}
// 输出:
// name: Alice
// age: 25
// city: New York
```

**应用场景：**

- 遍历对象的可枚举属性。

#### **2.5. `for...of` 循环**

**语法：**

```javascript
for (let element of iterable) {
    // 循环体
}
```

**示例：**

```javascript
const fruits = ['apple', 'banana', 'cherry'];
for (let fruit of fruits) {
    console.log(fruit);
}
// 输出:
// apple
// banana
// cherry
```

**应用场景：**

- 遍历数组、字符串、Map、Set 等可迭代对象。

### **3. 循环控制**

#### **3.1. `break` 语句**

**作用：**

- 立即退出当前循环，终止循环的执行。

**示例：**

```javascript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break;
    }
    console.log(i);
}
// 输出: 0, 1, 2, 3, 4
```

#### **3.2. `continue` 语句**

**作用：**

- 跳过当前循环的剩余部分，立即开始下一次循环迭代。

**示例：**

```javascript
for (let i = 0; i < 5; i++) {
    if (i === 2) {
        continue;
    }
    console.log(i);
}
// 输出: 0, 1, 3, 4
```

### **4. 嵌套循环**

**定义：**

- 在一个循环的内部再嵌套一个或多个循环。

**示例：**

```javascript
for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 2; j++) {
        console.log(`外层循环: ${i}, 内层循环: ${j}`);
    }
}
// 输出:
// 外层循环: 1, 内层循环: 1
// 外层循环: 1, 内层循环: 2
// 外层循环: 2, 内层循环: 1
// 外层循环: 2, 内层循环: 2
// 外层循环: 3, 内层循环: 1
// 外层循环: 3, 内层循环: 2
```

**注意事项：**

- 嵌套循环可能导致性能问题，尤其是在处理大数据集时，应谨慎使用。

### **5. 循环中的作用域和性能**

- **作用域：**
  - 循环内部声明的变量（如 `let`）仅在循环体内有效，使用 `var` 声明的变量则具有函数作用域。
  
- **性能优化：**
  - 尽量减少循环内部的计算和操作，提升代码执行效率。
  - 对于大型数据集，考虑使用更高效的算法或方法（如数组的内建方法 `map`、`filter` 等）。

### **6. 实际案例**

示例 1：**遍历数组并计算总和**

```javascript
const numbers = [10, 20, 30, 40, 50];
let total = 0;
for (let i = 0; i < numbers.length; i++) {
    total += numbers[i];
}
console.log(`总和: ${total}`); // 输出: 总和: 150
```

示例 2：**查找对象中满足条件的属性**

```javascript
const scores = { Alice: 85, Bob: 92, Charlie: 78, David: 90 };
for (let student in scores) {
    if (scores[student] >= 90) {
        console.log(`${student} 获得了优秀成绩: ${scores[student]}`);
    }
}
// 输出:
// Bob 获得了优秀成绩: 92
// David 获得了优秀成绩: 90
```

### **7. 练习题**

```javascript
// 练习题 1: 使用 for 循环打印从 1 到 10 的所有偶数。
for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) {
        console.log(i);
    }
}
// 输出: 2, 4, 6, 8, 10

// 练习题 2: 使用 while 循环计算数组 [5, 10, 15, 20] 的平均值。
const arr = [5, 10, 15, 20];
let sum = 0;
let index = 0;
while (index < arr.length) {
    sum += arr[index];
    index++;
}
const average = sum / arr.length;
console.log(`平均值: ${average}`); // 输出: 平均值: 12.5

// 练习题 3: 使用 for...of 循环遍历字符串 "Hello" 并打印每个字符。
const str = "Hello";
for (let char of str) {
    console.log(char);
}
// 输出:
// H
// e
// l
// l
// o
```

### **8. 复习总结**

- **理解不同类型的循环结构**：掌握 `for`、`while`、`do...while`、`for...in` 和 `for...of` 的语法及适用场景。
- **循环控制**：熟悉 `break` 和 `continue` 的使用，能够在需要时控制循环流程。
- **嵌套循环的使用**：了解嵌套循环的基本概念和注意事项，避免不必要的性能开销。
- **性能优化**：在编写循环时，关注代码的执行效率，避免低效的循环嵌套和不必要的计算。
