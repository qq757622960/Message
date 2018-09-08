> CSS 规范

> 代码风格

样式书写一般有两种：一种是紧凑格式 (Compact)
```
.lz{ display: block;width: 50px;}
```
一种是展开格式 (Expanded)
```
.lz{
    display: block;
    width: 50px;
}
```

团队约定
统一使用展开格式书写样式

### 代码大小写
样式选择器，属性名，属性值关键字全部使用小写字母书写，属性字符串允许使用大小写。
```
/* 推荐 */
.lz{
	display:block;
}
	
/* 不推荐 */
.lz{
	DISPLAY:BLOCK;
}
```

### 选择器

* 尽量少用通用选择器 `*`
* 不使用 ID 选择器
* 不使用无具体语义的标签选择器

```
/* 推荐 */
.lz {}
.lz li {}
.lz li p{}

/* 不推荐 */
*{}
#lz {}
.lz div{}
```

### 代码缩进

统一使用四个空格进行代码缩进，使得各编辑器表现一致（各编辑器有相关配置）
```
.lz {
    width: 100%;
    height: 100%;
}
```

### 分号

每个属性声明末尾都要加分号
```
.lz {
    width: 100%;
    height: 100%;
}
```

### 代码易读性
左括号与类名之间一个空格，冒号与属性值之间一个空格

*推荐*
```
.lz { 
    width: 100%; 
}
```

*不推荐*
```
.lz { 
    width:100%; 
}
```

逗号分隔的取值，逗号之后一个空格
*推荐*
```
.lz {
    box-shadow: 1px 1px 1px #333, 2px 2px 2px #ccc;
}
```

*不推荐*
```
.lz {
    box-shadow: 1px 1px 1px #333,2px 2px 2px #ccc;
}
```

为单个css选择器或新申明开启新行
*推荐*
```
.lz, 
.lz_logo, 
.lz_hd {
    color: #ff0;
}
.nav{
    color: #fff;
}
```

*不推荐*
```
.lz,lz_logo,.lz_hd {
    color: #ff0;
}.nav{
    color: #fff;
}
```

颜色值 rgb() rgba() hsl() hsla() rect() 中不需有空格，且取值不要带有不必要的 0

*推荐*
```
.lz {
    color: rgba(255,255,255,.5);
}
```

*不推荐*
```
.lz {
    color: rgba( 255, 255, 255, 0.5 );
}
```

属性值十六进制数值能用简写的尽量用简写
*推荐*
```
.lz {
    color: #fff;
}
```

*不推荐*
```
.lz {
    color: #ffffff;
}
```

### 属性书写顺序

建议遵循以下顺序：

1. 布局定位属性：display / position / float / clear / visibility / overflow
2. 自身属性：width / height / margin / padding / border / background
3. 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
4. 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …

```
.lz {
    display: block;
    position: relative;
    float: left;
    width: 100px;
    height: 100px;
    margin: 0 10px;
    padding: 20px 0;
    font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;
    color: #333;
    background: rgba(0,0,0,.5);
    -webkit-border-radius: 10px;
    -moz-border-radius: 10px;
    -o-border-radius: 10px;
    -ms-border-radius: 10px;
    border-radius: 10px;
}
```

> 注释规范

* 注释以字符 /* 开始，以字符 */ 结束
* 注释不能嵌套

```
/*Comment Text*/
```

## 团队约定
### 单行注释
注释内容第一个字符和最后一个字符都是一个空格字符，单独占一行，行与行之间相隔一行

*推荐*
```
/* Comment Text */
.lz{}

/* Comment Text */
.lz{}

```

*不推荐*
```
/*Comment Text*/
.lz{
	display: block;
}
.lz{
	display: block;/*Comment Text*/
}

```

### 模块注释
注释内容第一个字符和最后一个字符都是一个空格字符，/* 与 模块信息描述占一行，多个横线分隔符-与*/占一行，行与行之间相隔两行

