# Attachments

## 查询

```http
GET /api/v4/attachments/query?ids[]=:id&ids[]=:id HTTP/1.1
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
[
  {
    "id": 2474,
    "name": "test.png",
    "size": "81702",
    "mime_type": "image/png",
    "extension": "image",
    "extra_info": {},
    "download_url": "http://7xlxax.dl1.z0.glb.clouddn.com/17013-1531909931-49d1c668335fe2fc660e92042431d544-1531909931258?attname=%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7+2018-07-16+%E4%B8%8B%E5%8D%883.40.46.png&e=1532329592&token=WFpC8JEsN77rEZRgdoQgQw-yB82e-j3fpp8dXB8Z:JZFJ7usX7rWZ6hxZgkdkq3WWhXw="
  },
  ...
]
```

`GET /api/v4/attachments/query`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| ids | array | 附件id的集合 |
| fops | string | 七牛云图片处理的参数，[文档](https://developer.qiniu.com/search?keyword=%E5%9B%BE%E7%89%87%E5%A4%84%E7%90%86) |

## 获取附件上传的 Token

```http
GET /api/v4/attachments/uptoken?purpose=create_responses HTTP/1.1
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
{
  "uptoken": "WFpC8JEsN77rEZRgdoQgQw-yB82e-j3fpp8dXB8Z:hQdV5hQ3etWr_MVcMwe8HpHf3bo=:eyJzY29wZSI6InNscC1hdHRhY2htZW50LWJldGEiLCJzYXZlS2V5IjoiMS9jcmVhdGVfcmVzcG9uc2VzLy0xNTk0MDA1ODk0LTFhMmU2ZGVkOGZkMDdiZTM2ZjEzNDI3Yjg4Yzk2MDExLSQoeDprZXkpIiwiY2FsbGJhY2tVcmwiOiJodHRwczovL2JldGEuc2t5bGFya2x5LmNvbS9hdHRhY2htZW50cy5qc29uIiwiY2FsbGJhY2tCb2R5Ijoia2V5PSQoa2V5KVx1MDAyNm5hbWU9JChmbmFtZSlcdTAwMjZzaXplPSQoZnNpemUpXHUwMDI2bWltZV90eXBlPSQobWltZVR5cGUpIiwiZGVhZGxpbmUiOjE1OTQwMDk0OTQsImZzaXplTGltaXQiOjUyNDI4ODAwLCJ1cGhvc3RzIjpbImh0dHA6Ly91cC5xaW5pdS5jb20iLCJodHRwOi8vdXBsb2FkLnFpbml1LmNvbSIsIi1IIHVwLnFpbml1LmNvbSBodHRwOi8vMTgzLjEzMS43LjMiXSwiZ2xvYmFsIjpmYWxzZX0="
}
```

`GET /api/v4/attachments/uptoken`

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| purpose | string | 固定为 create_responses |

## 上传附件到七牛

```http
POST https://up.qbox.me/ HTTP/1.1
```

```http
HTTP/1.1 200 OK
{
  "extension": "image",
  "extra_info": {},
  "id": 3258,
  "mime_type": "image/jpeg",
  "name": "test.jpg",
  "size": "41491"
}
```

`POST https://up.qbox.me/`

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| token | string | [获取附件上传的 Token] |
| file | file | 文件 |
| x:key | integer | 暂时固定为 1593586993541 |

## 创建附件（废弃）

```http
POST /api/v4/attachments HTTP/1.1
```

```http
HTTP/1.1 200 OK
```

`POST /api/v4/attachments`

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| key | string | 获取文件的 key |
| name | string | 文件名称 |
| size | integer | 文件大小 |
| mime_type | 文件类型 | |
