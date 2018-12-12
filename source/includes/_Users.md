# Users

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

