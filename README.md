## 1 应用缓存

HTML5中我们可以轻松的构建一个离线（无网络状态）应用，只需要创建一个cache manifest文件。

### 1.1 优势

1、可配置需要缓存的资源

2、网络无连接应用仍可用

3、本地读取缓存资源，提升访问速度，增强用户体验

4、减少请求，缓解服务器负担

### 1.2 缓存清单

一个普通文本文件，其中列出了浏览器应缓存以供离线访问的资源，推荐使用.appcache为后缀名

例如我们创建了一个名为demo.appcache的文件，然后在需要应用缓存在页面的根元素(html)添加属性manifest="demo.appcache"，路径要保证正确。

### 1.3 manifest文件格式*

1、顶行写CACHE MANIFEST

2、CACHE: 换行 指定我们需要缓存的静态资源，如.css、image、js等

3、NETWORK: 换行 指定需要在线访问的资源，可使用通配符

4、FALLBACK: 换行 当被缓存的文件找不到时的备用资源



### 1.4 其它

1、CACHE: 可以省略，这种情况下将需要缓存的资源写在CACHE MANIFEST

2、可以指定多个CACHE: NETWORK: FALLBACK:，无顺序限制

3、#表示注释，只有当demo.appcache文件内容发生改变时或者手动清除缓存后，才会重新缓存。

4、chrome 可以通过chrome://appcache-internals/工具和离线（offline）模式来调试管理应用缓存
