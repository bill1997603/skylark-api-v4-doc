# Flows

## 获取流程详情

```http
GET /api/v4/yaw/flows/:id HTTP/1.1
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

## 获取发起的流程任务列表

```http
GET /api/v4/yaw/flows/:id/journeys HTTP/1.1
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

## 获取某条流程任务的所有 Moment

```http
GET /api/v4/yaw/journeys/:id/moments HTTP/1.1
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

`GET /api/v4/yaw/journeys/:id/moments`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 流程id |

## 创建流程任务（route）

```http
POST /api/v4/yaw/flows/:id/journeys HTTP/1.1
Authorization: your_authorization

{
    "assignment": {
        "operation": "route",
        "response_attributes": {
            "entries_attributes": [
                {
                    "field_id": 7199,
                    "value": "test"
                },
                {
                    "field_id": 7200,
                    "value": "新选项",
                    "option_id": 8854
                },
                {
                    "field_id": 7201,
                    "value": "2020-11-18"
                },
                {
                    "field_id": 7202,
                    "value": "WechatIMG132.jpeg",
                    "value_id": 3839,
                    "_destroy": false
                }
            ]
        }
    }
}
```

```http
HTTP/1.1 200 OK
{
    "assignment": {
        "id": 7802,
        "status": "stashed",
        "category": "proposed",
        "read": true,
        "current_duration_threshold": null,
        "created_at": "2020-11-18T15:20:08.113+08:00",
        "updated_at": "2020-11-18T15:45:24.343+08:00",
        "after_submit_action": "default",
        "after_submit_redirect_url": null,
        "gid": "gid://skylark/YetAnotherWorkflow::Assignment/7802",
        "pretty_current_duration_threshold": null,
        "journey": {
            "id": 2236,
            "sn": "145920201118152008000001",
            "custom_sn": null,
            "status": "stashed",
            "current_duration_threshold": null,
            "created_at": "2020-11-18T15:20:08.076+08:00",
            "updated_at": "2020-11-18T15:20:08.076+08:00",
            "gid": "gid://skylark/YetAnotherWorkflow::Journey/2236",
            "pretty_current_duration_threshold": null,
            "response": {
                "id": 78149,
                "created_at": "2020-11-18T15:20:08.063+08:00",
                "entries": []
            },
            "user": {
                "id": 79,
                "name": "樊翔宇",
                "nickname": "k k",
                "phone": "18828072450",
                "identifier": "18828072450",
                "qq": null,
                "headimgurl": "https://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTKFLWWPT1sSVywib8qpNNfLjMOliblYqa105ibCOKGvzwRV0vAEAlGLcwXia8AK9FQiavG1tDxcCCkfUCA",
                "openid": "oXDm5s2v7fnJ2Mut-UiiHtCEIb6Q",
                "imported_alias": "樊翔宇",
                "gid": "gid://skylark/User/79"
            }
        },
        "response": {
            "id": 78150,
            "created_at": "2020-11-18T15:20:08.097+08:00",
            "entries": [
                {
                    "id": 1141143,
                    "field_id": 7202,
                    "option_id": null,
                    "value": "WechatIMG132.jpeg",
                    "choice_id": null,
                    "value_id": 3839,
                    "latitude": null,
                    "longitude": null,
                    "group_id": null,
                    "detail_id": null,
                    "attachment": {
                        "id": 3839,
                        "name": "WechatIMG132.jpeg",
                        "size": "16998",
                        "mime_type": "image/jpeg",
                        "extension": "image",
                        "extra_info": {}
                    }
                },
                {
                    "id": 1141142,
                    "field_id": 7201,
                    "option_id": null,
                    "value": "2020-11-18",
                    "choice_id": null,
                    "value_id": null,
                    "latitude": null,
                    "longitude": null,
                    "group_id": null,
                    "detail_id": null
                },
                {
                    "id": 1141141,
                    "field_id": 7200,
                    "option_id": 8854,
                    "value": "新选项",
                    "choice_id": null,
                    "value_id": null,
                    "latitude": null,
                    "longitude": null,
                    "group_id": null,
                    "detail_id": null
                },
                {
                    "id": 1141140,
                    "field_id": 7199,
                    "option_id": null,
                    "value": "test",
                    "choice_id": null,
                    "value_id": null,
                    "latitude": null,
                    "longitude": null,
                    "group_id": null,
                    "detail_id": null
                }
            ]
        }
    },
    "next_vertices": [
        {
            "id": 5600,
            "name": "流程节点",
            "type": "YetAnotherWorkflow::Vertex::Normal",
            "metadata": {
                "position": {
                    "x": 397,
                    "y": 251.703125
                }
            },
            "operations": {
                "route": {
                    "name": "选路",
                    "enabled": true
                },
                "refuse": {
                    "name": "回退",
                    "enabled": true
                },
                "approve": {
                    "name": "通过",
                    "enabled": true
                },
                "comment": {
                    "name": "处理意见",
                    "enabled": true
                },
                "transfer": {
                    "name": "转交",
                    "enabled": true
                },
                "esignature": {
                    "name": "电子签字",
                    "enabled": false
                }
            },
            "settings": {
                "carbon_copy": {
                    "enable_manual": false
                },
                "refuse_mode": 1,
                "assign_manually": false,
                "batch_processing": false,
                "duration_threshold": {
                    "value": null,
                    "enable_delay": false,
                    "business_time": {
                        "final": "17:00",
                        "initial": "09:00",
                        "workday": true
                    },
                    "enable_manual": false,
                    "enable_business_time": false
                },
                "distributed_equally": false
            },
            "graph_id": 1730,
            "created_at": "2020-11-18T15:20:05.493+08:00",
            "updated_at": "2020-11-18T15:20:05.568+08:00",
            "gid": "gid://skylark/YetAnotherWorkflow::Vertex::Normal/5600",
            "fields": []
        }
    ],
    "next_graphs": [
        {
            "id": 1730,
            "name": "主流程",
            "ancestry": null,
            "settings": {
                "visibility": "public",
                "duration_threshold": {
                    "value": null,
                    "enable_delay": false,
                    "business_time": {
                        "final": "17:00",
                        "initial": "09:00",
                        "workday": true
                    },
                    "enable_manual": false,
                    "enable_business_time": false
                }
            },
            "metadata": {},
            "created_at": "2020-11-18T15:03:32.377+08:00",
            "updated_at": "2020-11-18T15:03:32.487+08:00",
            "gid": "gid://skylark/YetAnotherWorkflow::Graph/1730"
        }
    ]
}
```

`POST /api/v4/yaw/flows/:id/journeys`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| operation | string | 寻路固定为 route |
| 其他参数参考表单提交填写记录 | | |

## 发起流程任务（发起）

```http
POST /api/v4/yaw/flows/:id/journeys HTTP/1.1
Authorization: your_authorization

