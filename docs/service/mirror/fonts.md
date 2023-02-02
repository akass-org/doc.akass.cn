# 字体加速

## 文件源

字体从 Google Fonts, GitHub 等地下载，然后切割、生成对应的 CSS。由于目前人工操作占比极大，极为耗费人力资源，所以更新缓慢，按心情添加字体。

## 使用方式

引入所有字体文件
```html
<link rel="preconnect" href="https://fonts.akass.cn">
<link href="https://fonts.akass.cn/style.css" rel="stylesheet">
```

> 注意：`style.css` 文件对一个字体的多个发行版仅会引入最新版本。历史版本字体文件仅保存1年。


单独引入某一项字体文件

看 `style.css` 里面有啥呗。

## 缓存时间

目前为测试阶段，缓存30天，css文件不定期刷新。

加速地域：中国大陆地区。