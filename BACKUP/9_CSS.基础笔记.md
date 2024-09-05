# [CSS 基础笔记](https://github.com/hadleysu/gitblog/issues/9)

# CSS 基础笔记

- [CSS 基础笔记](#css-基础笔记)
  - [**CSS 能解决什么样的问题**](#css-能解决什么样的问题)
    - [参考文档](#参考文档)
  - [**分类**](#分类)
    - [**inline styling**](#inline-styling)
    - [**internal CSS**](#internal-css)
    - [**external CSS**](#external-css)
  - [**CSS Selectors**](#css-selectors)
    - [**Type Selector / Element Selector**](#type-selector--element-selector)
    - [**Id Selector**](#id-selector)
    - [**Class Selector**](#class-selector)
    - [**Multiple Element Selector**](#multiple-element-selector)
    - [**CSS 优先级规则**](#css-优先级规则)
    - [**CSS Selectors Table**](#css-selectors-table)
    - [**Child Selector**](#child-selector)
    - [**Descendant Selector**](#descendant-selector)
    - [**Attribute Selector**](#attribute-selector)
    - [**Pseudo Class**](#pseudo-class)
      - [hover (悬停时)](#hover-悬停时)
  - [**ID vs Class**: Differences and Use Cases](#id-vs-class-differences-and-use-cases)
  - [**Inheritable and Non-Inheritable Properties**](#inheritable-and-non-inheritable-properties)
  - [**Global Reset: Why We Use `* { margin: 0; padding: 0; box-sizing: border-box; }`**](#global-reset-why-we-use---margin-0-padding-0-box-sizing-border-box-)
  - [**Block vs Inline Elements**](#block-vs-inline-elements)
  - [**Example Notes**](#example-notes)
  - [**Responsive Design**](#responsive-design)
    - [**viewport**](#viewport)
    - [**Media Queries**](#media-queries)
    - [**Flexbox**](#flexbox)
    - [**Grids**](#grids)
  - [**Bootstrap**](#bootstrap)
    - [**Bootstrap’s grid system**](#bootstraps-grid-system)
  - [**Sass**](#sass)
    - [**Sass 支持变量**](#sass-支持变量)
    - [**Sass 中嵌套语法更简单**](#sass-中嵌套语法更简单)
    - [**继承**](#继承)
    - [**父选择器 \& ( Referencing Parent Selectors: \& )**](#父选择器---referencing-parent-selectors--)
      - [**\& 有以下几种用法**](#-有以下几种用法)
      - [**问题**](#问题)

## **CSS 能解决什么样的问题**

[CSS：层叠样式表 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS) Cascading Style Sheets 用于设置网页的样式及布局——比如，可以更改内容的字体、颜色、大小以及间距，或是将其分列，或是添加动画及赋予内容其他装饰性的特征。[CS50W HTML, CSS notes](https://cs50.harvard.edu/web/2020/notes/0/)

### 参考文档

- [MDN - CSS selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)
- [W3Schools - CSS Selectors](https://www.w3schools.com/CSS/css_selectors.asp)

- [W3Schools - CSS Flexbox](https://www.w3schools.com/css/css3_flexbox.asp)

- [阮一峰 Flex 布局教程：语法篇](https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

- [阮一峰 Flex 布局教程：实例篇](https://www.ruanyifeng.com/blog/2015/07/flex-examples.html)

- [阮一峰 Flexbox 布局的最简单表单](https://www.ruanyifeng.com/blog/2018/10/flexbox-form.html)

- [阮一峰 CSS Grid 网格布局教程](https://www.ruanyifeng.com/blog/2019/03/grid-layout-tutorial.html)

- [W3Schools - CSS Grid Layout Module](https://www.w3schools.com/css/css_grid.asp)

## **分类**

### **inline styling**

```html
<h1 style="color: blue; text-align: center;">This is a heading.</h1>
```

### **internal CSS**

```html
<head>
  <style>
    h1 {
      color: blue;
      text-align: center;
    }
  </style>
</head>
```

### **external CSS**

- 创建单独的 css 文件，如 style.css
- 在< head >里用< link >引用，如：

```html
<head>
  <link ref="stylesheet" href="style.css" />
</head>
```

## **CSS Selectors**

### **Type Selector / Element Selector**

```css
div {
  background-color: orange;
  width: 200px;
  height: 200px;
  padding: 20px; /*内边距*/
  margin: 20px; /*外边距*/
}

/* font */
div {
  border: 2px solid black;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 28px;
  font-weight: bold;
}
```

---

### **Id Selector**

HTML 中：

```html
<h1 id="foo">Heading 1</h1>
<h1>Heading 2</h1>
<h1>Heading 3</h1>
```

CSS 中：

```css
#foo {
  color: blue;
}
```

---

### **Class Selector**

HTML 中：

```html
<h1 class="baz">Heading 1</h1>
<h1 class="baz">Heading 2</h1>
<h1>Heading 3</h1>
```

CSS 中：

```css
.baz {
  color: blue;
}
```

---

### **Multiple Element Selector**

```css
table {
  border: 2px solid black;
  border-collapse: collapse;
}
td,
th {
  /*th 和 td 具有相同的样式，就直接用逗号连接放一起*/
  border: 2px solid black;
  padding: 5px;
}
```

---

### **CSS 优先级规则**

当同一个元素被多条 CSS 规则定义时,浏览器会根据一定的优先级规则来决定最终应用哪一条规则。这个优先级规则被称为 CSS 优先级。

CSS 优先级的主要规则如下:

1. **内联样式 > ID 选择器 > 类选择器 > 元素选择器**

   - inline `如 style="..."`
   - id `如 #my-element`
   - class `如 .my-class`
   - type `如 div`

2. **就近原则**

   - 当多条具有相同优先级的规则应用于同一元素时,就近原则生效,即最后定义的规则会覆盖先前的规则。

3. **!important 关键字**
   - 使用 `!important` 关键字可以提升某条 CSS 规则的优先级,使其覆盖其他规则。但应该谨慎使用,因为它会破坏 CSS 的级联机制。

---

### **CSS Selectors Table**

|       |                           |
| ----- | ------------------------- |
| a, b  | Multiple Element Selector |
| a b   | Descendant Selector       |
| a > b | Child Selector            |
| a + b | Adjacent Sibling Selector |
| [a=b] | Attribute Selector        |
| a:b   | Pseudoclass Selector      |
| a::b  | Pseudoelement Selector    |

---

### **Child Selector**

指定直系子代

HTML 中：

```html
<ol>
  <li>list item one</li>
  <li>list item two</li>
  <ul>
    <li>sublist item one</li>
    <li>sublist item two</li>
  </ul>
  <li>list item three</li>
</ol>
>
```

CSS 中：

```css
ul > li {
  color: blue;
}
```

---

### **Descendant Selector**

选定所有后代元素

```css
ul li {
  color: blue;
}
```

---

### **Attribute Selector**

HTML 中：

```html
<ul>
  <li><a href="https:google.com">Google</a></li>
  <li><a href="https://developer.mozilla.org/zh-CN/docs/Web/CSS">CSS</a></li>
</ul>
```

CSS 中：

```css
a {
  color: blue;
}
a[href="https:google.com"] {
  color: red;
}
```

---

### **Pseudo Class**

#### hover (悬停时)

HTML 中：

```html
<button>Click Me</button>
```

CSS 中：

```css
button {
  width: 200px;
  height: 50px;
  font-size: 20px;
  background-color: blue;
}
button:hover {
  background-color: red;
}
```

---

## **ID vs Class**: Differences and Use Cases

- **ID**:

  - Unique: Can only be used once per page.
  - Syntax: `#idName`.
  - Specificity: Higher specificity than class, meaning it will override class styles if both are applied.
  - **Use Case**: Useful when you need to style a specific element that won't be repeated on the page (e.g., a single header).

- **Class**:
  - Reusable: Can be used multiple times across different elements.
  - Syntax: `.className`.
  - Specificity: Lower specificity compared to ID.
  - **Use Case**: Ideal for styling multiple elements that share the same design (e.g., a button style applied across the site).

**Example**:

```css
#main-title {
  font-size: 30px;
  color: blue;
}

.button {
  background-color: green;
  color: white;
}
```

## **Inheritable and Non-Inheritable Properties**

- **Inheritable Properties**:
  - Some CSS properties are inheritable, meaning that child elements will inherit the styles applied to their parent.
  - **Example**: `font-family` in the `body` tag is inheritable, meaning that all elements within the `body` will inherit the font style unless overridden.

```css
body {
  background-color: rgb(255, 247, 201);
  font-family: Arial; /* This is inheritable */
  font-size: 20px;
  padding: 50px;
}

form {
  background-color: rgb(255, 220, 105);
  border: 5px solid #444; /* This is not inheritable */
  width: 400px;
  padding: 25px;
  margin-top: 30px;
}
```

- **Non-Inheritable Properties**:
  - Certain properties, like `border`, are not inherited by child elements. Each element must explicitly declare them if needed.

## **Global Reset: Why We Use `* { margin: 0; padding: 0; box-sizing: border-box; }`**

- **Purpose**:

  - The `*` selector applies styles to all elements. It resets `margin` and `padding` to `0` to eliminate browser inconsistencies in default spacing.
  - **`box-sizing: border-box;`**: Ensures that padding and borders are included within the element's total width and height, preventing layout issues.

- **Is It Necessary in Every CSS File?**
  - It’s not strictly required but is often used as a best practice for maintaining consistent layouts across different browsers.

**Explanation of `box-sizing: border-box;`**:

- Normally, when you add padding or border to an element, it increases its width/height. With `box-sizing: border-box;`, padding and borders are included inside the element’s width/height, preventing overflow and ensuring layout consistency.

- 例子：如果元素 `width: 400px; padding: 25px; border: 5px;`，在 `box-sizing: content-box;` 时，元素的实际宽度会变为 `460px`（400+25+25+5+5）。而在 `box-sizing: border-box;` 时，元素的宽度仍然保持 `400px`。

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

## **Block vs Inline Elements**

- **Block Elements**:
  - Occupy the full width available and always start on a new line.
  - Examples: `<div>`, `<h1>`, `<p>`.
  - **Use Case**: Used for large containers or sections of content.

```html
<div>This is a block element.</div>
<p>This is also a block element.</p>
```

- **Inline Elements**:
  - Occupy only the space necessary for their content and do not start on a new line.
  - Examples: `<span>`, `<a>`, `<strong>`.
  - **Use Case**: Used for styling text or small elements within a block-level element.

```html
<p>This is a block element with an <a href="#">inline link</a>.</p>
```

## **Example Notes**

```css
/* 1. ID vs Class */
#header {
  font-size: 36px; /* ID used for unique styling */
}

.button {
  background-color: green;
  padding: 10px; /* Class for reusable styles */
}

/* 2. Inheritance */
body {
  font-family: Arial; /* Inherited by all child elements */
}

form {
  border: 2px solid black; /* Not inherited */
}

/* 3. Reset and Box-Sizing */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box; /* Prevents overflow by including padding/border in width */
}

/* 4. Block and Inline Elements */
div {
  display: block; /* Block-level element */
}
/* 如果你希望 div 和 span 保持它们的默认行为，就不需要明确指定 display: block; 和 display: inline;，因为浏览器已经默认应用了这些显示属性。 */
span {
  display: inline; /* Inline element */
}
```

## **Responsive Design**

- viewport
- Media Queries
- Flexbox
- Grids

### **viewport**

`viewport` 元素可以控制网页在不同设备上的显示方式和缩放比例。代码中，`width=device-width` 表示将 viewport 的宽度设置为设备的屏幕宽度，`initial-scale=1.0` 表示将网页的初始缩放比例设置为 1.0，也就是不缩放。这样可以让网页适应不同大小的屏幕，实现响应式设计。

```html
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <!-- 其他的head元素 -->
</head>
<body>
  <!-- 网页的内容 -->
</body>
```

### **Media Queries**

`Media Queries` 的作用是实现响应式网页设计，让网页能够适应不同大小和分辨率的屏幕和设备。

```css
@media (min-width: 600px) {
  body {
    background-color: red;
  }
}
@media (max-width: 599px) {
  body {
    background-color: blue;
  }
}
```

### **Flexbox**

`Flexbox` 是 CSS3 中的一种布局模式，它可以让网页中的元素按照灵活的方式排列和对齐。

HTML 中：

```html
<div id="container">
  <div>1.This is some sample text inside of a div to dome Flexbox.</div>
  <div>2.This is some sample text inside of a div to dome Flexbox.</div>
  <div>3.This is some sample text inside of a div to dome Flexbox.</div>
  <div>4.This is some sample text inside of a div to dome Flexbox.</div>
  <div>5.This is some sample text inside of a div to dome Flexbox.</div>
  <div>6.This is some sample text inside of a div to dome Flexbox.</div>
  <div>7.This is some sample text inside of a div to dome Flexbox.</div>
  <div>8.This is some sample text inside of a div to dome Flexbox.</div>
</div>
```

CSS 中：

```css
#container {
  display: flex; /* 设置为flex布局 */
  flex-wrap: wrap; /* 允许项目换行 */
}
#container > div {
  background-color: springgreen;
  margin: 20px;
  padding: 20px;
  width: 200px;
}
```

### **Grids**

`Grids` 是 CSS3 中的另一种布局模式，它可以让网页中的元素按照二维的方式排列和对齐。Grids 的优点是可以创建复杂的网格结构，可以控制网格的行高和列宽，可以实现网页的响应式设计。

HTML 中：

```html
<div id="grid">
  <div class="grid-item">1</div>
  <div class="grid-item">2</div>
  <div class="grid-item">3</div>
  <div class="grid-item">4</div>
  <div class="grid-item">5</div>
  <div class="grid-item">6</div>
</div>
```

CSS 中：

```css
#grid {
  background-color: green;
  display: grid; /* 设置为grid布局 */
  padding: 20px;
  grid-column-gap: 20px;
  grid-row-gap: 10px;
  grid-template-columns: 200px 200px auto; /* 设置三列的宽度 */
}
.grid-item {
  background-color: springgreen;
  font-size: 20px;
  padding: 20px;
  text-align: center;
}
```

## **Bootstrap**

`BOOTSTRAP` 是一个开源的前端框架，它可以让开发者快速地创建响应式的网页和应用。BOOTSTRAP 提供了丰富的 `CSS` 样式，组件和 `JavaScript` 插件，可以方便地实现网页的布局，导航，表单，按钮，图标，模态框，轮播图，警告框等功能。

```html
<head>
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css"
  />
</head>
<body>
  <!-- 可直接使用Bootstrap组件里的代码 -->
  <div class="alert alert-primary" role="alert">
    A simple primary alert—check it out!
  </div>
</body>
```

### **Bootstrap’s grid system**

每行有 **12 个模板列**，允许您创建不同组合的元素，它们可以跨越任意数量的列。列类指示您想要使用的模板列的数量（例如，`.col-4` 跨越四个列）。

```html
<head>
  <title>My Web Page!</title>
  <link
    rel="stylesheet"
    href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
    integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
    crossorigin="anonymous"
  />
  <style>
    .row > div {
      padding: 20px;
      background-color: teal;
      border: 2px solid black;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="row">
      <div class="col-4">This is a section.</div>
      <div class="col-4">This is another section.</div>
      <div class="col-4">This is a third section.</div>
    </div>
  </div>
  <br />
  <div class="container">
    <div class="row">
      <div class="col-3">This is a section.</div>
      <div class="col-6">This is another section.</div>
      <div class="col-3">This is a third section.</div>
    </div>
  </div>
</body>
```

根据不同的屏幕尺寸( lg / sm )控制容器和列的大小和行为。

```html
<head>
  <title>My Web Page!</title>
  <link
    rel="stylesheet"
    href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
    integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
    crossorigin="anonymous"
  />
  <style>
    .row > div {
      padding: 20px;
      background-color: teal;
      border: 2px solid black;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="row">
      <div class="col-lg-3 col-sm-6">This is a section.</div>
      <div class="col-lg-3 col-sm-6">This is another section.</div>
      <div class="col-lg-3 col-sm-6">This is a third section.</div>
      <div class="col-lg-3 col-sm-6">This is a fourth section.</div>
    </div>
  </div>
</body>
```

## **Sass**

Syntactically Awesome Style Sheets 可以帮助您减少 CSS 的重复，节省时间，提高代码的可维护性。

### **Sass 支持变量**

- 创建单独的 Sass 文件，如 `variables.scss`

```scss
/* 定义变量 */
$color: red; /*如果颜色发生改变只需要改变变量即可*/

ul {
  font-size: 14px;
  color: $color;
}

ol {
  font-size: 18px;
  color: $color;
}
```

- 在< head >里用< link >引用，如：

```html
<link rel="stylesheet" href="variables.css" />
```

- **浏览器理解 CSS 但不理解 Sass** ，为解决这个问题，可以在电脑上直接安装 Sass ，或在终端使用 `sass variables.scss:variables.css` 命令进行**编译**，将 Sass 代码编译成标准的 CSS 代码。
- 终端使用 `sass --watch variables.scss:variables.css` 命令时，能在检测到 Sass 文件发生改变时，自动进行编译，将 Sass 代码编译成 CSS 代码，实现自动更新 CSS 代码。

### **Sass 中嵌套语法更简单**

While using Sass, we can also physically nest our styling rather than use the CSS selectors we talked about earlier. Sass 中：

```scss
div {
  font-size: 10px;

  p {
    color: blue;
  }

  ul {
    color: green;
  }
}
```

编译后生成的 CSS 中：

```css
div {
  font-size: 18px;
}

div p {
  /*Descendant Selector */
  color: blue;
}

div ul {
  /*Descendant Selector */
  color: green;
}
```

### **继承**

Sass 中：

```scss
%message {
  /*adding a % before a name of a class, adding some styling*/
  font-family: sans-serif;
  font-size: 18px;
  font-weight: bold;
  border: 1px solid black;
  padding: 20px;
  margin: 20px;
}

.success {
  @extend %message; /*adding the line @extend %classname to the beginning of some styling*/
  background-color: green;
}

.warning {
  @extend %message;
  background-color: orange;
}

.error {
  @extend %message;
  background-color: red;
}
```

HTML 中：

```html
<head>
  <title>My Web Page!</title>
  <link rel="stylesheet" href="inheritance.css" />
</head>
<body>
  <div class="success">This is a success message.</div>

  <div class="warning">This is a warning message.</div>

  <div class="error">This is an error message.</div>
</body>
```

### **父选择器 & ( Referencing Parent Selectors: & )**

#### **& 有以下几种用法**

- 与伪类或伪元素结合：你可以用&和伪类或伪元素配合使用，表示父选择器的某种状态或修饰。比如，你可以用 `&:focus` 来表示 `input:focus` ，表示 input 元素获得焦点时的样式。你也可以用 `&:hover` 来表示 `input[type="submit"]:hover` ，表示 input 元素类型为 submit 并且鼠标悬停时的样式。

Sass 中：

```scss
//定义一个input选择器，选择所有的<input>元素
input {
  font-size: 16px;
  width: 300px;
  padding: 13px 0;

  //使用&和:focus伪类结合，选择所有获得焦点的<input>元素
  &:focus {
    outline: none;
  }

  //使用&和属性选择器结合，选择所有类型为submit的<input>元素
  &[type="submit"] {
    font-size: 14px;
    width: 185px;
    /* Remove border */
    border-width: 0px;
    border-radius: 15px;
    margin: 20px;

    //使用&和:hover伪类结合，选择所有鼠标悬停的类型为submit的<input>元素
    &:hover {
      /* Add box-shadow when hovering button (border adds space) */
      box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.8);
    }
  }
}
```

编译后生成的 CSS 中：

```css
input {
  font-size: 16px;
  width: 300px;
  padding: 13px 0;
  /* Parent selector = & */
}
input:focus {
  outline: none;
}
input[type="submit"] {
  font-size: 14px;
  width: 185px;
  /* Remove border */
  border-width: 0px;
  border-radius: 15px;
  margin: 20px;
}
input[type="submit"]:hover {
  /* Add box-shadow when hovering button (border adds space) */
  box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.8);
}
```

---

- 与属性选择器结合：你可以用 `&` 和属性选择器配合使用，表示父选择器具有某种属性或属性值。比如，你可以用 `&[type="text"]` 来表示 `input[type="text"]` ，表示 input 元素类型为 text 的样式。你也可以用 `&[type="submit"]` 来表示 `input[type="submit"]` ，表示 input 元素类型为 submit 的样式。

Sass 中：

```scss
input {
  font-size: 16px;
  width: 300px;
  padding: 13px 0;

  //使用&和属性选择器结合，选择所有类型为text的<input>元素
  &[type="text"] {
    /* Give input text a lighter color */
    color: #464646;
    margin: 0 0 0 5px;
  }

  &[type="submit"] {
    font-size: 14px;
    width: 185px;
    /* Remove border */
    border-width: 0px;
    border-radius: 15px;
    margin: 20px;
  }
}
```

编译后生成的 CSS 中：

```css
input {
  font-size: 16px;
  width: 300px;
  padding: 13px 0;
  /* Parent selector = & */
}
input[type="text"] {
  /* Give input text a lighter color */
  color: #464646;
  margin: 0 0 0 5px;
}
input[type="submit"] {
  font-size: 14px;
  width: 185px;
  /* Remove border */
  border-width: 0px;
  border-radius: 15px;
  margin: 20px;
}
```

---

- 与类选择器结合：你可以用 `&` 和类选择器配合使用，表示父选择器同时具有某个类名。比如，你可以用 `&.blue-button` 来表示 `input.blue-button` ，表示 input 元素同时具有 blue-button 类名的样式。

Sass 中：

```scss
input {
  font-size: 16px;
  width: 300px;
  padding: 13px 0;

  //使用&和类选择器结合，选择所有同时具有blue-button类名的<input>元素
  &.blue-button {
    background-color: dodgerblue;
    color: white;
    font-size: smaller;
    max-width: 200px;
    border-radius: 0px;
    border: 1px solid #156bbd;
    float: right;
    padding: 10px 2px;
    margin: 0;
  }
}
```

编译后生成的 CSS 中：

```css
input {
  font-size: 16px;
  width: 300px;
  padding: 13px 0;
  /* Parent selector = & */
}
input.blue-button {
  background-color: dodgerblue;
  color: white;
  font-size: smaller;
  max-width: 200px;
  border-radius: 0px;
  border: 1px solid #156bbd;
  float: right;
  padding: 10px 2px;
  margin: 0;
}
```

---

- 与其他选择器拼接：你可以用 `&` 和其他选择器拼接，表示父选择器的一部分。比如，你可以用 `&-button` 来表示 `input-button` ，表示以 input-button 为选择器的样式。

Sass 中：

```scss
//定义一个.header选择器，选择所有具有header类名的元素
.header {
  display: flex;
  align-items: center;

  //使用&和其他选择器拼接，选择所有具有header-advanced类名的元素
  &-advanced {
    @extend .header;
    background-color: #f1f1f1;
    height: 50px;
  }

  //使用&和其他选择器拼接，选择所有具有header-advanced-logo类名的元素
  &-advanced-logo {
    @extend .header;
    padding: 10px;

    //使用嵌套的img选择器，选择所有父元素具有header-advanced-logo类名的<img>元素
    img {
      height: 30px;
    }
  }

  //使用&和其他选择器拼接，选择所有具有header-links类名的元素
  &-links {
    @extend .header;
    margin-left: auto;
  }
}
```

编译后生成的 CSS 中：

```css
/*如果使用了@extend指令，就会生成后代选择器，如果没有使用，就不会生成后代选择器。*/
.header,
.header-links,
.header-advanced-logo,
.header-advanced {
  display: flex;
  align-items: center;
}
/*因为使用了@extend指令，就会生成后代选择器*/
.header a,
.header-links a,
.header-advanced-logo a,
.header-advanced a {
  color: black;
  padding: 10px;
  text-decoration: none;
}
.header-advanced {
  background-color: #f1f1f1;
  height: 50px;
}
.header-advanced-logo {
  padding: 10px;
}
.header-advanced-logo img {
  height: 30px;
}
.header-links {
  margin-left: auto;
}
```

---

- 与后代选择器结合：你可以用 `&` 和后代选择器结合，表示父选择器的子孙元素。比如，你可以用 `.nav-menu &` 来表示 `.nav-menu input` ，表示 nav-menu 类名下的 input 元素的样式。

Sass 中：

```scss
//在sass中先写了子元素的效果，但在某种情况下需要进行覆盖时，可以使用选择器后面加&，注意中间要加空格。
a {
  color: red;

  //选择nav-menu类名下的所有<a>元素
  .nav-menu & {
    color: blue;
  }
}
```

编译后生成的 CSS 中：

```css
a {
  color: red;
}
/*后代选择器*/
.nav-menu a {
  color: blue;
}
```

---

#### **问题**

- 是不是在 `sass` 的嵌套代码里如果不使用 `&` ，就会产生后代选择器呢？

  - 是的。如果你在 `sass` 的嵌套代码里不使用 `&`，就会产生后代选择器。

- 什么情况下在 `sass` 的嵌套代码里不会产生后代选择器呢？
  - 如果你在 `sass` 的嵌套代码里使用了 `&` 符号，就不会产生后代选择器，而是会产生其他类型的选择器，比如多类选择器，伪类选择器，属性选择器等。


---

Add Sass: Parent Selectors: &