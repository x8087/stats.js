stats.js
========

#### JavaScript Performance Monitor ####

This class provides a simple info box that will help you monitor your code performance.

* **FPS** 在最后一秒渲染的帧。数字越大越好。
* **MS** 渲染帧所需的毫秒数。数字越小越好。
* **MB** MBytes 已分配内存。(使用"--enable-precise-memory-info "运行 Chrome 浏览器）
* **CUSTOM** 支持用户自定义面板。


### Screenshots ###

![fps.png](https://raw.githubusercontent.com/mrdoob/stats.js/master/files/fps.png)
![ms.png](https://raw.githubusercontent.com/mrdoob/stats.js/master/files/ms.png)
![mb.png](https://raw.githubusercontent.com/mrdoob/stats.js/master/files/mb.png)
![custom.png](https://raw.githubusercontent.com/mrdoob/stats.js/master/files/custom.png)


### Installation ###
```bash
npm install stats.js
```

### Usage ###

```javascript
var stats = new Stats();
stats.showPanel( 1 ); // 0: fps, 1: ms, 2: mb, 3+: custom
document.body.appendChild( stats.dom );

function animate() {

	stats.begin();

	// monitored code goes here

	stats.end();

	requestAnimationFrame( animate );

}

requestAnimationFrame( animate );
```


### Bookmarklet ###

You can add this code to any page using the following bookmarklet:

```javascript
javascript:(function(){var script=document.createElement('script');script.onload=function(){var stats=new Stats();document.body.appendChild(stats.dom);requestAnimationFrame(function loop(){stats.update();requestAnimationFrame(loop)});};script.src='https://mrdoob.github.io/stats.js/build/stats.min.js';document.head.appendChild(script);})()
```
