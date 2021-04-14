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

## 查询单条数据

```http
GET /api/v4/responses/:id HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK
{
    "id": 1385,
    "created_at": "2020-08-04T11:23:00.571+08:00",
    "cached_values": {
        "2": {
            "value": [
                "15884559372"
            ],
            "text_value": [
                "15884559372"
            ],
            "exported_value": [
                "15884559372"
            ]
        },
        "4": {
            "value": [
                "杨女士"
            ],
            "text_value": [
                "杨女士"
            ],
            "exported_value": [
                "杨女士"
            ]
        }
    },
    "mapped_values": {
        "payment_method": {
            "value": [
                {
                    "id": 126,
                    "gid": "gid://skylark/Option/126",
                    "value": "按揭"
                }
            ],
            "text_value": [
                "按揭"
            ],
            "exported_value": [
                "按揭"
            ]
        },
        "saler_phone": {
            "value": [
                "12334566543"
            ],
            "text_value": [
                "12334566543"
            ],
            "exported_value": [
                "12334566543"
            ]
        },
        "customer_gender": {
            "value": [
                {
                    "id": 4,
                    "gid": "gid://skylark/Option/4",
                    "value": "女"
                }
            ],
            "text_value": [
                "女"
            ],
            "exported_value": [
                "女"
            ]
        },
        "customer_phone": {
            "value": [
                "12121212112"
            ],
            "text_value": [
                "12121212112"
            ],
            "exported_value": [
                "12121212112"
            ]
        },
        "customer_name": {
            "value": [
                "杨女士"
            ],
            "text_value": [
                "杨女士"
            ],
            "exported_value": [
                "杨女士"
            ]
        },
        "motivation": {
            "value": [
                {
                    "id": 13,
                    "gid": "gid://skylark/Option/13",
                    "value": "家庭自住"
                }
            ],
            "text_value": [
                "家庭自住"
            ],
            "exported_value": [
                "家庭自住"
            ]
        },
        "saler": {
            "value": [
                "张朦檬"
            ],
            "text_value": [
                "张朦檬"
            ],
            "exported_value": [
                "张朦檬"
            ]
        },
        "intention": {
            "value": [
                {
                    "id": 62,
                    "gid": "gid://skylark/Option/62",
                    "value": "D无意向"
                }
            ],
            "text_value": [
                "D无意向"
            ],
            "exported_value": [
                "D无意向"
            ]
        },
        "living_area2": {
            "value": [
                {
                    "id": 547,
                    "gid": "gid://skylark/Option/547",
                    "value": "平乐"
                }
            ],
            "text_value": [
                "平乐"
            ],
            "exported_value": [
                "平乐"
            ]
        },
        "entitlement": {
            "value": [
                {
                    "id": 128,
                    "gid": "gid://skylark/Option/128",
                    "value": "有"
                }
            ],
            "text_value": [
                "有"
            ],
            "exported_value": [
                "有"
            ]
        },
        "remark": {
            "value": [
                "一个人到访，说的是给娃娃看房，娃娃在成都工作，然后在外面看了下环境就想走，进来给她讲户型也不是很感兴趣，然后就要慌到走。"
            ],
            "text_value": [
                "一个人到访，说的是给娃娃看房，娃娃在成都工作，然后在外面看了下环境就想走，进来给她讲户型也不是很感兴趣，然后就要慌到走。"
            ],
            "exported_value": [
                "一个人到访，说的是给娃娃看房，娃娃在成都工作，然后在外面看了下环境就想走，进来给她讲户型也不是很感兴趣，然后就要慌到走。"
            ]
        },
        "source": {
            "value": [
                {
                    "id": 484,
                    "gid": "gid://skylark/Option/484",
                    "value": "到访客户"
                }
            ],
            "text_value": [
                "到访客户"
            ],
            "exported_value": [
                "到访客户"
            ]
        },
        "customer_resistance": {
            "value": [
                {
                    "id": 554,
                    "gid": "gid://skylark/Option/554",
                    "value": "区域"
                },
                {
                    "id": 555,
                    "gid": "gid://skylark/Option/555",
                    "value": "地段"
                },
                {
                    "id": 556,
                    "gid": "gid://skylark/Option/556",
                    "value": "户型"
                },
                {
                    "id": 557,
                    "gid": "gid://skylark/Option/557",
                    "value": "装修"
                },
                {
                    "id": 558,
                    "gid": "gid://skylark/Option/558",
                    "value": "价格"
                }
            ],
            "text_value": [
                "区域",
                "地段",
                "户型",
                "装修",
                "价格"
            ],
            "exported_value": [
                "区域，地段，户型，装修，价格"
            ]
        },
        "preferred_apartment": {
            "value": [
                {
                    "id": 563,
                    "gid": "gid://skylark/Option/563",
                    "value": "住宅1F"
                },
                {
                    "id": 564,
                    "gid": "gid://skylark/Option/564",
                    "value": "住宅2F"
                }
            ],
            "text_value": [
                "住宅1F",
                "住宅2F"
            ],
            "exported_value": [
                "住宅1F，住宅2F"
            ]
        },
        "price_range": {
            "value": [
                {
                    "id": 543,
                    "gid": "gid://skylark/Option/543",
                    "value": "总价61-70万"
                }
            ],
            "text_value": [
                "总价61-70万"
            ],
            "exported_value": [
                "总价61-70万"
            ]
        },
        "line_card": {
            "value": [
                {
                    "id": 762,
                    "gid": "gid://skylark/Option/762",
                    "value": "否"
                }
            ],
            "text_value": [
                "否"
            ],
            "exported_value": [
                "否"
            ]
        }
    },
    "involved_user_ids": [],
    "involved_organization_ids": [],
    "entries": [
        {
            "id": 10584,
            "field_id": 423,
            "option_id": 762,
            "value": "否",
            "choice_id": null,
            "value_id": null,
            "latitude": null,
            "longitude": null,
            "group_id": null,
            "detail_id": null
        },
        {
            "id": 10583,
            "field_id": 163,
            "option_id": 484,
            "value": "到访客户",
            "choice_id": null,
            "value_id": null,
            "latitude": null,
            "longitude": null,
            "group_id": null,
            "detail_id": null
        }
    ],
    "user": {
        "id": 75,
        "name": "张朦檬",
        "nickname": "Smile",
        "sex": 2,
        "phone": "15884559372",
        "identifier": "15884559372",
        "openid": "ouvMN1qTZ_ucaufm5HFI26w_Q43A",
        "created_at": "2020-07-03T10:17:37.855+08:00",
        "updated_at": "2020-07-03T11:13:04.931+08:00",
        "headimgurl": "http://thirdwx.qlogo.cn/mmopen/vi_32/AAlQYG92O3xBbrZniaa6uv6ex5wTeUyllIKYu7zWwrqrCvoL9jCuic21P7sGR52r1WjgsCxMic5kSzwiahz5JClxbQ/96",
        "tags": [
            {
                "id": 2,
                "name": "magnate_saler"
            },
            {
                "id": 1,
                "name": "magnate_admin"
            }
        ],
        "organizations": [
            {
                "id": 8,
                "name": "销售",
                "description": "",
                "created_at": "2020-07-03T10:17:02.093+08:00"
            }
        ]
    }
}
```

`GET /api/v4/responses/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 记录 id |
