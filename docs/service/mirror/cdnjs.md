# CDNJS文件镜像

## 同步源

为解决git clone文件利用率低导致的存储成本增加，遂决定使用反代加缓存的形式进行镜像。

现在的同步方式是反代+本地缓存，未缓存的新文件第一次访问时耗时较久，还请耐心等待。[详细信息](../img/info.png)

如果有更好的同步方式还请您不吝赐教。

## 使用方式

使用加速域名 `sf.akass.cn` 替换 `cdnjs.cloudflare.com/ajax/libs` 即可。

例如：

```
https://cdnjs.cloudflare.com/ajax/libs/vue/3.2.33/vue.cjs.min.js
```
替换为
```
https://sf.akass.cn/vue/3.2.33/vue.cjs.min.js
```

## 缓存

CDN缓存时间 **365天**。有强制缓存。

本地缓存时间：永久

加速地域：中国大陆地区。