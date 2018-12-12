---
title: API Reference

language_tabs:
  - http

toc_footers:


includes:
  - Pagination
  - WechatClient
  - Pushes
  - Flows
  - Users
  - Organizations
  - Forms
  - Attachments
  - ColumnExplanation
  - errors

search: true
---

# Introduction

Welcome to the Skylark API!

域名：
  
  - 测试：https://beta.skylarkly.com
  - 正式：https://skylarkly.com

**注**：
  
  - 所有的开发对接工作在Beta https://beta.skylarkly.com 上完成，部署时会给线上环境的配置

# Authentication

1、创建一个ApiApplication，获得`appid`和`appsecret`（由我们提供）

2、获得Namespace的id（由我们提供）

3、构建Authorization header

`header`值的形式：`appid`:`encoded_data`

`appid`：为第一步获取到的`appid`

`encoded_data`：以`appsecret`为key，用JWT的HS256进行加密，加密payload为`{"namespace_id":id}`（id为Integer）

示例：

`appid: 56dc47367f8c775cf2318aa29345af558ad8aa2835bc3cc1d4416abfa94bd721`

`appsecret: 7bb73122837c4befb9c6593287f73a5e915415fe29f5aeb182717b66e873e96b`

`namespace_id: 1`

JWT的

HEADER为：`{"typ":"JWT","alg":"HS256"}`
PAYLOAD为：`{"namespace_id":1}`

计算出`encoded_data`为：

`eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJuYW1lc3BhY2VfaWQiOjF9.z-RcFpDiYBXAO8i88M_x1JpJRr6CDMo8sb1rU6dw-0E`

最终构建出`Authorization` header的值为： 

`56dc47367f8c775cf2318aa29345af558ad8aa2835bc3cc1d4416abfa94bd721:eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJuYW1lc3BhY2VfaWQiOjF9.z-RcFpDiYBXAO8i88M_x1JpJRr6CDMo8sb1rU6dw-0E`

可以用jwt.io进行测试

实际使用中，处于安全的考虑，最好在payload中加入过期时间，如：

  `{"namespace_id":1,"exp":1535553256}`
