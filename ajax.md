# jQuery - Ajax

AJAX 是一个首字母缩写，代表异步 JavaScript 和 XML，这一技术帮助我们在没有浏览页面刷新的情况下从服务器加载数据。

如果你对 AJAX 比较陌生，我建议你在学习本教程之前先去浏览一下我们的 [**Ajax 教程**](http://www.tutorialspoint.com/ajax/)。

JQuery 是一个伟大的工具，提供了一组丰富的 AJAX 方法来开发下一代 web 应用程序。

## 下载简单的数据

使用 jQuery AJAX 来下载任何静态或动态的数据都是非常简单的。jQuery 提供了 **load()** 方法来实现这一功能 ——

### 语法

这是 **load()** 方法的简单语法 ——

``` 
[selector].load( URL, [data], [callback] );
```

这是所有参数的描述 ——

- **URL ——** 服务器端 URL 向发送请求的一端提供资源。可能是一个 CGI、ASP、JSP、PHP 脚本，能够动态生成数据或数据库。

- **data ——** 这一可选参数代表了一个对象，它的属性被序列化到要传递给请求端的正确编码的参数。如果指定了，那么请求是由 **POST** 方法实现的。如果省略了，那么请求是由 **GET** 方法实现的。

- **callback ——** callback 函数在请求数据被加载到匹配集合的元素后调用。向该函数传递的第一个参数是来自服务器端的响应文本，第二个参数时状态码。

### 示例

考虑下面这个带有一小段 jQuery 编码的 HTML 文件 ——

``` 
<html>
   <head>
      <title>The jQuery Example</title>
      <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
		
      <script type="text/javascript" language="javascript">
         $(document).ready(function() {
            $("#driver").click(function(event){
               $('#stage').load('/jquery/result.html');
            });
         });
      </script>
		
   </head>
	
   <body>
	
      <p>Click on the button to load /jquery/result.html file −</p>
		
      <div id="stage" style="background-color:cc0;">
         STAGE
      </div>
		
      <input type="button" id="driver" value="Load Data" />
		
   </body>
	
</html>
```

这里 **load()** 起订一个 Ajax 请求到指定的 URL **/jquery/result.html** 文件。加载这个文件后，所有的内容将会被填充到 ID 为 *stage* 的 < div> 标签内。假设，我们的 /jquery/result.html 文件只有一个 HTML 行——

``` 
< h1>THIS IS RESULT...</h1>
```

当点击给定的按钮后，result.html 文件开始被加载。

![](images\ajax-jt-1.png)

## 获取 JSON 数据

有可能会出现返回的 JSON 字符串与你的请求不符的情况。jQuery 使用 **getJSON()** 函数解析返回 JSON 字符串并使结果字符串作为第一个参数以进行后续的操作对回调函数是可用的。

### 语法

这是 **getJSON()** 方法的简单语法 ——

``` 
[selector].getJSON( URL, [data], [callback] );
```

这是所有参数的描述 ——

- **URL ——** 服务器端资源的 URL 通过 GET 方法取得联系。

- **data ——** 一个对象，它的属性作为名称/值对，用于构造一个要被附加到 URL 上的字符串，或者预先格式化并编码的查询字符串。

- **callback ——** 一个函数，当请求完成时会被调用。产生于响应体的数据值，作为一个 JSON 字符串，要被当作第一个参数传递给这个回调，第二个参数时状态。

### 示例

考虑下面的带有一小段 jQuery 编码的 HTML 文件 ——

``` 
<html>
   <head>
      <title>The jQuery Example</title>
      <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
		
      <script type="text/javascript" language="javascript">
         $(document).ready(function() {
            $("#driver").click(function(event){
               $.getJSON('/jquery/result.json', function(jd) {
                  $('#stage').html('<p> Name: ' + jd.name + '</p>');
                  $('#stage').append('<p>Age : ' + jd.age+ '</p>');
                  $('#stage').append('<p> Sex: ' + jd.sex+ '</p>');
               });
            });
         });
      </script>
		
   </head>
	
   <body>
	
      <p>Click on the button to load result.json file −</p>
		
      <div id="stage" style="background-color:#eee;">
         STAGE
      </div>
		
      <input type="button" id="driver" value="Load Data" />
		
   </body>
	
</html>
```

这里 JQuery 使用 **getJSON()** 方法来启动一个 Ajax 请求道指定的 URL **result.json** 文件中。在加载这个文件后，所有的内容会被传递到回调函数，最终会填充到 ID 为 *stage* 的 < div> 标签内部。假设，我们的 result.json 文件有下述 json 格式的内容 ——

``` 
{
"name": "Zara Ali",
"age" : "67",
"sex": "female"
}
```

当你点击给定的按钮时，result.json 文件就开始加载 ——

![](images\ajax-jt-2.png)

## 传递数据到服务器

许多情况下，你从客户端收集输入并把这些输入传递到服务器端以做进一步处理。JQuery AJAX 使用任何可用的 Ajax 方法的 **data** 参数，使得将收集的数据传递到服务器端变得容易。

### 示例

这个例子解释了怎样将客户端的输入传递到 web 服务器脚本，它会发送相同的结果，然后我们可以输出它 ——

``` 
<html>
   <head>
      <title>The jQuery Example</title>
      <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
		
      <script type="text/javascript" language="javascript">
         $(document).ready(function() {
            $("#driver").click(function(event){
               var name = $("#name").val();
               $("#stage").load('/jquery/result.php', {"name":name} );
            });
         });
      </script>
		
   </head>
	
   <body>
	
      <p>Enter your name and click on the button:</p>
      <input type="input" id="name" size="40" /><br />
		
      <div id="stage" style="background-color:cc0;">
         STAGE
      </div>
		
      <input type="button" id="driver" value="Show Result" />
		
   </body>
	
</html>
``` 

这是在 **result.php** 脚本上编写的代码 ——

``` 
<?php
if( $_REQUEST["name"] )
{
   $name = $_REQUEST['name'];
   echo "Welcome ". $name;
}
?> 
``` 

现在你可以在给定的输入框中键入任何文本，然后点击"显示结果"按钮来看看你在输入框中键入的内容。

![](images\ajax-jt-3.png)

## JQuery AJAX 方法

你已经用 JQuery 了解了基本的 AJAX 概念。下表是所有的 JQuery AJAX 方法，你可以根据你的编程序要选择你需要的方法 ——

<table class="table table-bordered">
<tr>
<th>序号</th>
<th>方法 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>jQuery.ajax( options )</b>
<p>使用一个 HTTP 请求加载一个远程页面。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>jQuery.ajaxSetup( options )</b>
<p>为 AJAX 请求设置全局设置。</p></td>
</tr>
<tr>
<td>3</td>
<td><b>jQuery.get( url, [data], [callback], [type] )</b>
<p>使用一个 HTTP GET 请求加载一个远程页面。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>jQuery.getJSON( url, [data], [callback] )</b>
<p>使用一个 HTTP GET 请求加载 JSON 数据。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>jQuery.getScript( url, [callback] )</b>
<p>使用一个 HTTP GET 请求加载并执行一个 JavaScript 文件。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>jQuery.post( url, [data], [callback], [type] )</b>
<p>使用一个 HTTP POST 请求加载一个远程页面。</p></td>
</tr>
<tr>
<td>7</td>
<td><b>load( url, [data], [callback] )</b>
<p>从远程文件加载 HTML 并把它注入到 DOM 中。</p></td>
</tr>
<tr>
<td>8</td>
<td><b>serialize( )</b>
<p>将一组输入元素序列化一个字符串数据中。</p></td>
</tr>
<tr>
<td>9</td>
<td><b>serializeArray( )</b>
<p>像 .serialize() 方法一样，序列化所有的表单及表单元素，但是返回 JSON 数据结构。</p></td></tr>
</table>

## JQuery AJAX 事件

你可以在 AJAX 调用进程的生命周期中，调用不同的 JQuery 方法。下述方法是基于不同的事件/状态的 ——

你可以浏览全部的 [**AJAX 事件**](http://www.tutorialspoint.com/jquery/ajax-events.htm)。

<table class="table table-bordered">
<tr>
<th>序号</th>
<th>方法 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>ajaxComplete( callback )</b>
<p>当一个 AJAX 请求完成后，附加一个要被执行的函数。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>ajaxStart( callback )</b>
<p>当一个 AJAX 开始并且没有准备好的操作时，附加一个要被执行的函数。</p></td>
</tr>
<tr>
<td>3</td>
<td><b>ajaxError( callback )</b>
<p>当一个 AJAX 请求失败后，附加一个要被执行的函数。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>ajaxSend( callback )</b>
<p>在一个 AJAX 请求发送之前，附加一个要被执行的函数。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>ajaxStop( callback )</b>
<p>当全部的 AJAX 请求结束后，附加一个要被执行的函数。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>ajaxSuccess( callback )</b>
<p>当一个 AJAX 请求成功完成后，附加一个要被执行的函数。</p></td>
</tr>
</table>



