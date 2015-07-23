# jQuery - 事件处理

使用事件我们可以创建动态 web 页面。事件是行为，可以通过 Web 应用程序检测到。


以下是事件的示例 ——

- 鼠标点击

- 一个 web 页面加载

- 用鼠标取代元素

- 提交 HTML 表单

- 键盘上的按键

- 等等

当这些事件被触发时，你可以使用自定义函数实现你想要用事件实现的任何事情。这些自定义函数称为事件处理程序。

## 创建事件处理程序

使用 jQuery 事件模型，我们可以在 DOM 中用下述 **bind()** 方法实现事件处理程序 ——

``` 
<html>
   <head>
      <title>The jQuery Example</title>
      <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
		
      <script type="text/javascript" language="javascript">
         $(document).ready(function() {
            $('div').bind('click', function( event ){
               alert('Hi there!');
            });
         });
      </script>
		
      <style>
         .div{ margin:10px;padding:12px; border:2px solid #666; width:60px;}
      </style>
		
   </head>
	
   <body>
	
      <p>Click on any square below to see the result:</p>
		
      <div class="div" style="background-color:blue;">ONE</div>
      <div class="div" style="background-color:green;">TWO</div>
      <div class="div" style="background-color:red;">THREE</div>
		
   </body>
	
</html>
```

这段代码会导致 division 元素响应点击事件；当用户点击这个 division 内部之后，警报将被显示出来。

这将产生如下所示结果：

![](images\event-jt-1.png)

bind() 指令的全部语法如下所示 ——

``` 
selector.bind( eventType[, eventData], handler)
```

下面是各个参数的描述 ——

- **eventType ——** 一个字符串，包含一个 JavaScript 事件类型，例如点击或提交。请参考下一节事件类型的完整列表。

- **eventData ——** 这是一个可选参数，是数字的映射，会被传递到事件处理程序中。

- **handler ——** 一个函数，每次事件被触发时，该函数会被执行。

## 删除事件处理程序

通常来说，一旦建立了一个事件处理程序，它仍在影响其余部分的页面。有时你可能会需要删除事件处理程序。

jQuery 提供了 **unbind()** 命令来删除一个已存在的事件处理程序。unbind() 的语法如下：

``` 
selector.unbind(eventType, handler)

or 

selector.unbind(eventType)
```

下面是各个参数的描述 ——

- **eventType ——** 一个字符串，包含一个 JavaScript 事件类型，如点击或提交。请参考下一节事件类型的完整列表。

- **handler ——** 如果提供的话，确定要被删除的特定的监听器。

## 事件类型

下述是跨平台的，建议你使用 jQuery 来绑定事件类型 ——

<table class="table table-bordered">
<tr>
<th>序号</th> 
<th>事件类型 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>blur</b>
<p>当元素失去关注时会出现。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>change</b>
<p>当元素发生改变时出现。</p></td>
</tr>
<tr>
<td>3</td>
<td><b>click</b>
<p>当鼠标点击时出现。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>dblclick</b>
<p>当鼠标双击时出现。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>error</b>
<p>当有错误在下载或卸载等时出现。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>focus</b>
<p>当元素获取关注时出现。</p></td>
</tr>
<tr>
<td>7</td>
<td><b>keydown</b>
<p>当按下键盘时出现。</p></td>
</tr>
<tr>
<td>8</td>
<td><b>keypress</b>
<p>当键盘被按下并被释放时出现。</p></td>
</tr>
<tr>
<td>9</td>
<td><b>keyup</b>
<p>当键盘被释放时出现。</p></td>
</tr>
<tr>
<td>10</td>
<td><b>load</b>
<p>当文档被下载后出现。</p></td>
</tr>
<tr>
<td>11</td>
<td><b>mousedown</b>
<p>按下鼠标按钮后出现。</p></td>
</tr>
<tr>
<td>12</td>
<td><b>mouseenter</b>
<p>当鼠标进入元素区域时出现。</p></td>
</tr>
<tr>
<td>13</td>
<td><b>mouseleave</b>
<p>当鼠标离开元素区域时出现。</p></td>
</tr>
<tr>
<td>14</td>
<td><b>mousemove</b>
<p>当鼠标指针移动时出现。</p></td>
</tr>
<tr>
<td>15</td>
<td><b>mouseout</b>
<p>当鼠标指针移动一个元素时出现。</p></td>
</tr>
<tr>
<td>16</td>
<td><b>mouseover</b>
<p>当鼠标指针移开一个元素时出现。</p></td>
</tr>
<tr>
<td>17</td>
<td><b>mouseup</b>
<p>释放鼠标按钮时出现。</p></td>
</tr>
<tr>
<td>18</td>
<td><b>resize</b>
<p>调整窗口大小时出现。</p></td>
</tr>
<tr>
<td>19</td>
<td><b>scroll</b>
<p>滚动窗口时出现。</p></td>
</tr>
<tr>
<td>20</td>
<td><b>select</b>
<p>选中文本时出现。</p></td>
</tr>
<tr>
<td>21</td>
<td><b>submit</b>
<p>提交表单时出现。</p></td>
</tr>
<tr>
<td>22</td>
<td><b>unload</b>
<p>卸载文档时出现。</p></td>
</tr>
</table>

