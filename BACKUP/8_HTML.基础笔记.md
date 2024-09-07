# [HTML 基础笔记](https://github.com/hadleysu/gitblog/issues/8)

# HTML 基础笔记

- [HTML 基础笔记](#html-基础笔记)
  - [**HTML 能解决什么样的问题**](#html-能解决什么样的问题)
  - [**1st HTML**](#1st-html)
  - [**DOM**](#dom)
  - [**tags**](#tags)
  - [**attributes**](#attributes)
  - [**`class` 和 `id` 属性的多重用途和功能**](#class-和-id-属性的多重用途和功能)
    - [1. **用于设置 CSS 样式**](#1-用于设置-css-样式)
    - [2. **用于 JavaScript 操作 DOM**](#2-用于-javascript-操作-dom)
    - [3. **用于表单数据提交**](#3-用于表单数据提交)
    - [4. **用于锚点链接**](#4-用于锚点链接)
    - [5. **用于 ARIA 和辅助技术**](#5-用于-aria-和辅助技术)
    - [总结](#总结)

## **HTML 能解决什么样的问题**

HyperText Markup Language which is a language that we can use to describe the structure of the webpage.All of the buttons and the text, and the forms and other parts of the webpage that the user ultimately sees and interacts with. [HTML（超文本标记语言） | MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTML)

## **1st HTML**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Hello!</title>
  </head>
  <body>
    Hello,world!
  </body>
</html>
```

## **DOM**

Document Object Model(文档对象模型)The tree like structure that describes how all of these HTML elements are related to each other.

## **tags**

|          |                                                        |
| -------- | ------------------------------------------------------ |
| h1       | heading，h1~h6                                         |
| ol       | ordered list                                           |
| ul       | unordered list                                         |
| li       | list item ，嵌套在 ol/ul 里使用                        |
| img      | image，required attributes（src/alt/width）            |
| a        | anchor 超链接，attribute(href)                         |
| table    | 表格                                                   |
| thead    | 表头                                                   |
| th       | 表头单元格                                             |
| tbody    | 表体                                                   |
| tr       | table row                                              |
| td       | table data                                             |
| form     | 表单                                                   |
| input    | 输入框，attribute(type/placeholder/name/list)          |
| datalist | 定义一个输入候选列表,需要和 input 标签配合使用         |
| option   | 定义 datalist 列表中每个候选项的值，即下拉菜单的内容。 |

## **attributes**

|             |                                                                |
| ----------- | -------------------------------------------------------------- |
| src         | source                                                         |
| alt         | alternative text (用文字描述图片内容 )                         |
| width       | 宽度                                                           |
| href        | hyperlink reference                                            |
| type        | 表单控件类型（如 text/submit/radio/password）                  |
| placeholder | 当没有值设定时，出现在表单控件上的文字                         |
| name        | 表单的控件名称，作为键值对的一部分与表单一同提交               |
| list        | input 标签的 list 属性是 datalist 标签的 id 属性的值，相互关联 |

datalist 标签和 option 标签的一个例子是：

```html
<label for="city">请选择您的城市：</label>
<input type="text" id="city" list="city-list" />
<datalist id="city-list">
  <option value="北京"></option>
  <option value="上海"></option>
  <option value="广州"></option>
  <option value="深圳"></option>
</datalist>
```

- datalist 标签可以定义一个输入候选列表，option 标签可以定义每个候选项的值。
- datalist 标签需要和 input 标签配合使用，通过 input 标签的 list 属性来指定要关联的 datalist 标签的 id 属性。这样，当用户在 input 标签的输入框中输入或点击时，就会显示 datalist 标签中的候选列表，用户可以从中选择一个或者自己输入一个值。

## **`class` 和 `id` 属性的多重用途和功能**

在 HTML 元素标签中添加 `class` 和 `id` 属性不仅仅是为了设置 CSS 样式，它们有其他的作用和意义。以下是 `class` 和 `id` 的多重用途和功能：

### 1. **用于设置 CSS 样式**

- **主要用途**：通过在 HTML 元素中添加 `class` 和 `id` 属性，可以在 CSS 中使用选择器来为这些元素应用特定的样式。

  - **`class`**: 可用于给多个元素应用同样的样式。
  - **`id`**: 应用于唯一的元素（每个页面中 `id` 必须是唯一的）。

**示例**:

```html
<div class="container">...</div>
<p id="main-text">这是主要文本。</p>

<style>
  .container {
    background-color: lightblue;
  }
  #main-text {
    color: red;
  }
</style>
```

### 2. **用于 JavaScript 操作 DOM**

- **选择和操作元素**：`class` 和 `id` 可以用作 JavaScript 操作 DOM 的选择器。
  - **`id`**: 使用 `document.getElementById()` 方法选择唯一的元素。
  - **`class`**: 使用 `document.getElementsByClassName()` 或 `document.querySelectorAll()` 来选择具有相同 `class` 的多个元素。

**示例**:

```html
<button id="myButton">点击我</button>
<script>
  const button = document.getElementById("myButton");
  button.addEventListener("click", () => {
    alert("按钮被点击了！");
  });
</script>
```

### 3. **用于表单数据提交**

- 在表单提交中，`id` 有时用来唯一标识表单元素，并通过 JavaScript 处理用户输入的数据。
- 例如，使用 `id` 选择表单中的特定输入框，并读取其值。

**示例**:

```html
<form>
  <input type="text" id="username" name="username" />
  <button type="submit">提交</button>
</form>

<script>
  const username = document.getElementById("username").value;
  console.log(username);
</script>
```

### 4. **用于锚点链接**

- `id` 还可以用于创建锚点链接，使页面内导航更方便。通过在 HTML 元素中添加 `id`，可以通过链接跳转到页面的特定部分。

**示例**:

```html
<a href="#section1">跳转到第一节</a>
<div id="section1">
  <h2>这是第一节内容</h2>
</div>
```

### 5. **用于 ARIA 和辅助技术**

- `id` 和 `class` 也可以用于可访问性相关的技术，帮助屏幕阅读器等辅助技术理解页面内容。
- 通过添加特定的 `aria-*` 属性，可以改进网页的可访问性。

**示例**:

```html
<button id="submitButton" aria-label="提交表单">提交</button>
```

### 总结

- **`class` 和 `id` 不仅用于 CSS 样式的定义**，它们还可以帮助 **JavaScript 操作 DOM**、**锚点导航**、**表单提交**，以及 **改善页面可访问性** 等多方面的功能。
