# Flows

## 创建组织流程

```http
GET /api/v4/yaw/flows/8 HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
{
  "id":8,
  "title":"简单流程",
  "fields":[
    {
      "id":38761,
      "title":"别填",
      "description":null
    },
    {
      "id":38806,
      "title":"明细清单",
      "description":null
    }
  ],
  "vertices":[
    {
      "id":78,
      "name":"开始节点",
      "type":"YetAnotherWorkflow::Vertex::Initial"
    },
    {
      "id":80,
      "name":"流程节点3",
      "type":"YetAnotherWorkflow::Vertex::Normal"
    },
    {
      "id":79,
      "name":"结束节点",
      "type":"YetAnotherWorkflow::Vertex::Final"
    },
    {
      "id":90,
      "name":"流程节点2",
      "type":"YetAnotherWorkflow::Vertex::Normal"
    },
    {
      "id":91,
      "name":"流程节点1",
      "type":"YetAnotherWorkflow::Vertex::Normal"
    },
    {
      "id":113,
      "name":"开始节点",
      "type":"YetAnotherWorkflow::Vertex::Initial"
    },
    {
      "id":114,
      "name":"结束节点",
      "type":"YetAnotherWorkflow::Vertex::Final"
    }
  ],
  "edges":[
    {
      "id":101,
      "from_vertex_id":78,
      "to_vertex_id":91
    },
    {
      "id":92,
      "from_vertex_id":80,
      "to_vertex_id":79
    },
    {
      "id":103,
      "from_vertex_id":90,
      "to_vertex_id":80
    },
    {
      "id":102,
      "from_vertex_id":91,
      "to_vertex_id":90
    }
  ]
}

```

`GET /api/v4/yaw/flows/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 流程id |

## 获取发起的流程列表

```http
GET /api/v4/yaw/flows/110/journeys HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
X-SLP-Current-Page: 1
X-SLP-Total-Pages: 29
X-SLP-Total-Count: 2
[
  {
    "id":110,
    "sn":"820180503184630000029",
    "status":"processing",
    "current_duration_threshold":null,
    "created_at":"2018-06-06T15:39:10.532+08:00",
    "updated_at":"2018-06-06T15:39:10.532+08:00",
    "current_vertex_id":91,
    "reviewer_vertex_ids":[
      78
    ],
    "response":{
      "id":548288,
      "cached_values":{
        "38761":{
          "value":[
            "123123123"
          ],
          "text_value":[
            "123123123"
          ],
          "exported_value":[
            "123123123"
          ]
        }
      }
    },
    "user":{
      "id":17013,
      "name":"aaaa",
      "identifier":"12345",
      "headimgurl":"/non-digested-assets/avatars/default.png"
    }
  },
  ...
]
```
`GET /api/v4/yaw/flows/:id/journeys`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 流程id |

## 获取某条流程的所有Moment

```http
GET /api/v4/yaw/journeys/392/moments
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
[
  {
    "id": 392,
    "status": "proposed",
    "comment": null,
    "esignature": "data:image/png;base64,something",
    "created_at": "2018-06-29T15:09:31.835+08:00",
    "updated_at": "2018-06-29T15:09:31.835+08:00",
    "vertex_id": 168,
    "user": {
      "id": 127057,
      "name": "cacao",
      "identifier": null,
      "headimgurl": "/non-digested-assets/avatars/default.png"
    }
  },
  {
    "id": 393,
    "status": "approved",
    "comment": "",
    "esignature": "data:image/png;base64,something",
    "created_at": "2018-06-29T15:09:46.297+08:00",
    "updated_at": "2018-06-29T15:09:46.297+08:00",
    "vertex_id": 170,
    "user": {
      "id": 127057,
      "name": "cacao",
      "identifier": null,
      "headimgurl": "/non-digested-assets/avatars/default.png"
    }
  }
]
```

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 流程id |
