# Organizations

## 所有组织

```http
GET /api/v4/organizations HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
X-SLP-Current-Page: 1
X-SLP-Total-Pages: 1
X-SLP-Total-Count: 4
[
  {
    "id": 14516,
    "name": "第一个组织",
    "description": "您可以根据需要更改名字及描述，或者删除组织",
    "description_text": "您可以根据需要更改名字及描述，或者删除组织",
    "created_at": "2017-12-25T16:06:13.111+08:00",
    "updated_at": "2018-08-14T10:00:49.663+08:00",
    "children_count": 2,
    "parent_id": null,
    "ancestry": null
  },
  {
    "id": 15113,
    "name": "组织_a",
    "description": "",
    "description_text": "",
    "created_at": "2018-08-14T10:00:29.691+08:00",
    "updated_at": "2018-08-14T10:00:40.625+08:00",
    "children_count": 1,
    "parent_id": 14516,
    "ancestry": "14516"
  },
  {
    "id": 15114,
    "name": "组织_a_a",
    "description": "",
    "description_text": "",
    "created_at": "2018-08-14T10:00:40.624+08:00",
    "updated_at": "2018-08-14T10:00:40.624+08:00",
    "children_count": 0,
    "parent_id": 15113,
    "ancestry": "14516/15113"
  },
  {
    "id": 15115,
    "name": "组织_b",
    "description": "",
    "description_text": "",
    "created_at": "2018-08-14T10:00:49.660+08:00",
    "updated_at": "2018-08-14T10:00:49.660+08:00",
    "children_count": 0,
    "parent_id": 14516,
    "ancestry": "14516"
  }
]

```

`GET /api/v4/organizations`

**Parameters**

*   None

## 顶级组织

```http
GET /api/v4/organizations/roots HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
X-SLP-Current-Page: 1
X-SLP-Total-Pages: 1
X-SLP-Total-Count: 1

[
  {
    "id": 14516,
    "name": "第一个组织",
    "description": "您可以根据需要更改名字及描述，或者删除组织",
    "description_text": "您可以根据需要更改名字及描述，或者删除组织",
    "created_at": "2017-12-25T16:06:13.111+08:00",
    "updated_at": "2018-08-14T10:00:49.663+08:00",
    "children_count": 2,
    "parent_id": null,
    "ancestry": null
  }
]

```

`GET /api/v4/organizations/roots`

**Parameters**

*   None

## 子代组织

```http
GET /api/v4/organizations/15113/children HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
X-SLP-Current-Page: 1
X-SLP-Total-Pages: 1
X-SLP-Total-Count: 2
[
  {
    "id": 15113,
    "name": "组织_a",
    "description": "",
    "description_text": "",
    "created_at": "2018-08-14T10:00:29.691+08:00",
    "updated_at": "2018-08-14T10:00:40.625+08:00",
    "children_count": 1,
    "parent_id": 14516,
    "ancestry": "14516"
  },
  {
    "id": 15115,
    "name": "组织_b",
    "description": "",
    "description_text": "",
    "created_at": "2018-08-14T10:00:49.660+08:00",
    "updated_at": "2018-08-14T10:00:49.660+08:00",
    "children_count": 0,
    "parent_id": 14516,
    "ancestry": "14516"
  }
]

```

`GET /api/v4/organizations/:id/children`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 父级组织id |

## 组织成员

```http
GET /api/v4/organizations/:organization_id/members HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
X-SLP-Current-Page: 1
X-SLP-Total-Pages: 1
X-SLP-Total-Count: 3
[
  {
    "id": 127059,
    "name": "user_a",
    "nickname": null,
    "sex": null,
    "phone": null,
    "identifier": "user_a",
    "openid": null,
    "created_at": "2018-08-14T10:10:19.434+08:00",
    "updated_at": "2018-08-14T10:10:19.434+08:00",
    "headimgurl": "/non-digested-assets/avatars/default_96.png"
  },
  {
    "id": 127060,
    "name": "user_b",
    "nickname": null,
    "sex": null,
    "phone": null,
    "identifier": "user_b",
    "openid": null,
    "created_at": "2018-08-14T10:10:24.671+08:00",
    "updated_at": "2018-08-14T10:10:24.671+08:00",
    "headimgurl": "/non-digested-assets/avatars/default_96.png"
  },
  {
    "id": 127061,
    "name": "user_c",
    "nickname": null,
    "sex": null,
    "phone": null,
    "identifier": "user_c",
    "openid": null,
    "created_at": "2018-08-14T10:10:29.831+08:00",
    "updated_at": "2018-08-14T10:10:29.831+08:00",
    "headimgurl": "/non-digested-assets/avatars/default_96.png"
  }
]

```