## 事件对象

回调函数接受一个参数，当调用处理程序时，JavaScript 事件对象将通过它进行传递。

事件对象通常是不必要的并且参数也会被省略，因为足够的上下文通常是可用的，当处理程序被触发时，处理程序一定会知道需要做什么，但是还有一些你需要访问的属性。

## 事件属性

下述是可用的事件属性，并且可以以与平台无关的方法来安全的访问 ——

<table class="table table-bordered">
<tr>
<th>序号</th>
<th>属性 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>altKey</b>
<p>当事件触发时，如果 Alt 键被按下去，该属性设置为 true，如果没有则设置为 false。Alt 键在大多数 Mac 键盘上是标签选项。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>ctrlKey</b>
<p>当事件触发时，如果 Ctrl 键被按下去，该属性设置为 true，如果没有则设置为 false。</p></td>
</tr>
<tr>
<td>3</td>
<td><b>data</b>
<p>当处理程序建好后，任何值都会作为第二个参数传递给 bind() 命令。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>keyCode</b>
<p>对于 keyup 和 keydown 事件，该属性会返回键被按下去了。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>metaKey</b>
<p>当事件触发时，如果 Meta 键被按下去，该属性设置为 true。在 PC 上，Meta 是 Ctrl 键，而在 Macs 上，它是 Command 键。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>pageX</b>
<p>对于鼠标事件，指定了原始页面的相关事件的水平坐标。</p></td>
</tr>
<tr>
<td>7</td>
<td><b>pageY</b>
<p>对于鼠标事件，指定了原始页面的相关事件的竖直坐标。</p></td>
</tr>
<tr>
<td>8</td>
<td><b>relatedTarget</b>
<p>对于一些鼠标事件，当事件触发时，识别了光标离开或进入的元素。</p></td>
</tr>
<tr>
<td>9</td>
<td><b>screenX</b>
<p>对于鼠标事件，指定了原始屏幕的相关事件的水平坐标。</p></td>
</tr>
<tr>
<td>10</td>
<td><b>screenY</b>
<p>对于鼠标事件，指定了原始屏幕的相关事件的竖直坐标。</p></td>
</tr>
<tr>
<td>11</td>
<td><b>shiftKey</b>
<p>当事件触发时，如果 Shift 键被按下，该属性设置为 true，如果没有则设置为 false。</p></td>
</tr>
<tr>
<td>12</td>
<td><b>target</b>
<p>识别要触发的事件的元素。</p></td>
</tr>
<tr>
<td>13</td>
<td><b>timeStamp</b>
<p>创建事件时的时间戳(以毫秒为单位)。</p></td>
</tr>
<tr>
<td>14</td>
<td><b>type</b>
<p>对于所有的事件来说，指定了要触发的事件类型(例如，点击)。</p></td>
</tr>
<tr>
<td>15</td>
<td><b>which</b>
<p>对于键盘事件来说，指定了引发事件的键的数字代码，对于鼠标事件来说，指定了哪一个按钮被按下(1 是左键，2 是中间键，3 是右键)。</p></td>
</tr>
</table>

``` 
<html>
   <head>
      <title>The jQuery Example</title>
      <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
		
      <script type="text/javascript" language="javascript">
         $(document).ready(function() {
            $('div').bind('click', function( event ){
               alert('Event type is ' + event.type);
               alert('pageX : ' + event.pageX);
               alert('pageY : ' + event.pageY);
               alert('Target : ' + event.target.innerHTML);
            });
         });
      </script>
		
      <style>
         .div{ margin:10px;padding:12px; border:2px solid #666; width:60px;}
      </style>
		
   </head>
	
   <body>
	
      <p>Click on any square below to see the result:</p>
		
      <div class="div" style="background-color:blue;">ONE</div>
      <div class="div" style="background-color:green;">TWO</div>
      <div class="div" style="background-color:red;">THREE</div>
		
   </body>
	
</html>
```

