# GritBoy的*HTML学习笔记*
- - -
## HTML
### Hypertext Markup Language 超文本标记语言
* 超文本：网页上不光有文本，还有图片、音乐、视频
* 标记：是一种记号，标志
* 语言：就是代码
* HTML是一种规范，是一种标准，编写网页的一种标准
### HTML的主要目的
显示网页的不同效果、不同部分
## `<div>`和`<span>`标记
- 都是没有任何意义的标记，大多数情况下和CSS配合使用
- `<div>`是块元素，`<span>`是行内元素
- 块元素
	- 一般是单独占一行，不管内容多少，都是一行
- 行内元素
- 不会单独占一行
	- 多个行内元素会排在同一行
	- 行内元素的宽度，主要是根据内容决定
	- 在标记嵌套时，一般是块元素中嵌套行内元素

## 特殊符号
- 空格：&nbsp;代表一个半角空格。一个汉字的大小相当于两个半角空格
- <：`&lt`;
- `>`：`&gt`;
- &：`&amp`;
- ¥：`&yen`;
- ×：`&times`;
- ÷：`&divide`;
## HTML项目符号（无序列表）：块元素
```
<ul>
  <li>内容1</li>
  <li>内容2</li>
</ul>
```
- 在HTML标记中，内容应该放在最底层标记中
- `<ul>`或`<li>`的常用属性
  - Type：项目符号的类型，取值：disc（小黑点）、circle（空心圆）、square（实心方块）
## HTML编号列表：块元素
```
<ol>
  <li>内容1</li>
  <li>内容2</li>
</ol>
```
- `<ol>`或`<li>`的常用属性
  - type：标号类型，取值：1、a、A、i、I
  - start：从第几个开始编号
## 滚动字幕标记`<marquee>`
- 语法格式：`<marquee>滚动的内容</marquee>`
- 常用属性：
  - Direction：滚动方向，取值：up、down、left、right 
  - Width：滚动宽度
  - Height：滚动高度
  - BgColor：滚动背景色
  - ScrollAmount：滚动步长值。步长越大，滚动越快
  - ScrollDelay：两部之间的停留时间，以毫秒为单位
  - Loop：循环滚动次数
## 图片标记：行内元素，单边标记
- 语法格式：`<img 属性=“值”>`
- 常用属性：
  - Width：图片宽度
  - Height：图片高度
  - Border：图片边框粗细
  - Src：图片路径（一般是相对路径）
  - Align：图片的水平对齐方式，取值：left、center、right
  - Hspace：图片与左右文字之间的距离
  - Vspace：图片与上下文字之间的距离
- 如果图片想等比例缩放，只需要指定width或height其中一个
- Align属性只能让文本居中，不能让图片单独居中
  - Align可以实现图文混排效果。Align=“left | right”
  - 要想让图片实现居中效果，可以给图片增加一个`<div>`元素
## 超级链接：行内元素，不要嵌套
- 语法格式：`<a  属性=“值”>……</a>`
- 常用属性
  - Href：目标文件的地址URL，该URL可以是相对地址，也可以是绝对地址
  - Target：目标文件的显示窗口
    - _blank：在新窗口中打开目标文件
    - _self：在当前窗口中打开目标文件（默认打开），相当于替换操作
    - _parent：在父级窗口中打开目标文件
    - _top：在最顶级窗口中打开目标文件
    - **其中_parent、_top常用在框架网页中**
  - Name：定义锚点链接的名称
## URL
### 绝对地址URL
#### 远程绝对地址
- 访问远程的文件，总是以`http://`域名、主机名开头
#### 本地绝对地址（很少使用）
- 访问本地的文件，是以`file:///`开头的绝对地址
### 相对地址URL
- 当前文件与目标文件是同级关系，链接地址直接写目标文件名
- 当前文件与目标文件所在的文件夹是同级关系，先找“文件夹名”，然后再找“文件名”
- 目标文件位于上一层目录中，往上找对应的目录，再找目录中的文件
  - `../` 代表上一层目录，`../../` 代表上两层目录，以此类推
