# jQuery - 影响

jQuery 提供了一个非常简单的接口来做各种类型的神奇效果。jQuery 方法使我们能够用最低的配置，迅速应用常用的效果。

本教程涵盖了所有重要的创建视觉效果的 jQuery 方法。

## 显示和隐藏元素

显示和隐藏元素的命令是我们所期望的 —— **show()** 用于在包装好的集合中显示元素，而 **hide()** 用于隐藏它们。

### 语法

这是 **show()** 方法的简单语法 ——

``` 
[selector].show( speed, [callback] );
``` 

这是所有参数的描述 ——

- **speed ——** 一个字符串，代表了三个预定义速度("慢"，"正常"，"快速")之一或者是运行动画的毫秒数(如 1000)。

- **callback ——** 可选参数，代表了当动画完成后要被执行的函数；每个动画元素要执行一次。

下面是 ** hide()** 方法的简单的语法 ——

``` 
[selector].hide( speed, [callback] );
``` 

这是所有参数的描述 ——

- **speed ——** 一个字符串，代表了三个预定义速度("慢速"，"正常"，"快速")之一或者是运行动画的毫秒数(如 1000)。

- **callback ——** 可选参数，代表了当动画完成后要被执行的函数；每个动画元素执行一次。

### 示例

考虑下面这个带有一小段 JQuery 编码的 HTML 文件 ——

``` 
<html>
   <head>
      <title>The jQuery Example</title>
      <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
		
      <script type="text/javascript" language="javascript">
         $(document).ready(function() {

            $("#show").click(function () {
               $(".mydiv").show( 1000 );
            });

            $("#hide").click(function () {
               $(".mydiv").hide( 1000 );
            });
         });
      </script>
		
      <style>
         .mydiv{ margin:10px;padding:12px; border:2px solid #666; width:100px; height:100px;}
      </style>

   </head>
	
   <body>
	
      <div class="mydiv">
         This is a SQUARE
      </div>

      <input id="hide" type="button" value="Hide" />   
      <input id="show" type="button" value="Show" />   

   </body>
	
</html>
```

它将产生如下所示结果 ——

![](images\effect-jt-1.png)

## 切换元素

jQuery 提供了方法来在显示和隐藏之间切换元素的显示状态。如果元素最初是显示状态，那么它会变为隐藏；如果元素最初是隐藏状态，那么它会显示出来。

### 语法

这是 **toggle()** 方法的简单语法 ——

``` 
[selector]..toggle([speed][, callback]);
``` 

这是所有参数的描述 ——

- **speed ——** 一个字符串，代表了三个预定义速度("慢速"，"正常"，"快速")之一或者是运行动画所需的毫秒数(如 1000)。

- **callback ——** 可选参数，代表了当动画完成后要被执行的函数；每个动画元素要执行一次。

### 示例

我们可以使任何元素产生动画效果，如包含一个动画的简单的 < div> ——

``` 
<html>
   <head>
      <title>The jQuery Example</title>
      <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/2.1.3/jquery.min.js"></script>
		
      <script type="text/javascript" language="javascript">

         $(document).ready(function() {
            $(".clickme").click(function(event){
               $(".target").toggle('slow', function(){
                  $(".log").text('Transition Complete');
               });
            });
         });
      </script>
		
      <style>
         .clickme{ margin:10px;padding:12px; border:2px solid #666; width:100px; height:50px;}
      </style>
		
   </head>
	
   <body>
	
      <div class="content">
         <div class="clickme">Click Me</div>
         <div class="target">
            <img src="./images/jquery.jpg" alt="jQuery" />
         </div>
         <div class="log"></div>
      </div>			
   </body>
	
</html>
```

这将产生如下所示的结果 ——

![](images\effect-jt-2.png)

## JQuery 效果方法

你已经了解了 JQuery 效果的基本概念。下表是用于创建不同种类效果的全部重要的方法 ——

