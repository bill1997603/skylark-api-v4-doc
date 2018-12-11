# Wechat Client

注：

  - access_token和jsapi_ticket都是在过期时间之前，可以一直使用，请求得到后而缓存之
  - 不要用access_token去微信端请求jsapi_ticket，jsapi_ticket通过我们提供的接口获取

## access_token

```http
GET /api/v4/wechat_clients/access_token HTTP/1.1

```

```http
HTTP/1.1 200 OK
{
  "access_token": "15_2FkbrFbJuemSy3ANqLmHNu65bpflFlORFTO8tqnvw5a1C0EhF-nfGAvmRhjHqX9-bc8yWqk_2ezUfINwwGLvisa5kgrLQzOKP1rN6SxTixiDklu1fA3UK0GsO_a5nmrkfo_B44xcvtpEj78sVMKcAIAEVT",
  "expired_at": "1541041188" // 过期的 unix 时间戳
}
```

`GET /api/v4/wechat_clients/access_token`

**Parameters**

*   None

[微信文档](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1421140183)

## jsapi_ticket

```http
GET /api/v4/wechat_clients/jsapi_ticket HTTP/1.1

```

```http
HTTP/1.1 200 OK
{
  "ticket": "sM4AOVdWfPE4DxkXGEs8VAT3lleStXwJQ-0K5TVdAa6VYKz9sECvxATXHT4fR5Vcqy8B4XnR3_fiV-xuSIWfjQ",
  "expired_at": "1535715059" // 过期的 unix 时间戳
}
```

`GET /api/v4/wechat_clients/jsapi_ticket`

**Parameters**

*   None

