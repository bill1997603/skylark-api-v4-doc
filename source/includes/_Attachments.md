# Attachments

## 查询

```http
GET /api/v4/attachments/query?id[]=2474&id[]=2475 HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
[
  {
    "id": 2474,
    "name": "屏幕快照 2018-07-16 下午3.40.46.png",
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
