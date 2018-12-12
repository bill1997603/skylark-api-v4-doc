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
GET /api/v4/organizations/127059/members HTTP/1.1
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
| id | integer | 组织id |
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

`POST /api/v4/organizations/`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| name | string | 名字 |
| identifier | string | 识别码 |
| phone | string | 电话号码 |
| organization_id | integer | 组织id |
