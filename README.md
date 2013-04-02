duckJS
======

# duckJS是什么 #
一款JavaScript模块加载器;
在遵循AMD规范的基础上，作了一些更加方便的改进，支持定义匿名模块。
这样在调用模块的时候只需关心模块的URL，而不需要知道模块名称。

# 如何使用duckJS #
轻松两步便可使用，举个栗子~

```html
<script type="text/javascript" src="path/duck.js" />
<script type="text/javascript">
	D.config({
		alias : {
			'jquery' : 'gallery/jquery-v1.7.2.min.js',
			'style' : 'css/style.css'
		}
	});
</script>
```

# define 定义模块 #
```html
define( ['jquery'], function($){
	D.log('模块已加载');
	var fn = {
		get : function(){ return 'i am a get method'; },
		set : function( id, text ){
			document.getElementById(id).value = text;
			$('#test').html('');
		}
	};
	return fn;
});
```
define是一个全局方法，每一个参数为一个数组，表示此模块的依赖列表，也可以是一个字符串，表示只有一个依赖。
也可以忽略第一个参数，直接定义一个匿名模块。

# use 调用模块 #
```html
<script type="text/javascript">
    // 加载一个样式文件
	D.use('style');
	
	D.use(['test','jquery'],function(test,$){
        // your code...
    });
    ... more code of yours ...
</script>
```

解析模块路径将优先从用户设置的config里读取，如果模块未在config里设置，才会对test启动解析过程，比如test模块url最后会被解析为path/test.js

# 预加载 #
```html
<script type="text/javascript" src="path/duck.js" data-main="gallery/jquery-v1.7.2.min.js, path/test.js" />
```

在duckJS对应的script标签设置data-main属性，将会对其中的模块进行预加载（即随着页面初始时一起加载）。

# 支持的浏览器 #
理论上支持IE6+，及其他现代浏览器。