*推荐*
```
/* Module A
---------------------------------------------------------------- */
.mod_a {}


/* Module B
---------------------------------------------------------------- */
.mod_b {}


```

*不推荐*
```
/* Module A ---------------------------------------------------- */
.mod_a {}
/* Module B ---------------------------------------------------- */
.mod_b {}
```

### 文件信息注释
在样式文件编码声明 @charset 语句下面注明页面名称、作者、创建日期等信息

```
@charset "UTF-8";
/**
 * @desc File Info
 * @author Author Name
 * @date 2015-10-10
 */
```

> SASS

### SASS 注释规范
SASS支持 CSS 标准的多行注释 /* */，同时也支持单行注释 //。
* 多行注释在使用非 Compressed 模式进行编译后的输出文件中会保留下来，单行注释 // 侧会被移除
* 多行注释和单行注释在 SASS 编译后输出的压缩 CSS 文件都会被移除
* 当多行注释内容第一个字符是感叹号 “!” 的时候，即 /*! */，SASS 无论用哪一种编译方式编译注释都会保留
* 注释内容可以加入 SASS 变量

### 团队约定
SCSS 文件内

* 全部遵循 CSS 注释规范
* 不使用 /*! */ 注释方式
* 注释内不放 SASS 变量

标准的注释规范如下：

```
@charset "UTF-8";

/**
 * @desc File Info
 * @author liqinuo
 * @date 2015-10-10
 */

/* Module A
----------------------------------------------------------------*/
.mod_a {}

/* module A logo */
.mod_a_logo {}

/* module A nav */
.mod_a_nav {}


/* Module B
----------------------------------------------------------------*/
.mod_b {}

/* module B logo */
.mod_b_logo {}

/* module B nav */
.mod_b_nav {}
```

## 嵌套规范
### 选择器嵌套

```
/* CSS */
.lz {}
body .lz {}

/* SCSS */
.lz {
    body & {}
}
```

```
/* CSS */
.lz {}
.lz_cover {}
.lz_info {}
.lz_info_name {}

/* SCSS */
.lz {
    &_cover {}
    &_info {
        &_name {}
    }
}
```

### 属性嵌套
```
/* CSS */
.lz {
    background-color: red;
    background-repeat: no-repeat;
    background-image: url(/img/icon.png);
    background-position: 0 0;
}

/* SCSS */
.lz {
    background: {
        color: red;
        repeat: no-repeat;
        image: url(/img/icon.png);
        position: 0 0;
    }
}
```

### 变量
可复用属性尽量抽离为页面变量，易于统一维护
```
// CSS
.lz {
    color: red;
    border-color: red;
}

// SCSS
$color: red;
.lz {
    color: $color;
    border-color: $color;
}
```

### 混合(mixin)
根据功能定义模块，然后在需要使用的地方通过 @include 调用，避免编码时重复输入代码段

```
// CSS
.lz_1 {
    -webkit-border-radius: 5px;
    border-radius: 5px;
}
.lz_2 {
    -webkit-border-radius: 10px;
    border-radius: 10px;
}

// SCSS
@mixin radius($radius:5px) {
    -webkit-border-radius: $radius;
    border-radius: $radius;
}
.lz_1 {
    @include radius; //参数使用默认值
}
.lz_2 {
    @include radius(10px);
}

// CSS
.lz_1 {
    background: url(/img/icon.png) no-repeat -10px 0;
}
.lz_2 {
    background: url(/img/icon.png) no-repeat -20px 0;
}

// SCSS
@mixin icon($x:0, $y:0) {
    background: url(/img/icon.png) no-repeat $x, $y;
}
.lz_1 {
    @include icon(-10px, 0);
}
.lz_2 {
    @include icon(-20px, 0);
}
```

### 占位选择器 %
如果不调用则不会有任何多余的 css 文件，占位选择器以 % 标识定义，通过 @extend 调用

```
//scss
%borderbox {
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}
.lz {
    @extend %borderbox;
}
```

