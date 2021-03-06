# NPM文件镜像

## 同步源

现在的同步方式是反代+本地缓存，未缓存的新文件第一次访问时耗时较久，还请耐心等待。[详细信息](../img/info.png)

如果有更好的同步方式还请您不吝赐教。

## 使用方式

使用加速域名 `npm.akass.cn` 替换 `unpkg.com` 或 `cdn.jsdelivr.net/npm` 即可。

例如：
```
https://unpkg.com/react@16.7.0/umd/react.production.min.js
# 或 https://cdn.jsdelivr.net/npm/react@16.7.0/umd/react.production.min.js
```
换为
```
https://npm.akass.cn/react@16.7.0/umd/react.production.min.js
```

## 缓存

CDN缓存时间 **365天**。有强制缓存。

本地缓存时间：永久

加速地域：中国大陆地区。

## 注意

为避免缓存版本错乱，我们没有也不会去缓存指向版本不明的链接。由于实现方式是反代，所以你的确可以通过这样的方式获取到文件。但是一旦文件被缓存到本地，就再也不会更改了，所以为了避免缓存错误，请勿直接使用这样的方式获取文件。

所以还请访问特定版本文件。

另：jsdelivr的一些功能我们还未能实现，如自动压缩min.js/css文件等，所以可能有部分文件源自jsdelivr的加载显示404。