这将产生如下所示结果：

![](images\event-jt-2.png)

## 事件方法

下述是方法列表，可以在事件对象中调用 ——

<table class="table table-bordered">
<tr>
<th>序号</th>
<th>方法 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>preventDefault()</b>
<p>阻止浏览器执行默认操作。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>isDefaultPrevented()</b>
<p>返回 event.preventDefault() 是否曾经在该事件对象中调用过。</p></td>
</tr>
<tr>
<td>3</td>
<td><b>stopPropagation()</b>
<p>停止向父元素 bubbing 事件，阻止通知任何父处理程序这一事件。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>isPropagationStopped()</b>
<p>返回 event.stopPropagation() 是否曾经在该事件对象中调用过。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>stopImmediatePropagation()</b>
<p>阻止其余的处理程序执行。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>isImmediatePropagationStopped()</b>
<p>返回 event.stopImmediatePropagation() 是否曾经在该事件对象中调用过。</p></td>
</tr>
</table>

## 事件处理方法

下表列出了重要的事件相关的方法 ——

<table class="table table-bordered">
<tr>
<th>序号</th>
<th>方法 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>bind( type, [data], fn )</b>
<p>为每个匹配的元素将一个处理程序捆绑到一个或多个事件上(如点击)。也可以捆绑自定义事件。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>off( events [, selector ] [, handler(eventObject) ]  )</b>
<p>该方法实现的是 live 的对立面，它删除了捆绑的 live 事件。</p></td>
</tr>
<tr>
<td>3</td>
<td><b>hover( over, out )</b>
<p>模拟徘徊，例如将鼠标移动到一个对象上，并将鼠标从该对象上移开。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>on( events [, selector ] [, data ], handler  )</b>
<p>为所有当前的 &minus; 以及之后的 &minus; 匹配元素将一个处理程序捆绑到一个事件上(如点击)。 也可以捆绑自定义事件。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>one( type, [data], fn )</b>
<p>为每个匹配的元素将一个处理程序绑定到一个或多个要被执行的事件上。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>ready( fn )</b>
<p>当 DOM 准备好要被遍历或者操作时，绑定一个要被执行的函数。</p></td>
</tr>
<tr>
<td>7</td>
<td><b>trigger( event, [data] )</b>
<p>在每个匹配的元素上触发一个事件。</p></td>
</tr>
<tr>
<td>8</td>
<td><b>triggerHandler( event, [data] )</b>
<p>在一个元素上触发全部绑定的事件处理程序。</p></td>
</tr>
<tr>
<td>9</td>
<td><b>unbind( [type], [fn] )</b>
<p>该方法实现绑定相反的操作，它从每个匹配的元素中删除绑定的事件。</p></td>
</tr>
</table>

## 事件辅助方法

jQuery 也提供了一组事件辅助函数，这些函数可以用于触发一个事件或绑定上述任何类型的事件。

## 触发方法

下面的例子中将触发所有段落中的 blur 事件 ——

``` 
$("p").blur();
```

## 绑定方法

下面的例子将一个 **click** 事件绑定到所有的 < div> 中 ——

``` 
$("div").click( function () { 
   // do something here
});
```

这是 jQuery 提供的所有支持方法完整的列表 ——