### extend 继承
```
// CSS
.lz_1 {
    font-size: 12px;
    color: red;
}
.lz_2 {
    font-size: 12px;
    color: red;
    font-weight: bold;
}

// SCSS
.lz_1 {
    font-size: 12px;
    color: red;
}
.lz_2 {
    @extend .lz_1;
    font-weight: bold;
}

// 或者
%font_red {
    font-size: 12px;
    color: red;
}
.lz_1 {
    @extend %font_red;
}
.lz_2 {
    @extend %font_red;
    font-weight: bold;
}
```

### for 循环
```
// CSS
.lz_1 {background-position: 0 -20px;}
.lz_2 {background-position: 0 -40px;}
.lz_3 {background-position: 0 -60px;}

// SCSS
@for $i from 1 through 3 {
    .lz_#{$i} {
        background-position: 0 (-20px) * $i;
    }
}
```
注意：#{} 是连接符，变量连接使用时需要依赖

### each 循环
```
// CSS
.lz_list {
    background-image: url(/img/lz_list.png);
}
.lz_detail {
    background-image: url(/img/lz_detail.png);
}

// SCSS
@each $name in list, detail {
    .lz_#{$name} {
        background-image: url(/img/lz_#{$name}.png);
    }
}


// CSS
.lz_list {
    background-image: url(/img/lz_list.png);
    background-color: red;
}
.lz_detail {
    background-image: url(/img/lz_detail.png);
    background-color: blue;
}

// SCSS
@each $name, $color in (list, red), (detail, blue) {
    .lz_#{$name} {
        background-image: url(/img/lz_#{$name}.png);
        background-color: $color;
    }
}
```
注意：#{} 是连接符，变量连接使用时需要依赖

### function 函数
```
@function pxToRem($px) {
    @return $px / 10px * 1rem;
}
.lz {
    font-size: pxToRem(12px);
}
```

### 运算规范
运算符之间空出一个空格
```
.lz {
    width: 100px - 50px;
    height: 30px / 5;
}
```
注意运算单位，单位同时参与运算，所以 10px 不等于 10，乘除运算时需要特别注意

```
// 正确的运算格式
.lz {
    width: 100px - 50px;
    width: 100px + 50px;
    width: 100px * 2;
    width: 100px / 2;
}
```

> 重置样式
### 移动端

```
* { -webkit-tap-highlight-color: transparent; outline: 0; margin: 0; padding: 0; vertical-align: baseline; }
body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, dl, dt, dd, ul, ol, li, pre, form, fieldset, legend, button, input, textarea, th, td { margin: 0; padding: 0; vertical-align: baseline; }
img { border: 0 none; vertical-align: top; }
i, em { font-style: normal; }
ol, ul { list-style: none; }
input, select, button, h1, h2, h3, h4, h5, h6 { font-size: 100%; font-family: inherit; }
table { border-collapse: collapse; border-spacing: 0; }
a { text-decoration: none; color: #666; }
body { margin: 0 auto; min-width: 320px; max-width: 640px; height: 100%; font-size: 14px; font-family: -apple-system,Helvetica,sans-serif; line-height: 1.5; color: #666; -webkit-text-size-adjust: 100% !important; text-size-adjust: 100% !important; }
input[type="text"], textarea { -webkit-appearance: none; -moz-appearance: none; appearance: none; }

```

### PC 端