## 特殊链接
### 下载链接
- 什么样的文件会出现下载提示？
- 反过来说，哪些文件网页可以直接执行？如：.jpg，.png，.gif，.html，.htm，.txt等
- 大部分文件，浏览器是不能直接执行的。如：.doc， .xls，.ppt，等
### 邮箱链接
`<a href="mailto:+邮箱地址"></a>`
### 普通空链接（#）
`<a href="#"></a>`
### JS链接：添加JS功能代码
`<a href="javascript:windows.close()">关闭窗口</a>`
## 锚点链接
### 含义
锚点链接，是在一个网页的不同区域进行跳转。锚点可以理解为“定义记号”
### 锚点的使用需要两步
  1. 定义锚点（做个记号）：`<a name=”锚点名称”></a>`
    - 锚点名称的命名规则：可以包含字母、数字、下划线，但只能以字母开头
    - **注意：这里的`<a>`和`</a>`之间没有内容，不是为了让我们看见，而是给链接用的**
  2. 链接锚点（跳转到那个记号）：
### 语法：
`<a href="文件名#锚点名称">……</a>`
- **注意：这里的`<a>`和`</a>`之间要有内容**
## `<meta>`标记
### `<meta>`的主要作用
是提供网页的元信息。比如：指定网页的搜索关键字。
### `<meta>`标记有两个属性：http-equiv和name。
#### http-equiv属性
- 功能：模拟http协议文件头信息，当信息从服务器端传到客户端时，告诉浏览器如何正确的显示网页内容。
- 一般要与content属性配合使用。Content属性指定信息的详细参数。
- 设置网页的字符集：
`<meta http-equiv="Content-Type" content="text/html; charset=utf-8">`
- 自动刷新网页：
  - `<meta http-equiv="refresh" content="2">//每隔两秒钟刷新网页`
  - `<meta http-equiv="refresh" content="2;url="…"">//每隔两秒钟跳转到url指定的网页`
#### name属性
- name属性主要用于设置网页的搜索关键字、版权信息、作者等。
- 设置网页搜索关键字。
`<meta name="keywords" content="……">`
- 设置网页描述信息。
`<meta name="description" content="……">`
## XHTML
### 简介
- 传统的HTML开发的初衷是面向pc机的，而随着移动端的不断涌现，HTML已经满足不了市场的需求了。
- XHTML是新一代的HTML语言。XHTML的目的是为了取代HTML。
- XHTML的标记与HTML一模一样。
- XHTML的语法要比HTML严格的多。
- XHTML：可扩展超文本标记语言。
### 编写规范
- 所有的标记都要全小写。
- 单边标记必须要关闭。如：`<br>` -----> `<br />`
- 所有的属性值都必须要加引号。
- 所有的属性都必须有值。如：`<hr noshade>` ----> `<hr noshade=”noshade” />`
- 标记之间要顺序嵌套，外层套内层，一层套一层。
- XHTML网页，必须要有DTD文档类型定义代码。
### DTD文档类型定义
#### DTD文档类型定义的目的
一种验证机制，检验你写的XHTML标记语法是否合法。
#### DTD一共有三大分类：
1. 严格型的DTD
- 不能再使用各种表现的标记。如`<font>`、`<b>`、`<body bgColor>`
- 要求必须使用CSS	来取代各种表现标记
- `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">`
2. 过渡型的DTD
- 可以继续使用HTML中的表现的写法
- 这些表现标记，还可以继续使用，如`<font>`、`<b>`、`<body bgColor>`
- `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">`
3. 框架型的DTD
- `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">`
## 表格标签：块元素
### 表格的结构
```
<!--两行两列表格-->
<table>
<tr>
  <td>……</td>
  <td>……</td>
</tr>
<tr>
  <td>……</td>
  <td>……</td>
</tr>
</table>
```
### `<table>`属性
- Width：表格宽度，单位可以是百分比，也可以是固定值
- Align：表格水平对齐方式。取值：left、center、right
- Height：表格高度
- Border：边框粗细
- Bordercolor：边框颜色
- BgColor：表格背景色
- Background：背景图片url
- Cellpadding：单元格边线到内容间的距离（填充距离）
- Cellspacing：单元格与单元格之间的距离（间距）
- Rules：合并单元格边框线。取值：all
- **注意：rules兼容性不好，请用CSS来取代它**
### `<tr>`属性
- Bgcolor：行背景色
- Height：行的高度
- Align：行中的文本水平居中
- Valign：垂直居中。取值：top、middle、bottom
### `<td>`（普通单元格）/`<th>`（标题单元格，默认居中加粗显示内容）属性
- Width：单元格宽度
- Height：单元格高度
- Bgcolor：单元格背景色
- Background：单元格背景图片
- Align：水平对齐
- Valign：垂直对齐
- Rowspan：上下单元格合并
  - 合并属性必须放在第一个单元格中。
