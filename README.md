
## 前端代码规范
[通用规范](#general)

[Javascript规范](#javascript)  

[HTML规范](#HTML)  

[CSS规范](#CSS)  



###  <a id="general"></a>通用规范
- **缩进**：统一使用四空格缩进
- **分号**：语句结束不可省略分号，依靠隐形分割代码可读性差，容易带来很多问题。
- **命名**：文件和文件夹的命名
	- 尽量使用名词命名
	- 命名尽量有语义, 代替不必要的注释
	- 使用英文单词，在语义化优化的情况下可使用缩写，规避拼音的使用
	- 推荐使用中划线`-`,不推荐使用下划线`_`
	- 文件和文件夹命名不使用驼峰，为了提高可读性，全部使用小写字母
	- Javasript、HTMl、CSS的变量名命名规范详见文档
	
 ![](https://ooo.0o0.ooo/2017/06/16/59434b07259d0.jpeg)

### <a id="javascript"></a>Javascipt规范
#### 要怎么做
- 变量声明必须使用var/let/const(注意let和const的兼容性)
- 逗号放在行尾
- 单引号 `'`优于双引号`"`

- **空格**
	- 对象属性声明的冒号`:`**后**，加空格
	```javascript
   var person = {
       name: 'Frank',
       sex: 'male',
       age: 26,
       ...
       birth: '1990-01-01'
   }
	```
	- 参数间的逗号**后**，加空格
	```javascript
    funciton foo(param1, param2, param3)
    ```
	- 条件语句`if`、`else`、`switch`...后，加空格
	- 开始大括号前，结束大括号**后**，加空格
	```javascript
        if (conditon) {
           ...  
        } else {
           ...
        }
    ```
	- 等号`=` `>` `+` `||`等运算符和逻辑运算符**前后**均加空格
	- 函数名后不加空格, 匿名函数`funciton`后不加空格
	```javascript
       funtion foo() {
          //do something
       }
       
       
       var foo = function() {
          //do something
       }
    ```


- **命名**
    - 变量名驼峰首字母小写： variableNamesLikeThis
	- 函数和方法驼峰命名首字母小写： functionNamesLikeThis, methodNameLikeThis
	- 类名枚举类型驼峰首字母大写： ClassNamesLikeThis, EnumNamesLikeThis
	- 常量下划线全部大写： SYMBOLIC_CONSTANTS_LIKE_THIS

#### 不要出现什么
- 不要在块内声明函数
  - 不要写成
   ``` javascript
  	 if (x) {
        function foo() {}
  	 }
	```
   - 可以写成
	``` javascript
  	 if (x) {
        var foo = function() {}
  	 }
	```

### <a id="HTML"></a>HTML规范

- 属性上使用双引号，不要使用单引号
- 使用这个简单地 doctype 来启用标准模式: ``` HTML <!DOCTYPE html> ```
- **字符编码**：通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式。这样做之后，需要避免在 HTML 中出现字符实体，直接提供字符与文档一致的编码（通常是 UTF-8）
``` HTML
<head>
  <meta charset="UTF-8">
</head>
```
- **IE 兼容模式**: Internet Explorer 支持使用兼容性 <meta> 标签来指定使用什么版本的 IE 来渲染页面。如果不是特殊需要，通常通过 edge mode 来通知 IE 使用最新的兼容模式。
``` HTML
   <meta http-equiv="X-UA-Compatible" content="IE=Edge">
```
- **属性顺序**
   属性应该尽量按照特定的顺序出现以保证易读性。
  - class
  - id, name
  - data-*
  -  src, for, type, href, value
  -  title, alt
  -  自定义指令

- **引入 CSS 和 JavaScript**:根据 HTML5 规范, 通常在引入 CSS 和 JavaScript 时不需要指明 type，因为 text/css 和 text/javascript 分别是他们的默认值。
``` HTML
<!-- External CSS -->
<link rel="stylesheet" href="code-guide.css">

<!-- In-document CSS -->
<style>
  /* ... */
</style>

<!-- JavaScript -->
<script src="code-guide.js"></script>

```


#### 推荐写法

``` HTML
<!DOCTYPE html>
<html>
  <head>
    <meta charset = "UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    <link rel="stylesheet" href="code-guide.css">
    <title>Page title</title>
    <style>
      /* ... */
    </style>
  </head>
  <body>
    <img class="coetent-header" id="company-avatar" src="images/company-logo.png" alt="Company">
    <h1 class="hello-world">Hello, world!</h1>
  </body>
  <script src="code-guide.js"></script>
</html>
```


### <a id="CSS"></a>CSS规范

- css 换行式书写，不使用一行式
	- 推荐采用
  ```CSS
    .demo-class {
        font-size: 12px;
        padding: 10px;
        margin: .5em;
    }
  ```
  - 不推荐采用
  ```CSS
    .demo-class {font-size: 12px;padding: 10px;magin: .5em;}
  ```
- 所有声明应该以分号结尾。虽然最后一条声明后的分号是可选的，但是如果没有他，你的代码会更容易出错
- 声明块的右括号应该另起一行
- 0后面不要加上单位，比如使用 `margin: 0`; 而不是 `margin: 0px`;
- 小数前不要加上0，比如使用`margin: .5em`;而不是 `margin: 0.5em`;
- **空格** 
	- 逗号分隔的取值，都应该在逗号之后增加一个空格，但不要在颜色值 rgb(), rgba(), hsl(), hsla(), 和 rect() 中增加空格
	```CSS
    /*bad Style*/
    .class-name,.class-type,.class-style {
       margin: 10px;
       background-color: rgb(0, 10, 20);
    }
    
    /*better style*/
    .class-name, .class-type, .class-style {
       margin: 10px;
       background-color: rgb(0,10,20);
    }
    ```
	- 每条声明 : 后应该插入一个空格
	- 为了代码的易读性，在每个声明的左括号前增加一个空格

- **命名**
  - 保持 Class 命名为全小写
  - 可以使用短划线（不要使用下划线和 驼峰 className 命名）进行分割
- **代码组织**
	- 推荐使用 `base.css`，`common.css`，`page.css`三层命名结构
	- 推荐[base.css](web-guide/css/base.css)





[参考推荐网站](https://github.com/icepy/Front-End-Develop-Guide)