```
html, body, div, h1, h2, h3, h4, h5, h6, p, dl, dt, dd, ol, ul, li, fieldset, form, label, input, legend, table, caption, tbody, tfoot, thead, tr, th, td, textarea, article, aside, audio, canvas, figure, footer, header, mark, menu, nav, section, time, video { margin: 0; padding: 0; }
h1, h2, h3, h4, h5, h6 { font-size: 100%; font-weight: normal }
article, aside, dialog, figure, footer, header, hgroup, nav, section, blockquote { display: block; }
ul, ol { list-style: none; }
img { border: 0 none; vertical-align: top; }
blockquote, q { quotes: none; }
blockquote:before, blockquote:after, q:before, q:after { content: none; }
table { border-collapse: collapse; border-spacing: 0; }
strong, em, i { font-style: normal; font-weight: normal; }
ins { text-decoration: underline; }
del { text-decoration: line-through; }
mark { background: none; }
input::-ms-clear { display: none !important; }
body { font: 12px/1.5 \5FAE\8F6F\96C5\9ED1, \5B8B\4F53, "Hiragino Sans GB", STHeiti, "WenQuanYi Micro Hei", "Droid Sans Fallback", SimSun, sans-serif; background: #fff; }
a { text-decoration: none; color: #333; }
a:hover { text-decoration: underline; }
```

> 媒体查询

### 常用查询语句
判断设备横竖屏

```
/* 横屏 */
@media all and (orientation :landscape) {

} 

/* 竖屏 */
@media all and (orientation :portrait) {

}
```
判断设备宽高

```
/* 设备宽度大于 320px 小于 640px */
@media all and (min-width:320px) and (max-width:640px) {
    
}
```
判断设备像素比

```
/* 设备像素比为 1 */
@media only screen and (-webkit-min-device-pixel-ratio: 1), only screen and (min-device-pixel-ratio: 1) {
    
}

/* 设备像素比为 1.5 */
@media only screen and (-webkit-min-device-pixel-ratio: 1.5), only screen and (min-device-pixel-ratio: 1.5) {
    
}

/* 设备像素比为 2 */
@media only screen and (-webkit-min-device-pixel-ratio: 2), only screen and (min-device-pixel-ratio: 2) {
    
}
```

## 常用设备设置
### iPhones

```
/* ----------- iPhone 4 and 4S ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  and (-webkit-min-device-pixel-ratio: 2) {

}

/* Portrait */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: portrait) {
}

/* Landscape */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 480px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: landscape) {

}

/* ----------- iPhone 5 and 5S ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 568px)
  and (-webkit-min-device-pixel-ratio: 2) {

}

/* Portrait */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 568px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: portrait) {
}

/* Landscape */
@media only screen 
  and (min-device-width: 320px) 
  and (max-device-width: 568px)
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: landscape) {

}

/* ----------- iPhone 6 ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
  and (-webkit-min-device-pixel-ratio: 2) { 

}

/* Portrait */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: portrait) { 

}

/* Landscape */
@media only screen 
  and (min-device-width: 375px) 
  and (max-device-width: 667px) 
  and (-webkit-min-device-pixel-ratio: 2)
  and (orientation: landscape) { 

}

/* ----------- iPhone 6+ ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 414px) 
  and (max-device-width: 736px) 
  and (-webkit-min-device-pixel-ratio: 3) { 

}

/* Portrait */
@media only screen 
  and (min-device-width: 414px) 
  and (max-device-width: 736px) 
  and (-webkit-min-device-pixel-ratio: 3)
  and (orientation: portrait) { 

}

/* Landscape */
@media only screen 
  and (min-device-width: 414px) 
  and (max-device-width: 736px) 
  and (-webkit-min-device-pixel-ratio: 3)
  and (orientation: landscape) { 

}
```

### Galaxy Phones

```
/* ----------- Galaxy S3 ----------- */

/* Portrait and Landscape */
@media screen 
  and (device-width: 320px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 2) {

}

/* Portrait */
@media screen 
  and (device-width: 320px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 2) 
  and (orientation: portrait) {

}

/* Landscape */
@media screen 
  and (device-width: 320px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 2) 
  and (orientation: landscape) {

}

/* ----------- Galaxy S4 ----------- */

/* Portrait and Landscape */
@media screen 
  and (device-width: 320px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) {

}

/* Portrait */
@media screen 
  and (device-width: 320px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) 
  and (orientation: portrait) {

}

/* Landscape */
@media screen 
  and (device-width: 320px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) 
  and (orientation: landscape) {

}

/* ----------- Galaxy S5 ----------- */

/* Portrait and Landscape */
@media screen 
  and (device-width: 360px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) {

}

/* Portrait */
@media screen 
  and (device-width: 360px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) 
  and (orientation: portrait) {

}

/* Landscape */
@media screen 
  and (device-width: 360px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) 
  and (orientation: landscape) {

}
```