- Columnspan：左右单元格合并
  - 合并时，有增就有减，要保证每一行单元格的个数不变。
## 表单：块元素
### 表单的概念
表单主要用于获取客户端用户数据。如注册表单、查询表单、登录表单等。
### 表单的工作原理
1. 浏览有表单的网页，填写一些必要的信息，然后点击某个按钮进行提交。
2. 这些表单数据通过互联网传递到了服务器上。
3. 服务器上有专门的程序对表单数据进行验证。
4. 服务器返回验证结果信息。

从上面表单的工作原理来看：表单的制作分两个部分，一是**前台页面**的制作，二是**后台PHP**对表单数据的处理。
### 表单的结构
```
<form name="form1">
  用户名：<input type="text" name="username">
  密码：<input type="password" name="userpassword">
  <input type="submit" value="提交表单">
</form>
```
### `<form>`标记属性 
- `name`：给表单起个名字。这个名字主要给JavaScript来进行客户端表单验证。
- `method`：指定表单的提交方式。取值：`get`、`post`。
- `action`：指定表单的处理程序，一般是PHP文件。
  - *如果`action`为空，那么表单数据发送到哪里去了？*
  - *答：提交给了当前文件自己来处理*
- `enctype`：指定表单数据的编码方式（加密方式）。这个属性只能用在`method="post"`方式下。
  - `application/x-www-form-urldecoded` //**默认的加密方式**
  - `multipart/form-data` //**如果你要上传文件，属性值必须为它**
#### GET方法和POST方法
##### GET提交方式（基本上用不着）
将表单数据追加到`action`指定的处理程序的后面，然后向服务器发出请求。
**注意：地址栏传数据的方式默认就是GET方式。**
例：
> file:///E:itcast/20150608/lesson/day3/login.php?username=yao&userpwd=123456

上面URL的说明：
- `login.php` //表单处理程序文件
- `username=yao&userpwd=123456` //表单提交的数据，又称**查询字符串**
- `action`文件和查询字符串之间用`?`分隔。 
- 每两个表单元素的`名称=值`之间用`&`分隔。
- 表单名称和值之间用`=`分隔。

**如果某个表单元素不想往服务器传递数据，那么我们可以不给它添加`name`属性。**
**传递到服务器的数据，如果没有name，则无法获取它的值**。
###### GET方式的特点
1. GET方式不能提交敏感数据，如：密码。
2. GET方式只能提交少量数据。因为地址栏的长度有限制。
3. GET方式不能传递附件。
##### POST提交方式（常用方式）
POST提交方式，它不是将表单数据追加到地址上，而是直接传给表单处理程序。
###### POST提交方式的特点
1. POST方式提交的数据相对安全。
2. POST方式可以提交海量数据。
3. POST方式可以上传附件。
### 单行文本域
#### 语法格式
```
<input type="text" 属性="值">
```
#### 常用属性
- `name`：文本框的名字。命名规则：可以包含字母、数字、下划线，但**只能以字母开头**。
- `type`：表单元素的类型。
- `value`：文本框中的值。
- `size`：文本框的长度。以字符为单位。
- 