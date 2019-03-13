# Forms

## 表单信息

```http
GET /api/v4/forms/3987 HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
{
  "id":3987,
  "title":"这是一个表单",
  "description":"<p>哈哈</p>",
  "created_at":"2018-02-08T15:32:02.921+08:00",
  "updated_at":"2018-05-21T22:07:51.748+08:00",
  "status":"published",
  "fields":[
    {
      "id":38664,
      "title":"文本",
      "description":"",
      "type":"Field::TextField",
      "position":0,
      "validations":[
        "presence"
      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38665,
      "title":"段落",
      "description":"",
      "type":"Field::TextArea",
      "position":1,
      "validations":[
        "presence"
      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38663,
      "title":"未命名标题",
      "description":"",
      "type":"Field::TextField",
      "position":2,
      "validations":[

      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38666,
      "title":"章节",
      "description":"<p>章节细节</p>",
      "type":"Field::SectionBreak",
      "position":3,
      "validations":[

      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38667,
      "title":"整数",
      "description":"",
      "type":"Field::Integer",
      "position":4,
      "validations":[

      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38668,
      "title":"日期时间",
      "description":"",
      "type":"Field::DateTime",
      "position":5,
      "validations":[

      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "input_type":"datetime-local",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38669,
      "title":"单选",
      "description":"",
      "type":"Field::RadioButton",
      "position":6,
      "validations":[

      ],
      "other_option":"其他",
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"list",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null,
      "options":[
        {
          "id":31826,
          "value":"4",
          "settings":{
            "limit_settings":{

            }
          },
          "position":0
        }
      ]
    },
    {
      "id":38670,
      "title":"多选",
      "description":"",
      "type":"Field::CheckBox",
      "position":7,
      "validations":[
        "presence"
      ],
      "other_option":"其他",
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"list",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null,
      "options":[
        {
          "id":31827,
          "value":"4",
          "settings":{
            "limit_settings":{

            }
          },
          "position":1518075122
        }
      ]
    },
    {
      "id":38671,
      "title":"文件上传",
      "description":"",
      "type":"Field::File",
      "position":8,
      "validations":[

      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38672,
      "title":"级联选择",
      "description":"",
      "type":"Field::CascadedSelect",
      "position":9,
      "validations":[
        "presence"
      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38673,
      "title":"组织",
      "description":"",
      "type":"Field::Organization",
      "position":10,
      "validations":[
        "presence"
      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38674,
      "title":"评分",
      "description":"",
      "type":"Field::Rating",
      "position":11,
      "validations":[
        "presence"
      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38675,
      "title":"地理位置",
      "description":"",
      "type":"Field::Location",
      "position":12,
      "validations":[

      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null
    },
    {
      "id":38676,
      "title":"明细",
      "description":"呵呵",
      "type":"Field::Detail",
      "position":13,
      "validations":[

      ],
      "other_option":null,
      "visibility":"public_visibility",
      "marked":false,
      "settings":{
        "layout":"block",
        "button_name":"添加菜单",
        "other_option_settings":{
          "limit":{

          }
        },
        "length_limit":{

        }
      },
      "detail_id":null,
      "children":[
        {
          "id":38677,
          "title":"文本",
          "description":"",
          "type":"Field::TextField",
          "position":0,
          "validations":[
            "presence"
          ],
          "other_option":null,
          "visibility":"public_visibility",
          "marked":false,
          "settings":{
            "layout":"block",
            "other_option_settings":{
              "limit":{

              }
            },
            "length_limit":{

            }
          },
          "detail_id":38676
        },
        {
          "id":38678,
          "title":"评分",
          "description":"",
          "type":"Field::Rating",
          "position":1,
          "validations":[

          ],
          "other_option":null,
          "visibility":"public_visibility",
          "marked":false,
          "settings":{
            "layout":"block",
            "other_option_settings":{
              "limit":{

              }
            },
            "length_limit":{

            }
          },
          "detail_id":38676
        }
      ]
    }
  ]
}

```

`GET /api/v4/forms/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 表单id |


## 表单数据

```http
GET /api/v4/forms/548795/responses HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
X-SLP-Current-Page: 1
X-SLP-Total-Pages: 3
X-SLP-Total-Count: 100
[
    {
        "id": 174,
        "created_at": "2019-02-25T22:00:00.364+08:00",
        "cached_values": {
            "61": {
                "value": [
                    "dasdassaddsa"
                ],
                "text_value": [
                    "dasdassaddsa"
                ],
                "exported_value": [
                    "dasdassaddsa"
                ]
            }
        },
        "user": {
            "id": 1,
            "name": "第一个管理员",
            "nickname": "",
            "sex": null,
            "phone": null,
            "identifier": "759251fe10d79e6c823b",
            "openid": null,
            "created_at": "2018-11-02T15:00:17.714+08:00",
            "updated_at": "2018-11-07T10:22:43.440+08:00",
            "headimgurl": "/non-digested-assets/avatars/default_96.png",
            "tags": [
                {
                    "id": 1,
                    "name": "b1"
                }
            ]
        },
        "entries": [
            {
                "id": 117,
                "field_id": 61,
                "option_id": null,
                "value": "dasdassaddsa",
                "choice_id": null,
                "value_id": null,
                "latitude": null,
                "longitude": null,
                "group_id": null,
                "detail_id": null
            }
        ]
    },
    {
        "id": 173,
        "created_at": "2019-02-25T21:59:54.509+08:00",
        "cached_values": {
            "61": {
                "value": [
                    "231213321"
                ],
                "text_value": [
                    "231213321"
                ],
                "exported_value": [
                    "231213321"
                ]
            }
        },
        "user": {
            "id": 1,
            "name": "第一个管理员",
            "nickname": "",
            "sex": null,
            "phone": null,
            "identifier": "759251fe10d79e6c823b",
            "openid": null,
            "created_at": "2018-11-02T15:00:17.714+08:00",
            "updated_at": "2018-11-07T10:22:43.440+08:00",
            "headimgurl": "/non-digested-assets/avatars/default_96.png",
            "tags": [
                {
                    "id": 1,
                    "name": "b1"
                }
            ]
        },
        "entries": [
            {
                "id": 116,
                "field_id": 61,
                "option_id": null,
                "value": "231213321",
                "choice_id": null,
                "value_id": null,
                "latitude": null,
                "longitude": null,
                "group_id": null,
                "detail_id": null
            }
        ]
    }
]

```

`GET /api/v4/forms/:id/responses`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 表单id |
