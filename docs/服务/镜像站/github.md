# GitHub文件镜像

## 同步源

我们采用白名单的方式同步 `raw.githubusercontent.com` 下的内容，仅有白名单内的 GitHub Repositories 才能得到 `AKASS` 的加速。

现在的同步方式是反代+本地缓存，未缓存的新文件第一次访问时耗时较久，还请耐心等待。[详细信息](../img/info.png)

如果您有更好的同步方式，希望您能不吝赐教。

## 白名单

- 白名单1及其超链接
- 白名单2及其超链接
- 白名单3及其超链接

## 使用方式

使用加速域名 `gh.akass.cn` 替换 `raw.githubusercontent.com` 即可。

路径结构如下：
```
https://gh.akass.cn/{username}/{reponame}/{tag}/{path}
```

例如：
```
https://gh.akass.cn/lsky-org/lsky-pro/2.0/public/favicon.ico
```

## 缓存

CDN缓存时间 **90天** 。有强制缓存。

本地缓存时间：90天

加速地域：中国大陆地区。

## 注意

为避免缓存版本错乱，我们没有也不会去缓存 `master`/`main` 等分支。由于实现方式是反代，所以你的确可以通过这样的方式获取到文件。但是一旦文件被缓存到本地，就再也不会更改了，所以为了避免缓存错误，请勿直接使用这样的方式获取文件。

所以还请使用 `{tag}` 来访问特定版本文件。