<table class="table table-bordered">
<tr>
<th>序号</th>
<th>方法 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>blur( )</b>
<p>触发每个匹配元素的 blur 事件。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>blur( fn )</b>
<p>将一个函数绑定到每个匹配元素的 blur 事件中。</p></td>
</tr>
<tr>
<td>3</td>
<td><b>change( )</b>
<p>触发每个匹配元素的 change 事件。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>change( fn )</b>
<p>将一个函数绑定到每个匹配元素的 change 事件中。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>click( )</b>
<p>触发每个匹配元素的 click 事件。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>click( fn )</b>
<p>将一个函数绑定到每个匹配元素的 click 事件中。</p></td>
</tr>
<tr>
<td>7</td>
<td><b>dblclick( )</b>
<p>触发每个匹配元素的 dblclick 事件。</p></td>
</tr>
<tr>
<td>8</td>
<td><b>dblclick( fn )</b>
<p>将一个函数绑定到每个匹配元素的 dblclick 事件中。</p></td>
</tr>
<tr>
<td>9</td>
<td><b>error( )</b>
<p>触发每个匹配元素的 error 事件。</p></td>
</tr>
<tr>
<td>10</td>
<td><b>error( fn )</b>
<p>将一个函数绑定到每个匹配元素的 error 事件中。</p></td>
</tr>
<tr>
<td>11</td>
<td><b>focus( )</b>
<p>触发每个匹配元素的 focus 事件。</p></td>
</tr>
<tr>
<td>12</td>
<td><b>focus( fn )</b>
<p>将一个函数绑定到每个匹配元素的 focus 事件中。</p></td>
</tr>
<tr>
<td>13</td>
<td><b>keydown( )</b>
<p>触发每个匹配元素的 keydown 事件。</p></td>
</tr>
<tr>
<td>14</td>
<td><b>keydown( fn )</b>
<p>将一个函数绑定到每个匹配元素的 keydown 事件中。</p></td>
</tr>
<tr>
<td>15</td>
<td><b>keypress( )</b>
<p>触发每个匹配元素的 keypress 事件。</p></td>
</tr>
<tr>
<td>16</td>
<td><b>keypress( fn )</b>
<p>将一个函数绑定到每个匹配元素的 keypress 事件中。</p></td>
</tr>
<tr>
<td>17</td>
<td><b>keyup( )</b>
<p>触发每个匹配元素的 keyup 事件。</p></td>
</tr>
<tr>
<td>18</td>
<td><b>keyup( fn )</b>
<p>将一个函数绑定到每个匹配元素的 keyup 事件中。</p></td>
</tr>
<tr>
<td>20</td>
<td><b>load( fn )</b>
<p>将一个函数绑定到每个匹配元素的 load 事件中。</p></td>
</tr>
<tr>
<td>21</td>
<td><b>mousedown( fn )</b>
<p>将一个函数绑定到每个匹配元素的 mousedown 事件中。</p></td>
</tr>
<tr>
<td>22</td>
<td><b>mouseenter( fn )</b>
<p>将一个函数绑定到每个匹配元素的 mouseenter 事件中。</p></td>
</tr>
<tr>
<td>23</td>
<td><b>mouseleave( fn )</b>
<p>将一个函数绑定到每个匹配元素的 mouseleave 事件中。</p></td>
</tr>
<tr>
<td>24</td>
<td><b>mousemove( fn )</b>
<p>将一个函数绑定到每个匹配元素的 mousemove 事件中。</p></td>
</tr>
<tr>
<td>25</td>
<td><b>mouseout( fn )</b>
<p>将一个函数绑定到每个匹配元素的 mouseout 事件中。</p></td>
</tr>
<tr>
<td>26</td>
<td><b>mouseover( fn )</b>
<p>将一个函数绑定到每个匹配元素的 mouseover 事件中。</p></td>
</tr>
<tr>
<td>27</td>
<td><b>mouseup( fn )</b>
<p>将一个函数绑定到每个匹配元素的 mouseup 事件中</p></td>
</tr>
<tr>
<td>28</td>
<td><b>resize( fn )</b>
<p>将一个函数绑定到每个匹配元素的 resize 事件中。</p></td>
</tr>
<tr>
<td>29</td>
<td><b>scroll( fn )</b>
<p>将一个函数绑定到每个匹配元素的 scroll 事件中。</p></td>
</tr>
<tr>
<td>30</td>
<td><b>select( )</b>
<p>触发每个匹配元素的 select 事件。</p></td>
</tr>
<tr>
<td>31</td>
<td><b>select( fn )</b>
<p>将一个函数绑定到每个匹配元素的 select 事件中。</p></td>
</tr>
<tr>
<td>32</td>
<td><b>submit( )</b>
<p>触发每个匹配元素的 submit 事件。</p></td>
</tr>
<tr>
<td>33</td>
<td><b>submit( fn )</b>
<p>将一个函数绑定到每个匹配元素的 submit 事件中。</p></td>
</tr>
<tr>
<td>34</td>
<td><b>unload( fn )</b>
<p>将一个函数绑定到每个匹配元素的 unload 事件中。</p></td>
</tr>
</table>