`GET /api/v4/organizations/:id/members`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| organization_id | integer | 组织id |
| with_descendants | string | Optional 传任意值，代表包含子孙后代组织的成员 |

## 创建组织

```http
POST /api/v4/organizations/ HTTP/1.1
Authorization: your_authorization
Content-Type: application/json
{
  "name": "name",
  "description": "description",
  "application_strategy": "must_approved",
  "founder_id": 3,
  "patent_id": 13
}

```

```http
HTTP/1.1 201 Created
Content-Type: application/json
{
  "id": 25,
  "name": "name",
  "description": "description",
  "description_text": "description",
  "created_at": "2018-12-06T10:35:35.203+08:00",
  "updated_at": "2018-12-06T10:35:35.203+08:00",
  "children_count": 0,
  "parent_id": "13",
  "ancestry": "abc",
  "application_strategy": "must_approved"
}

```

`POST /api/v4/organizations/`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| name | string | 名字 |
| description | string | 描述 |
| application_strategy | string | 审核状态 | [:must_approved, :auto_approved, :closed] |
| founder_id | integer | 创建者id |
| patent_id | integer | 父级组织id | 创建顶级组织时不需要 |

## 创建组织成员

```http
POST /api/v4/organizations/20/members HTTP/1.1
Authorization: your_authorization
Content-Type: application/json

{
  "name": "jack",
  "identifier": "jack_123",
  "phone": "10086100101"
}

```

```http
HTTP/1.1 201 Created
Content-Type: application/json
{
  "id": 20,
  "name": "jack",
  "nickname": null,
  "sex": null,
  "phone": "10086100101",
  "identifier": "jack_123",
  "openid": null,
  "created_at": "2018-12-06T10:54:34.901+08:00",
  "updated_at": "2018-12-06T10:54:34.901+08:00"
}

```

`POST /api/v4/organizations/:organization_id/members`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| name | string | 名字 |
| identifier | string | 识别码 |
| phone | string | 电话号码 |
| organization_id | integer | 组织id |

## 修改组织信息

```http
PUT /api/v4/organizations/21 HTTP/1.1
Authorization: your_authorization
Content-Type: application/json

{
  "name": "修改组织名字",
  "description": "修改组织描述",
  "application_strategy": "must_approved"
}

```

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
    "id": 21,
    "name": "修改组织名字",
    "description": "修改组织描述",
    "description_text": "修改组织描述",
    "created_at": "2018-12-05T10:19:41.202+08:00",
    "updated_at": "2018-12-13T09:29:52.080+08:00",
    "children_count": 1,
    "parent_id": null,
    "ancestry": null,
    "application_strategy": "must_approved"
}

```

`PUS /api/v4/organizations/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 组织id |
| name | string | 名字 |
| description | string | 描述 |
| application_strategy | string | 审核状态 | [:must_approved, :auto_approved, :closed] |

## 删除组织

```http
DELETE /api/v4/organizations/21 HTTP/1.1
Authorization: your_authorization
Content-Type: application/json

```

```http
HTTP/1.1 204 No Content

```

`DELETE /api/v4/organizations/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 组织id |

## 修改组织成员信息

```http
PUT /api/v4/organizations/23/members/20 HTTP/1.1
Authorization: your_authorization
Content-Type: application/json

{
  "name": "jack",
  "identifier": "jack_123",
  "phone": "10086100101"
}

```
```http
HTTP/1.1 200 OK
Content-Type: application/json
{
    "id": 20,
    "name": "jack",
    "nickname": "jack",
    "sex": null,
    "phone": "10086100101",
    "identifier": "jack_123",
    "openid": null,
    "created_at": "2018-12-06T10:54:34.901+08:00",
    "updated_at": "2018-12-13T10:08:35.305+08:00"
}

```

`PUT /api/v4/organizations/:organization_id/members/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 组织id |
| organization_id | integer | 组织id |
| name | string | 名字 |
| identifier | string | 识别码 |
| phone | string | 电话号码 |

