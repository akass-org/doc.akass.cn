# 晓白云图床使用教程

## 图片压缩

晓白云图床Pro套餐支持图片压缩。

### WebP 压缩

在图片链接后加上 `!wp{level}` 即可。

例如，这是一张约10M的测试图片：
```
https://i-cdn.akass.cn/2022/05/6275d9a35a6e6.png
``` 

WebP压缩后仅剩260多KB。

```
https://i-cdn.akass.cn/2022/05/6275d9a35a6e6.png!wp60
```

#### 所有WebP压缩等级

- `wp60` : 60% 质量
- `wp80` : 80% 质量
- `wp90` : 90% 质量
- `wp` : 100% 质量

### AVIF 压缩

在图片链接后加上 `!avif` 即可。

例如，这是一张约10M的测试图片：
```
https://i-cdn.akass.cn/2022/05/6275d9a35a6e6.png
``` 

AVIF压缩后仅剩210多KB。

```
https://i-cdn.akass.cn/2022/05/6275d9a35a6e6.png!avif
```


## 对接ShareX

如图。

![ShareX1](https://i-cdn.akass.cn/2022/05/6284f19b57faf.png!wp)

![ShareX2](https://i-cdn.akass.cn/2022/05/6284f1b295cf3.png!wp)

需要指定上传的存储策略的话在 `URL参数` 中添加
| 名称 | 值 |
| --- | --- |
| strategy_id | 1（对应的存储策略D） |


### 剪切板/文件导入

- 未指定存储策略
    ```json
    {
    "Version": "13.7.0",
    "Name": "Lsky Pro v2",
    "DestinationType": "ImageUploader",
    "RequestMethod": "POST",
    "RequestURL": "https://lsky.pro/api/v1/upload",
    "Headers": {
        "Authorization": "Bearer Your_token"
    },
    "Body": "MultipartFormData",
    "FileFormName": "file",
    "URL": "$json:data.links.url$"
    }
    ```
- 指定存储策略
    ```json
    {
        "Version": "13.7.0",
        "Name": "Lsky Pro v2",
        "DestinationType": "ImageUploader",
        "RequestMethod": "POST",
        "RequestURL": "https://lsky.pro/api/v1/upload",
        "Parameters": {
        "strategy_id": "2（对应的存储策略id）"
        },
        "Headers": {
        "Authorization": "Bearer Your_Token"
        },
        "Body": "MultipartFormData",
        "FileFormName": "file",
        "URL": "$json:data.links.url$"
    }
    ```

## 对接PicGO

### 方法一： `自定义Web图床` 插件

按如下方式填写即可：

- API地址：https://your.domain/api/v1/upload
- POST 参数名：file
- JSON路径：data.links.url
- 自定义请求头：{"Authorization": "Bearer your_token"}
- 其他选填

### 方法二：`lankong` 插件

按如下方式填写：

- 打开 `Lsky Pro Version`
- Server： 填写你的图床地址即可，不需要 `/api/v1/upload` ，**不要以 `/` 结尾**
- Auth Token： `Bearer Your_token`
- Sync Delete： 打开即可通过PicGo删除图片
- 其他选填


## 获取Token

### CURL

- 简洁一点：

    ```
    curl -X POST -F "email=your_email@address" -F "password=your_passwd" https://your.domain/api/v1/tokens
    ```
- 展开：
    ```
    curl --location --request POST 'https://your.domain/api/v1/tokens' \
    --form 'email="your_email@address"' \
    --form 'password="your_passwd"'
    ```

### Shell wget
```
wget --no-check-certificate --quiet \
  --method POST \
  --timeout=0 \
  --header '' \
  --body-data 'email=your email address&password=password' \
   'https://pic.iqy.ink/api/v1/tokens'
```

### Postman/ApiPost/ApiFox

![postman](https://i-cdn.akass.cn/2022/05/6284f24f9fd78.png!wp)

![apipost](https://i-cdn.akass.cn/2022/05/6284f2843a854.png!wp)

都差不多。