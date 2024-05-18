# [HTML和CSS实现Google Image Search样式](https://github.com/hadleysu/gitblog/issues/10)

# HTML和CSS实现Google Image Search样式

- [HTML和CSS实现Google Image Search样式](#html和css实现google-image-search样式)
  - [参考文档](#参考文档)
  - [代码](#代码)
  - [实现 Google 图标与 images 之间的相对位置，且整体水平居中](#实现-google-图标与-images-之间的相对位置且整体水平居中)
    - [相对位置](#相对位置)
    - [容器水平居中](#容器水平居中)
      - [一种方法是使用 CSS 的 `transform` 属性](#一种方法是使用-css-的-transform-属性)
      - [另一种方法是使用 `margin: 0 auto;` 配合固定宽度](#另一种方法是使用-margin-0-auto-配合固定宽度)

## 参考文档

- [W3Schools - css position](https://www.w3schools.com/css/css_positioning.asp)

- [阮一峰 CSS 定位详解](https://www.ruanyifeng.com/blog/2019/11/css-position.html)
  
  - `static` `relative` `fixed` `absolute` `sticky`
  
- [MDN - css display](https://developer.mozilla.org/en-US/docs/Web/CSS/display)
  
  - `block` `inline` `inline-block` `flex` `grid`

- [MDN - css transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)

- [MDN -css margin](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)

  - `margin-top` `margin-right` `margin-bottom` `margin-left`

- [Bootstrap - Grid](https://getbootstrap.com/docs/5.3/layout/grid/)

- [Bootstrap - Columns](https://getbootstrap.com/docs/5.3/layout/columns/)

## 代码

HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Images</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container-fluid">
        <ul class="nav nav-underline justify-content-end p-2">
            <li class="nav-item">
                <a class="nav-link text-dark" href="index.html">Google</a>
            </li>
            <li class="nav-item">
                <a class="nav-link text-dark" href="advanced.html">Advanced</a>
            </li>
        </ul>
        <div class="image-logo">
            <!-- Google图标 -->
            <img src="https://www.google.com/images/branding/googlelogo/1x/googlelogo_color_272x92dp.png" class="rounded mx-auto d-block" alt="Google Images">
            <!-- "images"文字 -->
            <div class="images-text text-primary">
                <span>images</span>
            </div>
        </div>  
        <div class="mt-4 text-center">
            <form id="searchForm" class=" row justify-content-center" action="https://www.google.com/search">
                <div class="col-md-6">
                    <div class="input-group">
                        <span class="input-group-text">
                            <i class="bi bi-search"></i>
                        </span>
                        <input type="text" class="form-control form-control-lg" name="q">
                        <input type="hidden" name="tbm" value="isch">
                    </div>
                    <button type="submit" form="searchForm" class="btn btn-light me-2 mt-4">Images Search</button>
                </div>    
            </form>
        </div> 
    </div>
</body>
</html>
```

CSS:

```css
.image-logo {
    position: relative; /* 相对定位，为内部绝对定位元素提供参照 */
    display: inline-block; /* 使容器的宽度适应内容 */
    transform: translateX(-50%);/*将容器水平移动自身宽度的一半,达到水平居中的效果。*/
    left: 50%;/*将容器的左边缘移动到页面中心*/
}

.google-logo {
    width: 272px; 
    height: auto; /* 高度自动，保持宽高比 */
}

.images-text {
    position: absolute; /* 绝对定位 */
    bottom: 0; 
    right: 1px; 
}

/* 另一种方法是使用 margin: 0 auto; 配合固定宽度。
.image-logo 容器被设置为 position: relative; 
并且有一个固定的宽度。使用 margin: 0 auto; 将容器水平居中。*/
/* 
.image-logo {
    position: relative;
    width: 272px; 设置固定宽度
    margin: 0 auto; 水平居中
}

.google-logo {
    width: 100%;
    height: auto;
}

.images-text {
    position: absolute;
    bottom: 0;
    right: 1px;
} */
```

## 实现 Google 图标与 images 之间的相对位置，且整体水平居中

### 相对位置

将问题转化为我们有一个大容器元素和一个小容器元素,需要将小容器放置在大容器的右下角某个位置。我们可以使用 CSS 的绝对定位属性来实现这一目标。

具体步骤如下:

1. **设置父容器为相对定位**
   - 将大容器的 `position` 属性设置为 `relative`。这样可以为子元素提供一个相对定位的参考点。

2. **设置子容器为绝对定位**
   - 将小容器的 `position` 属性设置为 `absolute`。这样可以脱离文档流,使其可以相对于父容器进行定位。

3. **定位子容器的位置**
   - 使用 `right` 和 `bottom` 属性来控制小容器相对于父容器的水平和垂直位置。例如 `right: 20px; bottom: 30px;` 将把小容器放置在父容器的右下角,距离边缘分别为 20px 和 30px。

- **还有重要的一点，父容器的大小要正好是 Google 图标的大小，这样才好调整 images 文字的位置**。这样的样式设置才能保证，Google 图标与 images 之间的相对位置不会随着屏幕大小的改变而改变。

  - `display: inline-block;` or `width: 272px;` 要么使容器的宽度适应内容，而非占整行的宽度；要么设置固定宽度（即Google图标的宽度）。

### 容器水平居中

#### 一种方法是使用 CSS 的 `transform` 属性

```css
.image-logo {
    position: relative;/* 相对定位，为内部绝对定位元素提供参照 */
    display: inline-block; /* 使容器的宽度适应内容 */
    transform: translateX(-50%);/*将容器水平移动自身宽度的一半,达到水平居中的效果。*/
    left: 50%;/*将容器的左边缘移动到页面中心*/
}

.google-logo {
    width: 272px;
    height: auto;/* 高度自动，保持宽高比 */
}

.images-text {
    position: absolute;/* 绝对定位 */
    bottom: 0;
    right: 1px;
}
```

在这个例子中:

1. `.image-logo` 容器被设置为 `position: relative;`。
2. 使用 `transform: translateX(-50%);` 将容器水平移动自身宽度的一半,达到水平居中的效果。
3. 同时设置 `left: 50%;` 将容器的左边缘移动到页面中心。

#### 另一种方法是使用 `margin: 0 auto;` 配合固定宽度

```css
.image-logo {
    position: relative;
    width: 272px; /* 设置固定宽度 */
    margin: 0 auto; /* 水平居中 */
}

.google-logo {
    width: 100%;
    height: auto;
}

.images-text {
    position: absolute;
    bottom: 0;
    right: 1px;
}
```

在这个例子中:

1. `.image-logo` 容器被设置为 `position: relative;` 并且有一个明确的宽度。
2. 使用 `margin: 0 auto;` 将margin的水平值设为auto，实现容器水平居中。
