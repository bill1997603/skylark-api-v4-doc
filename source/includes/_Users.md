# Users

## 查询当前空间下所有用户
```http
GET /api/v4/users HTTP/1.1
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

`GET /api/v4/users`

## 所在组织

```http
GET /api/v4/users/14473/organizations HTTP/1.1
Authorization: your_authorization
{
  "name": "name",
  "description": "description",
  "application_strategy": "must_approved",
  "founder_id": 3,
  "patent_id": 13
}

```

```http
HTTP/1.1 200 OK
[
  {
    "id": 14473,
    "name": "child_1",
    "description": "",
    "description_text": "",
    "created_at": "2017-04-18T16:33:07.408+08:00",
    "updated_at": "2017-12-06T17:52:27.556+08:00",
    "children_count": 1,
    "parent_id": 14472,
    "ancestry": "14472"
  },
  {
    "id": 1935,
    "name": "测试组织",
    "description": "<p>aaa</p>",
    "description_text": "aaa",
    "created_at": "2015-05-25T15:58:45.083+08:00",
    "updated_at": "2018-04-06T15:37:24.712+08:00",
    "children_count": 2,
    "parent_id": null,
    "ancestry": null
  },
  ...
]
```

`GET /api/v4/users/:id/organizations`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 用户id |


## 查询用户信息

```http
GET /api/v4/users/1 HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
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
}
```

`GET /api/v4/users/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 用户id |

## 创建用户

```http
POST /api/v4/users/ HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
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
}
```

`POST /api/v4/users`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| name | String | 名字 |
| identifier | String | 识别码 |
| phone | String | 手机号 |
| openid | String | 微信的 openid |

## 更新用户

```http
PUT /api/v4/users/ HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
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
}
```

`PUT /api/v4/users`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 用户 id |
| name | String | 名字 |
| identifier | String | 识别码 |
| phone | String | 手机号 |
| openid | String | 微信的 openid |

## 更新用户标签

```http
POST /api/v4/users/:id/tags
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
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
}
```

`POST /api/v4/users/:id/tags`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 用户 id |
| add_tag_ids | integer[] | 需要添加标签的 ids |
| remove_tag_ids | integer[] | 需要删除的标签 ids |

## 更新用户标签

```http
GET /api/v4/users/:id/identity_certification
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
{
 "id": 1,
 "data": {}
}
```

`GET /api/v4/users/:id/identity_certification`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 用户 id |

## 更新用户标签

```http
GET /api/v4/users/query
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
  }
]
```

`GET /api/v4/users/query`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| keyword | string | 名字或手机号 |