## 增加组织人员

```http
PUT /api/v4/organizations/23/members/add HTTP/1.1
Authorization: your_authorization
Content-Type: application/json

{
  "member_ids": [19]
}

```

```http
HTTP/1.1 200 OK
Content-Type: application/json
[19]

```

`PUT /api/v4/organizations/:organization_id/members/add`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| organization_id | integer | 组织id |
| member_ids | array | 成员id |

## 移除组织成员

```http
PUT /api/v4/organizations/23/members/remove HTTP/1.1
Authorization: your_authorization
Content-Type: application/json

{
  "member_ids": [19]
}

```

```http
HTTP/1.1 200 OK
Content-Type: application/json
[19]

```

`PUT /api/v4/organizations/:organization_id/members/remove`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| organization_id | integer | 组织id |
| member_ids | array | 成员id |

## 增加组织管理员

```http
POST /api/v4/organizations/23/administrators HTTP/1.1
Authorization: your_authorization
Content-Type: application/json

{
  "user_id": 19
  "access_id": 1
}

```

```http
HTTP/1.1 201 Created
Content-Type: application/json
{
    "id": 33,
    "user": {
        "id": 19,
        "name": "123",
        "nickname": null,
        "phone": "19929029450",
        "identifier": "qwecasca",
        "qq": null,
        "headimgurl": "/non-digested-assets/avatars/default.png",
        "openid": null,
        "imported_alias": "123",
        "from_wechat": false,
        "tags": [],
        "custom_values": []
    },
    "access": {
        "id": 1,
        "name": "超级管理员",
        "actions": [
            1,
            3,
            4
        ],
        "founded": false
    },
    "organization": {
        "id": 23,
        "name": "123123",
        "description": "123123",
        "created_at": "2018-12-05T10:41:33.068+08:00"
    }
}

```

`POST /api/v4/organizations/:organization_id/administrators`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| user_id | integer | 成员id |
| access_id | integer | 权限id |

## 删除组织管理员

```http
DELETE /api/v4/organizations/23/administrators/33 HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 204 No Content

```

`DELETE /api/v4/organizations/:organization_id/administrators/:id`

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| organization_id | integer | 组织id |
| id | integer | 关联管理员id |

## 修改组织管理员权限

```http
PUT /api/v4/organizations/23/administrators/33 HTTP/1.1
Authorization: your_authorization
Content-Type: application/json

{
  "user_id": 19
  "access_id": 1
}

```

```http
HTTP/1.1 200 OK
Content-Type: application/json
{
  "id": 33,
  "user": {
    "id": 19,
    "name": "123",
    "nickname": null,
    "phone": "19929029450",
    "identifier": "qwecasca",
    "qq": null,
    "headimgurl": "/non-digested-assets/avatars/default.png",
    "openid": null,
    "imported_alias": "123",
    "from_wechat": false,
    "tags": [],
    "custom_values": []
  },
  "access": {
    "id": 1,
    "name": "超级管理员",
    "actions": [
      1,
      3,
      4
    ],
    "founded": false
  },
  "organization": {
    "id": 23,
    "name": "123123",
    "description": "123123",
    "created_at": "2018-12-05T10:41:33.068+08:00"
  }
}

```

`PUT /api/v4/organizations/:organization_id/administrators/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| user_id | integer | 成员id |
| access_id | integer | 权限id |
| organization_id | integer | 组织id |
| id | integer | 关联管理员id |

## 查询当前组织管理员

```http
GET /api/v4/organizations/:organization_id/administrators HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
Content-Type: application/json
[
  {
    "id": 18,
    "user": {
      "id": 3,
      "name": "a11",
      "nickname": null,
      "phone": "18828072450",
      "identifier": "18828072450",
      "qq": null,
      "headimgurl": "/non-digested-assets/avatars/default.png",
      "openid": null,
      "imported_alias": "a11",
      "from_wechat": false,
      "tags": [],
      "custom_values": []
    },
    "access": {
      "id": 2,
      "name": "创建者",
      "actions": [
        1,
        3,
        4
      ],
      "founded": true
    },
    "organization": {
      "id": 23,
      "name": "123123",
      "description": "123123",
      "created_at": "2018-12-05T10:41:33.068+08:00"
    }
  }
]

```

`GET /api/v4/organizations/:organization_id/administrators`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| organization_id | integer | 组织id |
