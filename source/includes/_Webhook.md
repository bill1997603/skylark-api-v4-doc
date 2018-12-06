# Webhook

在`post` payload_url时，会带上相关Http Header

<ul>
  <li>X-Slp-Event 事件名称</li>
  <li>Content-Type application/json</li>
</ul>

## AssignmentEvent

```
### Webhook payload example
{
  "action":"proposed",
  "assignment":{
    "id":"742",
    "created_at":"2018-07-06 09:50:39 +0800",
    "updated_at":"2018-07-06 09:50:39 +0800",
    "vertex_id":"137",
    "status":"processing",
    "operation_data":{
      "comment":"这是一条处理意见，啦啦",
      "operation":"approve",
      "esignature":"data:image/png;base64,something",
      "next_vertex_id":138,
      "next_reviewer_ids":[],
      "duration_thresholds":[],
      "carbon_copy_user_ids":[]
    },
    "response":{
      "id":"548810",
      "created_at":"2018-07-06 09:49:34 +0800",
      "updated_at":"2018-07-06 09:50:58 +0800",
      "cached_values":{
        "38827":{
          "value":[
            "测试"
          ],
          "text_value":[
            "测试"
          ],
          "exported_value":[
            "测试"
          ]
        },
        "38828":{
          "value":[
            {
              "id":"31969",
              "gid":"gid://skylark/Option/31969",
              "value":"新选项2"
            }
          ],
          "text_value":[
            "新选项2"
          ],
          "exported_value":[
            "新选项2"
          ]
        }
      }
    },
    "journey":{
      "id":"226",
      "created_at":"2018-07-06 09:50:39 +0800",
      "updated_at":"2018-07-06 09:50:39 +0800",
      "sn":"1620180706094934000042",
      "status":"processing",
      "current_vertex_id":"139",
      "reviewer_vertex_ids":[
        "137"
      ]
    },
    "user":{
      "id":"17013",
      "created_at":"1924-12-19 22:52:39 +0800",
      "updated_at":"2018-06-27 10:15:03 +0800",
      "name":"aaaa",
      "identifier":"12345",
      "headimgurl":"/non-digested-assets/avatars/default.png"
    }
  },
  "flow":{
    "id":"16",
    "created_at":"2018-05-14 15:28:10 +0800",
    "updated_at":"2018-07-06 09:50:19 +0800",
    "title":"简单-2层级"
  }
}

```

Key | Type | Description
------- | ------- | -------
action | string
assignemnt | object
assignemnt[response] | object | 填写的数据
assignment[journey] | object | 用户发起的一条流程
assignment[user]	 | user | 发起人 or 处理人
flow | object

action 可能值

<ul>
  <li>proposed 发起</li>
  <li>approved 通过</li>
  <li>refused 回退</li>
  <li>transferred 转交</li>
  <li>cancelled 发起人撤销</li>
  <li>suspended 异常</li>
  <li>finished 流程完成</li>
  <li>aborted 管理员终止</li>
</ul>

## ResponseEvent

### 提交、修改、删除表单数据

```
### Webhook payload example
{
  "action":"created",
  "form":{
    "id":"4001",
    "created_at":"2018-06-28 15:07:49 +0800",
    "updated_at":"2018-06-28 15:07:49 +0800",
    "title":"测试webhook"
  },
  "response":{
    "id":"548814",
    "created_at":"2018-07-06 10:05:33 +0800",
    "updated_at":"2018-07-06 10:05:33 +0800",
    "cached_values":{
      "38821":{
        "value":[
          "测试1"
        ],
        "text_value":[
          "测试1"
        ],
        "exported_value":[
          "测试1"
        ]
      },
      "38822":{
        "value":[
          "测试2"
        ],
        "text_value":[
          "测试2"
        ],
        "exported_value":[
          "测试2"
        ]
      },
      "38823":{
        "value":[
          {
            "value":"测试输入其他的内容"
          }
        ],
        "text_value":[
          "测试输入其他的内容"
        ],
        "exported_value":[
          "测试输入其他的内容"
        ]
      }
    },
    "user":{
      "id":"17013",
      "created_at":"1924-12-19 22:52:39 +0800",
      "updated_at":"2018-06-27 10:15:03 +0800",
      "name":"aaaa",
      "identifier":"12345",
      "headimgurl":"/non-digested-assets/avatars/default.png"
    }
  }
}

```

Key | Type | Description
------- | ------- | -------
action | string
assignemnt | object | 表单信息
response | object | 填写数据
response[user] | object | 填写人

action 可能值

<ul>
  <li>created 创建</li>
  <li>updated 更新</li>
  <li>destroyed 删除</li>
</ul>

## MemberEvent

### 加入、退出组织

```
### Webhook payload example
{
  "action": "created",
  "user_organization":{
    "id":"185566",
    "created_at":"2018-07-16 10:12:10 +0800",
    "updated_at":"2018-07-16 10:12:10 +0800",
    "user":{
      "id":"127058",
      "created_at":"2018-07-03 21:39:38 +0800",
      "updated_at":"2018-07-03 21:39:38 +0800",
      "name":"awe",
      "identifier":"asdxx",
      "headimgurl":"/non-digested-assets/avatars/default.png"
    },
    "organization":{
      "id":"11643",
      "created_at":"2016-04-28 19:36:15 +0800",
      "updated_at":"2017-12-06 17:52:25 +0800",
      "name":"自己",
      "ancestry":null,
      "children_count":"1"
    }
  }
}

```

Key | Type | Description
------- | ------- | -------
action | string
user_organization | object | 
user_organization[user]	 | object | 成员
user_organization[organization] | object | 组织

action 可能值

<ul>
  <li>created 创建</li>
  <li>destroyed 删除</li>
</ul>
