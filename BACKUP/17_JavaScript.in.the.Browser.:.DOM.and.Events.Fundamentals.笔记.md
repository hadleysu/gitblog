# [JavaScript in the Browser : DOM and Events Fundamentals 笔记](https://github.com/hadleysu/gitblog/issues/17)

# **JavaScript in the Browser : DOM and Events Fundamentals 笔记**

- [**JavaScript in the Browser : DOM and Events Fundamentals 笔记**](#javascript-in-the-browser--dom-and-events-fundamentals-笔记)
  - [1. **什么是 DOM？**](#1-什么是-dom)
  - [2. **DOM 树的结构**](#2-dom-树的结构)
  - [3. **为什么 DOM != JavaScript**](#3-为什么-dom--javascript)
  - [4. **什么是 Web API？**](#4-什么是-web-api)
  - [5. **DOM 和事件**](#5-dom-和事件)
  - [6. **获取 `input` 输入框中的值：使用 `.value` 与 `.textContent` 的对比**](#6-获取-input-输入框中的值使用-value-与-textcontent-的对比)
  - [7. **Refactoring（代码重构）**](#7-refactoring代码重构)
  - [8. **改变页面上元素的外观：使用 `classList` 操作类**](#8-改变页面上元素的外观使用-classlist-操作类)
  - [9. **JavaScript : `classList` 操作详解**](#9-javascript--classlist-操作详解)
    - [**1. 概述**](#1-概述)
    - [**2. `classList` 的常用方法**](#2-classlist-的常用方法)
      - [**2.1 `add()`**](#21-add)
      - [**2.2 `remove()`**](#22-remove)
      - [**2.3 `toggle()`**](#23-toggle)
      - [**2.4 `contains()`**](#24-contains)
      - [**2.5 `replace()`**](#25-replace)
    - [**3. 使用场景**](#3-使用场景)
      - [**3.1 动态改变元素样式**](#31-动态改变元素样式)
      - [**3.2 表单验证**](#32-表单验证)
    - [**4. 与 `className` 的对比**](#4-与-classname-的对比)
    - [**5. 小技巧：使用 `classList` 实现条件样式**](#5-小技巧使用-classlist-实现条件样式)
    - [**6. 总结**](#6-总结)
  - [10. **传递函数作为事件监听器方法的参数**](#10-传递函数作为事件监听器方法的参数)
  - [11. **DOM 操作与元素选择**](#11-dom-操作与元素选择)
    - [1. **`document.getElementsByClassName()` 与 `document.querySelector()` 对比**](#1-documentgetelementsbyclassname-与-documentqueryselector-对比)
      - [**1.1 `document.getElementsByClassName()`**](#11-documentgetelementsbyclassname)
      - [**1.2 `document.querySelector()`**](#12-documentqueryselector)
      - [**1.3 能相互替换吗？**](#13-能相互替换吗)
    - [2. **`document.querySelector()` 和 `document.querySelectorAll()` 对比**](#2-documentqueryselector-和-documentqueryselectorall-对比)
      - [**2.1 `document.querySelector()`**](#21-documentqueryselector)
      - [**2.2 `document.querySelectorAll()`**](#22-documentqueryselectorall)
    - [3. **总结对比**](#3-总结对比)
  - [12. **DOM 与 HTML、CSS、JavaScript 之间的关系**](#12-dom-与-htmlcssjavascript-之间的关系)
    - [**DOM 在知识图谱中的位置**](#dom-在知识图谱中的位置)
    - [**DOM 与 HTML、CSS、JavaScript 之间的关系**](#dom-与-htmlcssjavascript-之间的关系)
    - [**知识地图上的串联**](#知识地图上的串联)
    - [**知识地图总结**](#知识地图总结)
  - [13. **Keyboard Events: `keydown`, `keyup`, and `keypress`"**](#13-keyboard-events-keydown-keyup-and-keypress)
    - [**1. 概述**](#1-概述-1)
    - [**2. 常见键盘事件的区别**](#2-常见键盘事件的区别)
    - [**3. `keydown` 和 `keyup` 的应用场景**](#3-keydown-和-keyup-的应用场景)
      - [**`keydown` 应用场景：**](#keydown-应用场景)
      - [**`keyup` 应用场景：**](#keyup-应用场景)
      - [示例：捕获用户在输入框中的按键动作](#示例捕获用户在输入框中的按键动作)
    - [**4. `keypress` 与 `keydown` 的对比**](#4-keypress-与-keydown-的对比)
    - [**5. 键值属性**](#5-键值属性)
    - [**6. 如何避免重复按键的影响**](#6-如何避免重复按键的影响)
    - [**7. 总结**](#7-总结)
  - [14. **学习总结**](#14-学习总结)
    - [**实际代码例子**](#实际代码例子)
  - [**练习**](#练习)

## 1. **什么是 DOM？**

- **DOM**：Document Object Model（文档对象模型），是浏览器中加载 HTML 文档后形成的树状结构 ( DOM Tree )。

  - **HTML** 文件加载后，浏览器会将每个 HTML 标签转换成一个个对象，形成一个**树状结构**。
  - **DOM != JavaScript**：
    - JavaScript 是一种编程语言，负责执行逻辑和控制行为。
    - DOM 是浏览器中的一个**接口**，允许 JavaScript 与 HTML 和 CSS 进行交互，修改页面的结构、样式和内容。
  - **DOM** 不是 JavaScript 的一部分，而是浏览器提供给 JavaScript 的**Web API**。

  **工作原理**：

  - 当浏览器解析 HTML 时，生成 DOM 树，树中的每个节点对应一个页面元素（标签）。
  - 通过 DOM API，JavaScript 可以选择、修改和操作这些元素。
  - 浏览器会自动监听 JavaScript 对 DOM 的任何修改，并即时更新页面的显示（如增删 HTML 元素，修改样式等）。

## 2. **DOM 树的结构**

- **根节点**是`document` **对象**，它是整个 DOM 的入口，提供对 HTML 文档的全局访问。通过 `document` 对象，可以访问和操控页面中的元素、节点。

- `<html>` **元素是** `document` **对象的子节点**，是实际的页面内容的根元素。

- 每个 HTML 元素（如 `<body>`, `<h1>`, `<p>`）都被表示为一个**节点**（Node）。

- **DOM 树**的层次结构：

  - **Document**（文档对象）：`document` 对象是根节点。
  - **Element 节点**：每个 HTML 标签都对应一个元素节点。
  - **Text 节点**：每个元素节点内的文本内容。

  **例子**：

  ```html
  <html>
    <body>
      <h1>Welcome to JavaScript</h1>
      <p>This is an example paragraph.</p>
    </body>
  </html>
  ```

  对应的 DOM 树：

  ```markdown
  - document
    - html
      - body
        - h1
          - "Welcome to JavaScript"
        - p
          - "This is an example paragraph."
  ```

## 3. **为什么 DOM != JavaScript**

- **DOM** 是一种浏览器实现的 API，用于表示和操作 HTML 文档的结构。
- **JavaScript** 是一种编程语言，负责操作 DOM 的逻辑和行为。
- JavaScript 使用 DOM 来**访问、操作和修改**网页的结构和样式，但 DOM 不是 JavaScript 的一部分。

  **类比**：JavaScript 可以像遥控器一样控制电视（DOM），但遥控器本身并不等同于电视。

## 4. **什么是 Web API？**

- **Web API**：Web 应用编程接口，是浏览器提供给 JavaScript 使用的一组功能和接口，帮助开发者与浏览器功能互动。

  - **DOM** 就是一个 Web API，它允许 JavaScript 访问并修改 HTML 文档的结构。
  - 其他常见的 Web API 还包括 `fetch`（用于网络请求），`localStorage`（用于存储数据）等。

  **Web API 的作用**：

  - 它们是浏览器为开发者提供的工具，使 JavaScript 能够与浏览器的底层功能进行交互。
  - JavaScript 本身并不包含与网络、文件、用户交互等相关的功能，这些都是通过 Web API 实现的。**Web API** 的作用是使 JavaScript 能够：

    - 操作 **DOM 树**（如操作 HTML、CSS 样式、属性等）。
    - 处理 **事件**（如点击、鼠标移动、键盘输入等）。
    - 使用 **其他浏览器功能**（如 Fetch API、Local Storage、Geolocation、Notification 等）。

  **常见 Web API 示例**：

  1. **DOM API** : `document.querySelector()`,`getElementById()`
  2. **事件 API** : `addEventListener()`
  3. **网络 API** : `fetch()`
  4. **存储 API** : `localStorage.setItem()`

  **例子**：

  - 使用 DOM API 选择元素：

    ```javascript
    const header = document.querySelector("h1");
    console.log(header.textContent); // 输出: Welcome to JavaScript
    ```

  - 使用 `localStorage` 存储数据：

    ```javascript
    localStorage.setItem("name", "John Doe");
    console.log(localStorage.getItem("name")); // 输出: John Doe
    ```

  - 使用 `addEventListener` 事件监听，使用 `fetch` 发送 HTTP 请求：

    ```javascript
    document.getElementById("button").addEventListener("click", function () {
      alert("Button clicked!"); // 事件监听
    });

    fetch("https://api.example.com/data") // 发送HTTP请求
      .then((response) => response.json())
      .then((data) => console.log(data)); // 处理服务器返回的数据
    ```

## 5. **DOM 和事件**

- **事件**：用户与页面交互（如点击、输入、滚动等）时，浏览器会产生**事件**，这些事件可以通过 JavaScript 进行处理。

  - 常见事件包括 `click`，`submit`，`keydown` 等。

  **事件监听器**：

  - 可以通过 JavaScript 给 DOM 元素添加事件监听器，处理用户交互。

  **例子**：

  ```javascript
  const button = document.querySelector("button");
  button.addEventListener("click", function () {
    alert("Button was clicked!");
  });
  ```

- **事件流**：
  - 事件在 DOM 中有一个传播顺序，从最外层到最内层（捕获阶段），再从内层返回到外层（冒泡阶段）。
  - JavaScript 可以选择在哪个阶段处理事件。

## 6. **获取 `input` 输入框中的值：使用 `.value` 与 `.textContent` 的对比**

- **`input.value`**:

  - 用于获取 `<input>` 元素的值。适用于表单控件，如输入框、选择框等。
  - **用法**: `document.querySelector('input').value`
  - **示例**:

    ```html
    <input type="text" id="nameInput" value="John" />
    <script>
      const inputValue = document.getElementById("nameInput").value;
      console.log(inputValue); // 输出: John
    </script>
    ```

- **`element.textContent`**:

  - 用于获取或设置元素的文本内容，适用于非表单元素，如`<div>`、`<p>`等。
  - **用法**: `document.querySelector('p').textContent`
  - **示例**:

    ```html
    <p id="textElement">Hello World</p>
    <script>
      const textContent = document.getElementById("textElement").textContent;
      console.log(textContent); // 输出: Hello World
    </script>
    ```

- **对比**:
  - **`value`** 仅适用于 `<input>`、`<textarea>` 等表单控件。
  - **`textContent`** 则适用于所有元素，且用于操作元素中的文本，而不是用户输入的值。

## 7. **Refactoring（代码重构）**

- **Refactoring** 是指优化代码的过程，使代码更加简洁、可读、易于维护，而不改变程序的功能。
- **目的**:

  - 增加代码的可读性
  - 消除重复代码
  - 提高代码的可维护性

- **Refactoring 示例**：

  - **重构前**：

    ```javascript
    function calculateRectangleArea(width, height) {
      const area = width * height;
      return area;
    }

    function calculateCircleArea(radius) {
      const area = Math.PI * radius * radius;
      return area;
    }
    ```

  - **重构后**：

    ```javascript
    function calculateArea(shape, value1, value2 = null) {
      if (shape === "rectangle") {
        return value1 * value2;
      } else if (shape === "circle") {
        return Math.PI * value1 * value1;
      }
    }
    ```

  - **解释**：重构后，代码将不同形状的面积计算封装到一个函数中，避免重复代码，并增强了代码的可扩展性。

## 8. **改变页面上元素的外观：使用 `classList` 操作类**

当我们想要改变页面元素的外观时，可以将样式导出到一个 `class` 中，使用 `element.classList.add()` 或 `element.classList.remove()` 来动态操作类。

- **用法**：

  ```javascript
  element.classList.add("newClass");
  element.classList.remove("oldClass");
  ```

- **示例**：

  ```html
  <div id="box" class="red-box">我是一个盒子</div>
  <button onclick="changeBox()">改变颜色</button>

  <style>
    .red-box {
      background-color: red;
    }

    .blue-box {
      background-color: blue;
    }
  </style>

  <script>
    function changeBox() {
      const box = document.getElementById("box");
      box.classList.remove("red-box");
      box.classList.add("blue-box");
    }
  </script>
  ```

  - **解释**：在按钮点击时，我们移除 `red-box` 类，并添加 `blue-box` 类，从而改变盒子的背景颜色。

## 9. **JavaScript : `classList` 操作详解**

### **1. 概述**

`classList` 是 DOM 中用来操作元素 `class` 属性的一个属性。它为开发者提供了一系列方法，简化了对 `class` 的增删查改。相较于直接操作 `className`，`classList` 更加简洁和高效。

---

### **2. `classList` 的常用方法**

#### **2.1 `add()`**

- **功能：** 为元素添加一个或多个类名。
- **语法：**

  ```javascript
  element.classList.add(class1, class2, ...);
  ```

- **示例：**

  ```javascript
  const element = document.querySelector(".my-element");
  element.classList.add("new-class");
  console.log(element.classList); // ["existing-class", "new-class"]
  ```

#### **2.2 `remove()`**

- **功能：** 从元素中移除一个或多个类名。
- **语法：**

  ```javascript
  element.classList.remove(class1, class2, ...);
  ```

- **示例：**

  ```javascript
  element.classList.remove("new-class");
  console.log(element.classList); // 移除了 'new-class'
  ```

#### **2.3 `toggle()`**

- **功能：** 如果类名存在就移除类名，不存在则添加类名。可以接受一个可选的布尔值，决定是否添加或移除类名。
- **语法：**

  ```javascript
  element.classList.toggle(className [, force]);
  ```

- **示例：**

  ```javascript
  element.classList.toggle("hidden");
  console.log(element.classList); // 如果 'hidden' 存在就移除，否则添加
  ```

#### **2.4 `contains()`**

- **功能：** 检查元素是否包含指定的类名。
- **语法：**

  ```javascript
  element.classList.contains(className);
  ```

- **示例：**

  ```javascript
  const hasClass = element.classList.contains("new-class");
  console.log(hasClass); // true 或 false
  ```

#### **2.5 `replace()`**

- **功能：** 将元素的某个类名替换为另一个类名。
- **语法：**

  ```javascript
  element.classList.replace(oldClass, newClass);
  ```

- **示例：**

  ```javascript
  element.classList.replace("old-class", "new-class");
  console.log(element.classList); // 将 'old-class' 替换为 'new-class'
  ```

---

### **3. 使用场景**

#### **3.1 动态改变元素样式**

- **场景：** 当用户进行交互（如点击按钮、悬停）时，动态地为元素添加或移除类，改变其样式。
- **示例：**

  ```html
  <button id="toggleButton">Toggle Class</button>
  <div id="content" class="visible">This is some content</div>

  <style>
    .visible {
      display: block;
    }
    .hidden {
      display: none;
    }
  </style>

  <script>
    const button = document.getElementById("toggleButton");
    const content = document.getElementById("content");

    button.addEventListener("click", function () {
      content.classList.toggle("hidden");
    });
  </script>
  ```

#### **3.2 表单验证**

- **场景：** 在表单提交前对输入进行验证，如果验证失败，可以为输入框添加错误样式。
- **示例：**

  ```javascript
  const input = document.querySelector("#username");
  if (input.value === "") {
    input.classList.add("error");
  } else {
    input.classList.remove("error");
  }
  ```

---

### **4. 与 `className` 的对比**

- **`className`:** 会替换整个 `class` 属性的值，不方便操作多个类名，容易造成覆盖问题。
- **`classList`:** 支持多个类名的动态操作，可以增加、移除、切换、检查类名，灵活高效。

**示例对比：**

```javascript
// 使用 className 操作
element.className = "new-class"; // 覆盖掉所有其他类

// 使用 classList 操作
element.classList.add("new-class"); // 保留其他类名，只添加新的类
```

---

### **5. 小技巧：使用 `classList` 实现条件样式**

你可以通过 `classList` 在某些交互事件中动态应用样式。例如，点击按钮时切换模式（暗模式和亮模式）。

**示例：**

```html
<button id="themeToggle">Toggle Theme</button>
<div id="pageContent">This is the content</div>

<style>
  .dark-mode {
    background-color: black;
    color: white;
  }
</style>

<script>
  const toggleButton = document.getElementById("themeToggle");
  const content = document.getElementById("pageContent");

  toggleButton.addEventListener("click", function () {
    content.classList.toggle("dark-mode");
  });
</script>
```

---

### **6. 总结**

- **`classList`** 提供了一系列操作类名的便捷方法，如 `add()`、`remove()`、`toggle()` 等，大大简化了操作类名的逻辑。
- 使用 `classList` 更安全和高效，避免了直接修改 `className` 可能带来的覆盖问题。

## 10. **传递函数作为事件监听器方法的参数**

在 JavaScript 中，将函数作为事件监听器时，不能加上括号 `()`，因为加上括号意味着立即调用函数，而不是将函数传递给事件。

- **错误示例**：

  ```javascript
  button.addEventListener("click", myFunction()); // 错误，会立即调用
  ```

- **正确示例**：

  ```javascript
  button.addEventListener("click", myFunction); // 正确，传递函数引用
  ```

- **示例**：

  ```html
  <button id="myButton">点击我</button>

  <script>
    function showAlert() {
      alert("按钮被点击了！");
    }

    const button = document.getElementById("myButton");
    button.addEventListener("click", showAlert); // 传递函数，不加括号
  </script>
  ```

  - **解释**：如果在 `addEventListener` 中使用 `myFunction()`，函数会立即执行，而不是在事件触发时调用。因此需要传递函数的引用，即 `myFunction`。

## 11. **DOM 操作与元素选择**

### 1. **`document.getElementsByClassName()` 与 `document.querySelector()` 对比**

#### **1.1 `document.getElementsByClassName()`**

- **作用**: 选择具有特定 `class` 的所有元素，返回的是一个**动态的 HTMLCollection**。
- **用法**:

  - 只接受类名作为参数，不需要任何前缀符号。
    例如：

  ```javascript
  const elements = document.getElementsByClassName("highscore");
  console.log(elements);
  ```

- **特性**:
  - 返回 **HTMLCollection**，这是一个类数组对象，包含所有符合条件的元素。
  - 该方法会实时更新，如果 DOM 中有新元素添加到符合该 `class`，该集合会动态更新。
  - 只能通过 `class` 选择元素，不能选择 ID、标签或其他选择器。

---

#### **1.2 `document.querySelector()`**

- **作用**: 选择符合 CSS 选择器的**第一个元素**，返回的是**单个元素对象**。
- **用法**:

  - 需要传入完整的 CSS 选择器，包括类名、ID 或标签等选择器的前缀符号。
  - 类名选择器前加 `.`，ID 选择器前加 `#`，标签直接使用标签名。

  ```javascript
  const element = document.querySelector(".highscore");
  console.log(element);
  ```

- **特性**:
  - 返回符合条件的**第一个元素**，只返回一个 DOM 节点。
  - 支持复杂的 CSS 选择器，不仅限于 `class`，也可以用来选择 ID (`#id`)、标签 (`p`)，甚至复杂的组合选择器 (`div > p` 等)。
  - 不会动态更新，如果页面上元素发生变化，不会反映在结果中。

---

#### **1.3 能相互替换吗？**

- **不完全可以**。`getElementsByClassName()` 返回的是**所有具有该类名的元素**，是一个类数组，适用于处理多个元素。而 `querySelector()` 只返回**第一个匹配的元素**。
- **哪个更常用？**：在现代开发中，`document.querySelector()` 更常用，因为它的功能更强大，支持复杂的 CSS 选择器，并且可以选择任意类型的元素（不仅仅是通过 `class` 选择）。如果需要选择多个元素，通常使用 `querySelectorAll()`。

---

### 2. **`document.querySelector()` 和 `document.querySelectorAll()` 对比**

#### **2.1 `document.querySelector()`**

- **作用**: 选择**第一个**符合 CSS 选择器的元素。
- **返回值**: 返回**单个元素对象**或 `null`（如果没有找到匹配的元素）。
- **适用场景**: 适合当只需选择一个元素时使用，如表单中的特定输入框、页面中的唯一按钮等。

---

#### **2.2 `document.querySelectorAll()`**

- **作用**: 选择**所有**符合 CSS 选择器的元素，返回的是一个**静态的 NodeList**。
- **用法**:

  - 需要传入完整的 CSS 选择器，包括类名、ID 或标签等选择器的前缀符号。
  - 类名选择器前加 `.`，ID 选择器前加 `#`，标签直接使用标签名。

  ```javascript
  const elements = document.querySelectorAll(".highscore");
  console.log(elements);
  ```

- **返回值**: 返回一个**NodeList**，可以包含多个元素。
  - **NodeList** 是静态的：页面中元素的增减不会动态更新这个集合。
- **适用场景**: 当需要处理多个符合条件的元素时使用。

### 3. **总结对比**

| 特性         | `querySelector()`                   | `querySelectorAll()`                | `getElementsByClassName()`   |
| ------------ | ----------------------------------- | ----------------------------------- | ---------------------------- |
| **参数形式** | CSS 选择器 (`.class`, `#id`, `tag`) | CSS 选择器 (`.class`, `#id`, `tag`) | 只接受类名 (`className`)     |
| **返回类型** | 单个 DOM 元素                       | `NodeList`（静态集合）              | `HTMLCollection`（动态集合） |
| **返回数量** | 只返回第一个匹配的元素              | 返回所有匹配的元素                  | 返回所有具有该类名的元素     |
| **动态性**   | 静态，不会实时更新                  | 静态，不会实时更新                  | 动态，会随 DOM 变化自动更新  |

## 12. **DOM 与 HTML、CSS、JavaScript 之间的关系**

### **DOM 在知识图谱中的位置**

- **类别**：浏览器 API / Web API
- **作用**：提供接口，允许 JavaScript 操作和修改 HTML 和 CSS，从而动态更新网页内容和样式。

---

### **DOM 与 HTML、CSS、JavaScript 之间的关系**

1. **HTML (结构)**：

   - HTML 定义了网页的**结构**，包括标签、元素、文本等内容。
   - DOM 将 HTML 转换为**树状结构**，称为 DOM 树，这样每个 HTML 元素在树上都有一个对应的节点。HTML 是页面的静态结构，DOM 则将其转化为可操作的对象。
   - **关系**：HTML 是 DOM 的基础。浏览器加载 HTML 后，会将其解析为 DOM 树，JavaScript 就可以通过 DOM 操作 HTML 结构。

     **示例**：

     - HTML：`<div id="app"></div>`
     - DOM：通过 `document.getElementById('app')` 可以操作该 `div`。

2. **CSS (样式)**：

   - CSS 用来描述 HTML 元素如何呈现的语言。（如颜色、布局、字体等）。
   - 虽然 CSS 不能直接操作 DOM，但通过 JavaScript 修改 DOM 树上的样式属性时，可以动态影响元素的显示样式。
   - **关系**：CSS 可以与 DOM 结合使用，改变样式；DOM 的节点结构也可以动态影响 CSS 的应用（例如通过类名或内联样式）。

     **示例**：

     - 使用 JavaScript 修改 DOM 中的样式：`document.getElementById('app').style.color = 'red';`
     - 使用 DOM 操作类名：`document.getElementById('app').classList.add('highlight');`

3. **JavaScript (行为)**：

   - JavaScript 是用来与 DOM 交互的脚本语言，能够通过 DOM API 获取、修改和删除 HTML 元素，并添加事件、动画等。
   - **关系**：JavaScript 通过 DOM 操作 HTML 和 CSS，实现动态内容更新、用户交互和响应事件等行为。

     **示例**：

     - 动态添加元素：`document.body.appendChild(newElement);`
     - 修改内容：`document.getElementById('app').textContent = 'Hello World';`

---

### **知识地图上的串联**

1. **HTML (基础层)**:
   - 定义页面的**内容和结构**。所有页面的元素最初都来源于 HTML。
   - **关键词**：元素、属性、标签。
2. **CSS (表现层)**:

   - **作用**：定义页面的样式，如颜色、字体、布局等。
   - **如何与 DOM 交互**：通过 DOM API 操作类名、样式。
   - **关键词**：选择器、属性、样式规则。

3. **DOM (中介层)**:
   - **作用**：浏览器将 HTML 解析为 DOM 树，提供接口让 JavaScript 操作 HTML 元素和样式。
   - **特点**：JavaScript 可通过 DOM API 操作页面上的所有内容。
   - **关键词**：节点、DOM 树、DOM API。
4. **JavaScript (行为层)**:
   - **作用**：通过 DOM 操作 HTML 和 CSS，控制页面的行为和交互。
   - **如何与 DOM 交互**：通过 DOM API 进行页面元素、属性、样式等操作。
   - **关键词**：事件、操作、逻辑。

```plaintext
  HTML (结构)
    ↓
  DOM (树状模型，浏览器将 HTML 解析成 DOM)
    ↔ JavaScript (通过 DOM 操作 HTML，修改页面结构、样式、内容)
    ↔ CSS (通过 DOM 修改样式，实现动态显示效果)
```

### **知识地图总结**

- **HTML** 提供结构 → **DOM** 将 HTML 转换为可操作的对象模型 → **CSS** 提供样式，通过 **DOM API** 动态修改 → **JavaScript** 提供动态交互，通过 **DOM API** 操作 **HTML** 和 **CSS**。

这个模型是前端开发的核心，所有动态页面交互的实现都依赖于 **DOM** 作为中间桥梁，将 **HTML**、**CSS** 和 **JavaScript** 串联起来。

## 13. **Keyboard Events: `keydown`, `keyup`, and `keypress`"**

### **1. 概述**

在网页开发中，监听用户键盘输入是很常见的需求。JavaScript 提供了三种主要的键盘事件：

- **`keydown`:** 在键被按下时触发。
- **`keypress`:** 在按下可产生字符的键时触发（已经被废弃，不推荐使用）。
- **`keyup`:** 在键松开时触发。

这三个事件都有助于捕获用户在键盘上的行为，并根据输入进行响应。

---

### **2. 常见键盘事件的区别**

- **`keydown`:** 只要按下键盘的任意键，无论是字符键还是功能键（如 `Shift`、`Ctrl`、方向键），都会触发。适合捕获所有按键事件。
- **`keypress`:** 只会在按下可打印字符（例如字母、数字、符号）时触发，且不适用于功能键。由于浏览器的 API 变化，`keypress` 已经逐渐被弃用。

- **`keyup`:** 键被释放时触发。常用于需要检测按键结束后的操作。

---

### **3. `keydown` 和 `keyup` 的应用场景**

#### **`keydown` 应用场景：**

- **游戏控制：** 当按下某个方向键，控制游戏角色移动。
- **快捷键处理：** 当按下特定组合键（例如 `Ctrl + S`），触发保存功能。

#### **`keyup` 应用场景：**

- **检测完成输入：** 当用户松开键盘后，可以检查输入的内容并做进一步处理。
- **在表单中：** 当松开某个键时自动提交表单或进行验证。

#### 示例：捕获用户在输入框中的按键动作

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Keyboard Events Example</title>
  </head>
  <body>
    <input type="text" id="textInput" placeholder="Type something..." />

    <script>
      const inputField = document.getElementById("textInput");

      // 使用 keydown 监听用户按下的键
      inputField.addEventListener("keydown", function (event) {
        console.log("Key down:", event.key);
      });

      // 使用 keyup 监听用户松开的键
      inputField.addEventListener("keyup", function (event) {
        console.log("Key up:", event.key);
      });
    </script>
  </body>
</html>
```

---

### **4. `keypress` 与 `keydown` 的对比**

- **`keypress`:** 仅适用于捕获可打印字符（如字母、数字），并且在现代开发中已逐渐被弃用。
- **`keydown`:** 能够捕获所有按键（包括功能键），在绝大多数情况下更推荐使用。

### **5. 键值属性**

每个键盘事件对象都包含了一个 `event` 对象，其中 `event.key` 返回按下的键的值。例如：

- `event.key = "a"` 代表用户按下了字母键 “A”。
- `event.key = "Enter"` 代表用户按下了回车键。

```javascript
document.addEventListener("keydown", function (event) {
  console.log(`You pressed: ${event.key}`);
});
```

---

### **6. 如何避免重复按键的影响**

有时候，`keydown` 事件可能会因为按住键盘不松手而多次触发。因此，在某些应用场景下可能需要判断按键是否已经被处理，避免重复触发。

```javascript
let isKeyPressed = false;

document.addEventListener("keydown", function (event) {
  if (!isKeyPressed) {
    console.log(`Key pressed: ${event.key}`);
    isKeyPressed = true;
  }
});

document.addEventListener("keyup", function () {
  isKeyPressed = false;
});
```

---

### **7. 总结**

- **`keydown` 和 `keyup`** 是现代开发中最常使用的键盘事件，可以捕获所有按键。
- **`keypress`** 已经被弃用，不建议再使用。
- 键盘事件适合用于表单处理、快捷键设置、游戏控制等场景，能够提升用户交互体验。

## 14. **学习总结**

1. **DOM** 是 JavaScript 用来与网页结构交互的重要接口，允许通过树状结构访问和操作 HTML 元素。
2. **DOM != JavaScript**：DOM 是一种 Web API，用来表示和修改文档，而 JavaScript 是一种操作该 API 的语言。
3. **Web API** 提供了许多 JavaScript 直接调用的功能接口，帮助其与浏览器的底层机制进行交互。
4. **事件** 是用户与网页交互的重要部分，事件监听器帮助开发者捕获用户的操作并做出响应。
5. **获取值**: 使用 `input.value` 获取输入框的值，`element.textContent` 获取元素文本内容。
6. **重构**: 重构代码以减少重复、提高可读性。
7. **类操作**: 使用 `element.classList.add()` 和 `element.classList.remove()` 来改变元素的外观。
8. **`classList`** 提供了一系列操作类名的便捷方法，如 `add()`、`remove()`、`toggle()` 等，大大简化了操作类名的逻辑。
9. **事件监听**: 当传递函数作为事件监听器时，不要加括号，传递的是函数引用而不是函数的调用。
10. **传参**：`getElementsByClassName()` 只传类名，而 `querySelector()` 和 `querySelectorAll()` 需要传入完整的 CSS 选择器。
11. **返回**：`querySelector()` 返回单个元素，`querySelectorAll()` 返回 `NodeList`（静态），`getElementsByClassName()` 返回 `HTMLCollection`（动态）。
12. DOM 是连接 HTML、CSS 和 JavaScript 的桥梁，负责将静态的 HTML 和样式通过 JavaScript 变得动态、可交互。
13. **`keydown` 和 `keyup`** 是现代开发中最常使用的键盘事件，可以捕获所有按键。

---

### **实际代码例子**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>DOM Example</title>
  </head>
  <body>
    <h1>Welcome to JavaScript DOM</h1>
    <button>Click Me!</button>

    <script>
      // Selecting DOM element
      const button = document.querySelector("button");

      // Adding an event listener to the button
      button.addEventListener("click", function () {
        alert("Button was clicked!");
      });

      // Working with DOM tree - modifying content
      const header = document.querySelector("h1");
      header.textContent = "DOM and Events in Action";
    </script>
  </body>
</html>
```

## **练习**

1. 使用 `document.querySelector()` 选择页面元素，修改其文本内容。
2. 尝试添加不同事件（如 `click`、`mouseover`）来练习事件监听器的使用。