<table class="table table-bordered">
<tr>
<th>序号</th>
<th>方法 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>animate( params, [duration, easing, callback] )</b>
<p>用于制作自定义动画的函数。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>fadeIn( speed, [callback] )</b>
<p>通过调整所有匹配元素的不透明度来使它们消失，并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>3</td>
<td><b>fadeOut( speed, [callback] )</b>
<p>通过将所有匹配元素的不透明度调整为 0 使它们消失，然后设置显示为 "none"，并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>fadeTo( speed, opacity, callback )</b>
<p>将所有匹配元素的不透明度调整为一个指定的不透明度并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>hide( )</b>
<p>如果匹配元素集合时显示状态，那就隐藏它们。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>hide( speed, [callback] )</b>
<p>用优美的动画来隐藏所有匹配元素并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>7</td>
<td><b>show( )</b>
<p>如果匹配元素集合是隐藏状态，那就显示它们。</p></td>
</tr>
<tr>
<td>8</td>
<td><b>show( speed, [callback] )</b>
<p>用一个优美的动画显示所有的匹配元素并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>10</td>
<td><b>slideDown( speed, [callback] )</b>
<p>通过调整所有匹配元素的高来显示它们并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>11</td>
<td><b>slideToggle( speed, [callback] )</b>
<p>通过调整所有匹配元素的高来切换它们的可视状态并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>12</td>
<td><b>slideUp( speed, [callback] )</b>
<p>通过调整所有匹配元素的高来隐藏它们并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>13</td>
<td><b>stop( [clearQueue, gotoEnd ])</b>
<p>在指定的元素中停止当前正在运行的动画。</p></td>
</tr>
<tr>
<td>14</td>
<td><b>toggle( )</b>
<p>切换每个匹配元素集合的显示状态。</p></td>
</tr>
<tr>
<td>15</td>
<td><b>toggle( speed, [callback] )</b>
<p>使用一个优雅的动画来切换匹配元素集合的显示状态并在这一操作完成后激发一个可选的回调。</p></td>
</tr>
<tr>
<td>16</td>
<td><b>toggle( switch )</b>
<p>基于以上选项来切换匹配元素的显示状态(true 显示全部元素，false 隐藏全部元素)。</p></td>
</tr>
<tr>
<td>17</td>
<td><b>jQuery.fx.off</b>
<p>在全局范围内禁用所有动画。</p></td>
</tr>
</table>


## 基于效果的 UI 库

想要使用这些效果，你可以从 [**jQuery UI Library**](http://jqueryui.com/download) 下载最新版本的 jQuery UI 库 **jquery-ui-1.11.4.custom.zip** 或者使用 Google CDN，其方法和 jQuery 相同。

我们已经在 HTML 页面的下述代码片段中为 jQuery UI 使用了 Google CDN，所以我们可以使用 jQuery UI ——

``` 
<head>
   <script src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.11.3/jquery-ui.min.js"></script>
</head>
```

<table class="table table-bordered">
<tr>
<th>序号</th>
<th>方法 &amp; 描述</th>
</tr>
<tr>
<td>1</td>
<td><b>Blind</b>
<p>以百叶窗的效果将元素隐藏或使元素显现。</p></td>
</tr>
<tr>
<td>2</td>
<td><b>Bounce</b>
<p>使元素垂直或水平的弹跳 n 次。</p></td>
</tr>
<tr>
<td>3</td>
<td>
<b>Clip</b>
<p>剪辑元素打开或关闭，垂直或水平。</p></td>
</tr>
<tr>
<td>4</td>
<td><b>Drop</b>
<p>以下降的方式使元素隐藏或者显现出来。</p></td>
</tr>
<tr>
<td>5</td>
<td><b>Explode</b>
<p>将元素分解成多个部分。</p></td>
</tr>
<tr>
<td>6</td>
<td><b>Fold</b>
<p>将元素像一张纸一样折叠起来。</p></td>
</tr>
<tr>
<td>7</td>
<td><b>Highlight</b>
<p>用于定义的颜色将背景标亮。</p></td>
</tr>
<tr>
<td>8</td>
<td><b>Puff</b>
<p>缩放并淡出动画来创造蓬松的效果。</p></td>
</tr>
<tr>
<td>9</td>
<td><b>Pulsate </b>
<p>多次有规律的改变元素的不透明度。</p></td>
</tr>
<tr>
<td>10</td>
<td><b>Scale</b>
<p>用一个比例因子来减少或增加元素。</p></td>
</tr>
<tr>
<td>11</td>
<td><b>Shake</b>
<p>使元素 n 次垂直或水平摇晃。</p></td>
</tr>
<tr>
<td>12</td>
<td><b>Size</b>
<p>给元素重新设定一个指定的宽和高。</p></td>
</tr>
<tr>
<td>13</td>
<td><b>Slide</b>
<p>使元素滑落出视窗。</p></td>
</tr>
<tr>
<td>14</td>
<td><b>Transfer</b>
<p>将元素的轮廓转换为另一个。</p></td>
</tr>
</table>

