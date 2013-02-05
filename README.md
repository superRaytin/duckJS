duckJS
======

# duckJS是什么 #
一款JavaScript模块加载器。

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
