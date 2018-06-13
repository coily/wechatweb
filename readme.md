## 视频/音频 ##
> video 常用方法

    播放：play() 事件 play
		
    暂停：pause() 事件 pause
		 
    重载：load()

	检测支持类型：canPlayType(type)
常用type

- 	video/ogg
- 	video/mp4
- 	video/webm
- 	audio/mpeg
- 	audio/ogg
- 	audio/mp4

return支持的级别。可能的值：
"probably" - 最有可能支持
"maybe" - 可能支持
"" - （空字符串）不支持


> video 常用属性

    currentTime 	设置或返回音频/视频中的当前播放位置（以秒计）
    defaultMuted	设置或返回音频/视频默认是否静音(true|false)
    playbackRate	设置或返回音频/视频的默认播放速度(1.0,2.0)
    duration	 	返回当前音频/视频的长度（以秒计）
    ended			返回音频/视频的播放是否已结束
	volume			设置或返回音频/视频的音量


## 拖放 ##

> 思考：想一下物件拖拽的步骤？

1. 让元素可拖拽
2. 拖动的时候，传输什么数据
3. 让某个元素可以放置拖拽的东西
4. 拖拽完毕时候，放置元素

>
    step1：draggable="true"
    step2：dragstart事件，
	event.dataTransfer.setData(key,value);//setData()传输数据
    step3：dragover事件 //event.preventDefault();
    step4：drop事件 




## Cookie ##
**什么是cookie?**

cookie 是存储于访问者的计算机中的变量。
每当同一台计算机通过浏览器请求某个页面时，就会发送这个 cookie。
你可以使用 JavaScript 来创建和取回 cookie 的值。

应用例子：
> 密码 cookie
> 当访问者首次访问页面时，他或她也许会填写他/她们的密码。
> 密码也可被存储于 cookie 中。当他们再次访问网站时，密码就会从 cookie 中取回。

> 日期 cookie
> 当访问者首次访问你的网站时，当前的日期可存储于 cookie 中。
> 当他们再次访问网站时，他们会收到类似这样的一条消息"上次登录时间2016-1-1 18:23:04"。
> 日期也是从 cookie 中取回的。

**创建和存储 cookie**

访问cookie

	document.cookie;
设置cookie

	document.cookie = "time=xx&name=xx";



## HTML5 Web存储 ##

**localStorage**

**sessionStorage**

cookie 不适合大量数据的存储，因为它们由每个对服务器的请求来传递，这使得 cookie 速度很慢而且效率也不高。

> 在 HTML5 中，数据不是由每个服务器请求传递的，而是只有在请求时使用数据。它使在不影响网站性能的情况下存储大量数据成为可能。
> 对于不同的网站，数据存储于不同的区域，并且一个网站只能访问其自身的数据。
> HTML5 使用 JavaScript 来存储和访问数据。
    
    localStorage - 没有时间限制的数据存储

localStorage 方法存储的数据没有时间限制。一周或者一年后，数据依然可用。

**如何创建和访问 localStorage：**

	<script type="text/javascript">
		localStorage.lastTime="2016-01-01";
		alert(localStorage.lastTime);
	</script>

sessionStorage 使用方法同localStorage，但每次关闭浏览器清除