### HTC Phones
```
/* ----------- HTC One ----------- */

/* Portrait and Landscape */
@media screen 
  and (device-width: 360px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) {

}

/* Portrait */
@media screen 
  and (device-width: 360px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) 
  and (orientation: portrait) {

}

/* Landscape */
@media screen 
  and (device-width: 360px) 
  and (device-height: 640px) 
  and (-webkit-device-pixel-ratio: 3) 
  and (orientation: landscape) {

}
```

### iPads
```
/* ----------- iPad mini ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (-webkit-min-device-pixel-ratio: 1) {

}

/* Portrait */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (orientation: portrait) 
  and (-webkit-min-device-pixel-ratio: 1) {

}

/* Landscape */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (orientation: landscape) 
  and (-webkit-min-device-pixel-ratio: 1) {

}

/* ----------- iPad 1 and 2 ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (-webkit-min-device-pixel-ratio: 1) {

}

/* Portrait */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (orientation: portrait) 
  and (-webkit-min-device-pixel-ratio: 1) {

}

/* Landscape */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (orientation: landscape) 
  and (-webkit-min-device-pixel-ratio: 1) {

}

/* ----------- iPad 3 and 4 ----------- */

/* Portrait and Landscape */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (-webkit-min-device-pixel-ratio: 2) {

}

/* Portrait */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (orientation: portrait) 
  and (-webkit-min-device-pixel-ratio: 2) {

}

/* Landscape */
@media only screen 
  and (min-device-width: 768px) 
  and (max-device-width: 1024px) 
  and (orientation: landscape) 
  and (-webkit-min-device-pixel-ratio: 2) {

}
```

















> HTML 规范

> 代码规范

### 团队约定

HTML文件必须加上 DOCTYPE 声明，并统一使用 HTML5 的文档声明

```
<!DOCTYPE html>
```

### 团队约定
推荐使用属性值 cmn-Hans-CN（简体, 中国大陆），但是考虑浏览器和操作系统的兼容性，目前仍然使用 zh-CN 属性值

```
<html lang="zh-CN">
```

### 团队约定
一般情况下统一使用 “UTF-8” 编码

```
<meta charset="UTF-8">
```

> 书写风格

### HTML代码大小写

HTML标签名、类名、标签属性和大部分属性值统一用小写

*推荐*
```
<div class="demo"></div>
```

*不推荐*
```
<div class="DEMO"></div>
	
<DIV CLASS="DEMO"></DIV>
```

HTML文本、CDATA、JavaScript、meta标签某些属性等内容可大小写混合
```
<!-- 优先使用 IE 最新版本和 Chrome Frame -->
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1"/>

<!-- HTML文本内容 -->
<h1>I AM WHAT I AM </h1>

<!-- JavaScript 内容 -->
<script type="text/javascript">
	var demoName = 'demoName';
	...
</script>
	
<!-- CDATA 内容 -->
<script type="text/javascript"><![CDATA[
...
]]></script>
```

### 类型属性
不需要为 CSS、JS 指定类型属性，HTML5 中默认已包含

*推荐*

```
<link rel="stylesheet" href="" >
<script src=""></script>
```

*不推荐*
```
<link rel="stylesheet" type="text/css" href="" >
<script type="text/javascript" src="" ></script>
```

### 元素属性

* 元素属性值使用双引号语法
* 元素属性值可以写上的都写上

*推荐*

```
<input type="text">
	
<input type="radio" name="name" checked="checked" >
```

*不推荐*
```
<input type=text>	
<input type='text'>
	
<input type="radio" name="name" checked >
```

### 代码缩进
统一使用四个空格进行代码缩进，使得各编辑器表现一致（各编辑器有相关配置）

