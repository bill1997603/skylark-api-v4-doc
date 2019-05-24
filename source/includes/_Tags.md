# Tags

## 查询空间下标签类型

```http
GET /api/v4/tags HTTP/1.1
Authorization: your_authorization
{
  "type": "user"
}
or
{
  "type": "receipt"
}
```

```http
HTTP/1.1 200 OK
[
  {
    "id": 1,
    "name": "歌手",
    "full_name": "歌手"
  },
  {
    "id": 1,
    "name": "演员",
    "full_name": "演员"
  }
]
```

`GET /api/v4/tags`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| type | string | 标签类型 |

## 查询成员标签下的成员

```http
GET /api/v4/tags/1/taggable_users HTTP/1.1
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
[
  {
    "id": 1,
    "name": "第一个管理员",
    "nickname": "",
    "phone": "1111111111",
    "identifier": "1111111111",
    "qq": "123",
    "headimgurl": "/non-digested-assets/avatars/default.png",
    "openid": "123",
    "imported_alias": "第一个管理员",
    "from_wechat": false,
    "tags": [{
      "id": 1,
      "name": "b1",
      "full_name": "bq-b1",
      "color": "#e91e63",
      "tag_group_id": 1,
      "taggings_count": 9
    }, {
      "id": 3,
      "name": "a1",
      "full_name": "a1",
      "color": "#ff5722",
      "tag_group_id": 1,
      "taggings_count": 4
    }, {
      "id": 8,
      "name": "a2",
      "full_name": "a2",
      "color": "#673ab7",
      "tag_group_id": 1,
      "taggings_count": 1
    }
	},
  {
    "id": 1,
    "name": "第二个管理员",
    "nickname": "",
    "phone": "12222222222",
    "identifier": "12222222222",
    "qq": "123",
    "headimgurl": "/non-digested-assets/avatars/default.png",
    "openid": "123",
    "imported_alias": "第一个管理员",
    "from_wechat": false,
    "tags": [{
      "id": 1,
      "name": "b1",
      "full_name": "bq-b1",
      "color": "#e91e63",
      "tag_group_id": 1,
      "taggings_count": 9
    }, {
      "id": 3,
      "name": "a1",
      "full_name": "a1",
      "color": "#ff5722",
      "tag_group_id": 1,
      "taggings_count": 4
    }, {
      "id": 8,
      "name": "a2",
      "full_name": "a2",
      "color": "#673ab7",
      "tag_group_id": 1,
      "taggings_count": 1
    }
  }
]
```

`GET /api/v4/tags/:id/taggable_users`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 标签id |
