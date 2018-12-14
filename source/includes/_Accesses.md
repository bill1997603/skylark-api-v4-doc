# Accesses

## 获取当前空间下所有权限

```http
GET /api/v4/accesses HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
[
    {
        "id": 1,
        "name": "超级管理员",
        "actions": [
            1,
            3,
            4
        ],
        "founded": false
    },
    {
        "id": 7,
        "name": "测试管理员",
        "actions": [
            4
        ],
        "founded": false
    }
]

```

`GET /api/v4/accesses`