```
<div class="lz">
    <a href="#"></a>
</div>
```

### 纯数字输入框
使用 `type="tel"` 而不是 `type="number"`

```
<input type="tel">
```

### 代码嵌套
元素嵌套规范，每个块状元素独立一行，内联元素可选

*推荐*
```
<div>
    <h1></h1>
    <p></p>
</div>	
<p><span></span><span></span></p>
```

*不推荐*
```
<div>
    <h1></h1><p></p>
</div>	
<p> 
    <span></span>
    <span></span>
</p>
```

段落元素与标题元素只能嵌套内联元素

*推荐*
```
<h1><span></span></h1>
<p><span></span><span></span></p>
```

*不推荐*
```
<h1><div></div></h1>
<p><div></div><div></div></p>
```


> 注释规范

标准写法
```
<!--Comment Text-->
```

错误写法
```
<!-->The Wrong Comment Text-->

<!--->The Wrong Comment Text-->

<!--The--Wrong--Comment Text-->

<!--The Wrong Comment Text--->
```

## 团队约定
### 单行注释

一般用于简单的描述，如某些状态描述、属性描述等

注释内容前后各一个空格字符，注释位于要注释代码的上面，单独占一行

*推荐*
```
<!-- Comment Text -->
<div>...</div>
```

*不推荐*
```
<div>...</div><!-- Comment Text -->	
	
<div><!-- Comment Text -->
    ...
</div>
```

### 模块注释
一般用于描述模块的名称以及模块开始与结束的位置

注释内容前后各一个空格字符，`<!-- S Comment Text -->` 表示模块开始，`<!-- E Comment Text -->` 表示模块结束，模块与模块之间相隔一行

*推荐*
```
<!-- S Comment Text A -->	
<div class="mod_a">
    ...
</div>
<!-- E Comment Text A -->
	
<!-- S Comment Text B -->	
<div class="mod_b">
    ...
</div>
<!-- E Comment Text B -->
```

*不推荐*
```
<!-- S Comment Text A -->
<div class="mod_a">
    ...
</div>
<!-- E Comment Text A -->
<!-- S Comment Text B -->	
<div class="mod_b">
    ...
</div>
<!-- E Comment Text B -->

```

### 嵌套模块注释
当模块注释内再出现模块注释的时候，为了突出主要模块，嵌套模块不再使用

```
<!-- S Comment Text -->
<!-- E Comment Text -->
```

而改用
```
<!-- /Comment Text -->
```

注释写在模块结尾标签底部，单独一行。
```
<!-- S Comment Text A -->
<div class="mod_a">
		
    <div class="mod_b">
        ...
    </div>
    <!-- /mod_b -->
    	
    <div class="mod_c">
    	...
    </div>
    <!-- /mod_c -->
		
</div>
<!-- E Comment Text A -->
```

> 文件模板

HTML模版指的是团队使用的初始化HTML文件，里面会根据不同平台而采用不一样的设置，一般主要不同的设置就是 mata 标签的设置，以下是 PC 和移动端的 HTML 模版。

### HTML5 标准模板
```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>HTML5标准模版</title>
</head>
<body>
	
</body>
</html>
```

## 团队约定
### 移动端

```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, shrink-to-fit=no" >
<meta name="format-detection" content="telephone=no" >
<title>移动端HTML模版</title>
	
<!-- S DNS预解析 -->
<link rel="dns-prefetch" href="">
<!-- E DNS预解析 --> 

<!-- S 线上样式页面片，开发请直接取消注释引用 -->
<!-- #include virtual="" -->
<!-- E 线上样式页面片 -->

<!-- S 本地调试，根据开发模式选择调试方式，请开发删除 --> 
<link rel="stylesheet" href="css/index.css" >
<!-- /本地调试方式 -->

<link rel="stylesheet" href="http://srcPath/index.css" >
<!-- /开发机调试方式 -->
<!-- E 本地调试 -->

</head>
<body>

</body>
</html>
```