{
    "assignment": {
        "operation": "propose",
        "next_vertex_id": 1
}
```
```http
HTTP/1.1 200 OK
{
    "id": 7802,
    "status": "processing",
    "category": "proposed",
    "read": true,
    "current_duration_threshold": null,
    "created_at": "2020-11-18T16:05:08.207+08:00",
    "updated_at": "2020-11-18T16:05:08.261+08:00",
    "after_submit_action": "default",
    "after_submit_redirect_url": null,
    "gid": "gid://skylark/YetAnotherWorkflow::Assignment/7802",
    "pretty_current_duration_threshold": null,
    "journey": {
        "id": 2236,
        "sn": "145920201118152008000001",
        "custom_sn": null,
        "status": "processing",
        "current_duration_threshold": null,
        "created_at": "2020-11-18T16:05:08.207+08:00",
        "updated_at": "2020-11-18T16:05:08.207+08:00",
        "gid": "gid://skylark/YetAnotherWorkflow::Journey/2236",
        "pretty_current_duration_threshold": null,
        "response": {
            "id": 78149,
            "created_at": "2020-11-18T15:20:08.063+08:00",
            "entries": []
        },
        "user": {
            "id": 79,
            "name": "樊翔宇",
            "nickname": "k k",
            "phone": "18828072450",
            "identifier": "18828072450",
            "qq": null,
            "headimgurl": "https://thirdwx.qlogo.cn/mmopen/vi_32/Q0j4TwGTfTKFLWWPT1sSVywib8qpNNfLjMOliblYqa105ibCOKGvzwRV0vAEAlGLcwXia8AK9FQiavG1tDxcCCkfUCA",
            "openid": "oXDm5s2v7fnJ2Mut-UiiHtCEIb6Q",
            "imported_alias": "樊翔宇",
            "gid": "gid://skylark/User/79"
        }
    },
    "response": {
        "id": 78150,
        "created_at": "2020-11-18T15:20:08.097+08:00",
        "entries": [
            {
                "id": 1141143,
                "field_id": 7202,
                "option_id": null,
                "value": "WechatIMG132.jpeg",
                "choice_id": null,
                "value_id": 3839,
                "latitude": null,
                "longitude": null,
                "group_id": null,
                "detail_id": null,
                "attachment": {
                    "id": 3839,
                    "name": "WechatIMG132.jpeg",
                    "size": "16998",
                    "mime_type": "image/jpeg",
                    "extension": "image",
                    "extra_info": {}
                }
            },
            {
                "id": 1141142,
                "field_id": 7201,
                "option_id": null,
                "value": "2020-11-18",
                "choice_id": null,
                "value_id": null,
                "latitude": null,
                "longitude": null,
                "group_id": null,
                "detail_id": null
            },
            {
                "id": 1141141,
                "field_id": 7200,
                "option_id": 8854,
                "value": "新选项",
                "choice_id": null,
                "value_id": null,
                "latitude": null,
                "longitude": null,
                "group_id": null,
                "detail_id": null
            },
            {
                "id": 1141140,
                "field_id": 7199,
                "option_id": null,
                "value": "test",
                "choice_id": null,
                "value_id": null,
                "latitude": null,
                "longitude": null,
                "group_id": null,
                "detail_id": null
            }
        ]
    }
}
```

`POST /api/v4/yaw/flows/:id/journeys`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| operation | string | 发起固定为 propose |
| next_vertex_id | integer | 需要到达的下一个流程节点，从 [发起流程任务（寻路）] 的返回结果获取 |
