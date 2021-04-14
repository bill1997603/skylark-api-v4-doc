# IdentityCertifications

## 获取人脸核身的链接

```http
GET /api/v4/identity_certifications/new HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
{
  identity_vertify_url: #{identity_vertify_url}
}
```

`GET /api/v4/identity_certifications/auth`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| redirect_url | integer | 回调地址，用于获取 BizToken |

## 用户绑定授权信息

```http
GET /api/v4/identity_certifications/auth HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 201 CREATED
{
  message: '实名信息创建成功'
}
```

`GET /api/v4/identity_certifications/auth`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| user_id | integer | 用户id |
| BizToken | integer | 从人脸核身回调地址返回 |