### PC

```
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="keywords" content="your keywords">
<meta name="description" content="your description">
<meta name="author" content="author,email address">
<meta name="robots" content="index,follow">
<meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">
<meta name="renderer" content="ie-stand">
<title>PC端HTML模版</title>

<!-- S DNS预解析 --> 
<link rel="dns-prefetch" href="">
<!-- E DNS预解析 --> 

<!-- S 线上样式页面片，开发请直接取消注释引用 -->
<!-- #include virtual="" -->
<!-- E 线上样式页面片 -->

<!-- S 本地调试，根据开发模式选择调试方式，请开发删除 --> 
<link rel="stylesheet" href="css/index.css" >
<!-- /本地调试方式 -->

<link rel="stylesheet" href="http://srcPath/index.css" >
<!-- /开发机调试方式 -->
<!-- E 本地调试 -->

</head>
<body>

</body>
</html>
```

##命名规范
###目录命名
>DOM结构、命名统一，维护起来更便捷，因而目录统一采用以下命名规则。

+ 项目文件夹：projectname
+ 样式文件夹：css
+  脚本文件夹：js
+  样式类图片文件夹：img
###HTML/CSS命名
>确保文件命名总是以字母开头而不是数字，且字母一律小写，以下划线连接且不带其他标点符号

######HTML

+ lz.html
+ lz_list.html
+ lz_detail.html


######CSS

+ lz.css
+ lz_list.css
+ lz_detail.css

###ClassName命名
>ClassName的命名应该尽量精短、明确，必须以字母开头命名，且全部字母为小写，单词之间统一使用下划线 “_” 连接

######命名原则
>基于姓氏命名法（继承 + 外来）,祖先模块不能出现下划线，除了是全站公用模块，如 `mod_` 系列的命名：

    <div class="modulename">
		<div class="modulename_info">
			<div class="modulename_son"></div>
			<div class="modulename_son"></div>
			...
		</div>
	</div>

    <!-- 这个是全站公用模块，祖先模块允许直接出现下划线 -->
	<div class="mod_info">
		<div class="mod_info_son"></div>
		<div class="mod_info_son"></div>
		...		
	</div>

>在子孙模块数量可预测的情况下，严格继承祖先模块的命名前缀

    <div class="modulename">
		<div class="modulename_cover"></div>
		<div class="modulename_info"></div>
	</div>

>当子孙模块超过4级或以上的时候，可以考虑在祖先模块内具有识辨性的独立缩写作为新的子孙模块

    <div class="modulename">
		<div class="modulename_cover"></div>
		<div class="modulename_info">
    		<div class="modulename_info_user">
    			<div class="modulename_info_user_img">
    				<img src="" alt="">
    				<!-- 这个时候 miui 为 modulename_info_user_img 首字母缩写-->
    				<div class="miui_tit"></div>
    				<div class="miui_txt"></div>
    				...
    			</div>
    		</div>
    		<div class="modulename_info_list"></div>
		</div>
	</div>
######模块命名
>全站公共模块：以`mod_` 开头

    <div class="mod_yours"></div>

>业务公共模块：以 业务名`_mod_ `开头

    <div class="paipai_mod_yours"></div>


##JS规范
###语言规范
####类型
######基本类型
+ 字符串
+ 数值
+ 布尔类型
+ null
+ undefined
######复杂类型
+ object
+ array
+ function
###引用
>const 和 let 都是块级作用域，var 是函数级作用域。

>复杂类型对所有引用都使用 const，不要使用 var

    const a = 1;
	const b = 2;

>如果引用是可变动的，则使用 let

    let count = 1
	if (count < 10) {
  		count += 1
	}


####对象
请使用字面量值创建对象

    const a = {}

>别使用保留字作为对象的键值，这样在 IE8 下不会运行

    const a = {
  		defaults: {},//注意这里尽量不要用default;default是保留字
  		common: {}
	}
