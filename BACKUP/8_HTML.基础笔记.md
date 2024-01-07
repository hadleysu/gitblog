# [HTML 基础笔记](https://github.com/hadleysu/gitblog/issues/8)

# HTML 基础笔记

## HTML 能解决什么样的问题

HyperText Markup Language which is a language that we can use to describe the structure of the webpage.All of the buttons and the text, and the forms and other parts of the webpage that the user ultimately sees and interacts with. [HTML（超文本标记语言） | MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTML)

## 1st HTML

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

## DOM

Document Object Model(文档对象模型)The tree like structure that describes how all of these HTML elements are related to each other.

## tags

|           |                                   |
|-----------|-----------------------------------|
| h1        | heading，h1~h6                    |
| ol        | ordered list                      |
| ul        | unordered list                    |
| li        | list item ，嵌套在ol/ul里使用        |
| img       | image，required attributes（src/alt/width）|
| a         | anchor 超链接，attribute(href)     |
| table     | 表格                               |
| thead     | 表头                               |
| th        | 表头单元格                          |
| tbody     | 表体                               |
| tr        | table row                          |
| td        | table data                         |
| form      | 表单                               |
| input     | 输入框，attribute(type/placeholder/name/list) |
| datalist  | 定义一个输入候选列表,需要和input标签配合使用|
| option    | 定义datalist列表中每个候选项的值，即下拉菜单的内容。|

## attributes

|            |                                     |
|------------|-------------------------------------|
| src        | source                              |
| alt        | alternative text (用文字描述图片内容 )|
| width      | 宽度                                 |
| href       | hyperlink reference                  |
| type       | 表单控件类型（如text/submit/radio/password） |
| placeholder| 当没有值设定时，出现在表单控件上的文字         |
| name       | 表单的控件名称，作为键值对的一部分与表单一同提交|
| list       | input 标签的 list 属性是 datalist 标签的 id 属性的值，相互关联|

datalist标签和option标签的一个例子是：

```html
<label for="city">请选择您的城市：</label>
<input type="text" id="city" list="city-list">
<datalist id="city-list">
    <option value="北京">
    <option value="上海">
    <option value="广州">
    <option value="深圳">
</datalist>
```

- datalist标签可以定义一个输入候选列表，option标签可以定义每个候选项的值。
- datalist标签需要和input标签配合使用，通过input标签的list属性来指定要关联的datalist标签的id属性。这样，当用户在input标签的输入框中输入或点击时，就会显示datalist标签中的候选列表，用户可以从中选择一个或者自己输入一个值。