>请使用对象方法的简写方式

    const item = {
  		value: 1,
  		addValue(val) {
    		return item.value + val
  		}
	}
>请使用对象属性值的简写方式

    const job = 'FrontEnd'
	const item = {
  		job
	}

>对象属性值的简写方式要和声明式的方式分组

    const job = 'FrontEnd'
	const department = 'JDC'
	const item = {
	  job,
	  department,
	  sex: 'male',
	  age: 25
	}

####数组
>请使用字面量值创建数组

    const items = []

>向数组中添加元素时，请使用 push 方法

    const items = []
	items.push('test')

>使用数组的 map 等方法时，请使用 return 声明，如果是单一声明语句的情况，可省略 return

	[1, 2, 3].map(x => {
	  const y = x + 1
	  return x * y
	})
	
	[1, 2, 3].map(x => x + 1) //单一声明语句情况 可以省略return


####字符串
>字符串统一使用单引号的形式 ''

    const department = 'JDC'

>字符串太长的时候，请不要使用字符串连接符换行 \，而是使用 +

	const str = '凹凸实验室 凹凸实验室 凹凸实验室' +
  		'凹凸实验室 凹凸实验室 凹凸实验室' +
  		'凹凸实验室 凹凸实验室'

>程序化生成字符串时，请使用模板字符串

    const test = 'test'
	const str = `ab${test}`

####函数
>请使用函数声明，而不是函数表达式

    // 函数表达式 不推荐
	const foo = function () {
	  // do something
	}
	
	// 函数声明推荐使用
	function foo () {
	  // do something
	}

>不要在非函数代码块中声明函数

    // 不推荐使用
	if (isUse) {
	  function test () {
	    // do something
	  }
	}
	
	// 推荐使用
	let test
	if (isUse) {
	  test = () => {
	    // do something
	  }
	}


>不要更改函数参数的值

    // 不推荐
	function test (opts) {
	  opts = opts || {}
	}
	
	// 推荐
	function test (opts = {}) {
	  // ...
	}

####模块
>使用标准的 ES6 模块语法 import 和 export

    // good
	import Util from './util'
	export default Util
	
	// better
	import { Util } from './util'
	export default Util


>不要使用 import 的通配符 *，这样可以确保你只有一个默认的 export
	
	//推荐
    import Util from './util'
	// 不推荐
	import * as Util from './util'


####对象属性
>使用 . 来访问对象属性

    const joke = {
	  name: 'haha',
	  age: 28
	}
	const name = joke.name

####变量声明
>声明变量时，请使用 const、let 关键字，如果没有写关键字，变量就会暴露在全局上下文中，这样很可能会和现有变量冲突，另外，也很难明确该变量的作用域是什么。这里推荐使用 const 来声明变量，我们需要避免全局命名空间的污染。

	const demo = new Demo()

>将所有的 const 和 let 分组

    const b
	const d
	let a
	let c
	let e

###代码规范

####单行代码块
>在单行代码块中使用空格

    function foo () { return true }
	if (foo) { bar = 0 }


####变量命名
>当命名变量时，主流分为驼峰式命名（variableName）和下划线命名（variable_name）两大阵营
>>团队约定使用驼峰式命名

####逗号空格
>逗号前后的空格可以提高代码的可读性，团队约定在逗号后面使用空格，逗号前面不加空格。

    var foo = 1, bar = 2
####逗号风格
>逗号分隔列表时，在 JavaScript 中主要有两种逗号风格：

+ 标准风格，逗号放置在当前行的末尾
+ 逗号前置风格，逗号放置在下一行的开始位置

>>团队约定使用标准风格

    var foo = 1,
    bar = 2

	var foo = ['name',
            	'age']

####函数调用
>为了避免语法错误，团队约定在函数调用时，禁止使用空格

    fn()

####缩进
>缩进统一使用四个空格

####构造函数首字母大写
>构造函数的首字母要大小，以此来区分构造函数和普通函数。

    var fooItem = new Foo()







    
   
    








