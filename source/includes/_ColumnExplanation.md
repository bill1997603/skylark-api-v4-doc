# Column Explanation

## 数据库表解释

- Flow: 管理员创建的流程
  - Field: 发起人所需要填写的字段
  - Vertex & Edge: 节点和边，可以构建出流程的策略图
  
- Journey: 用户发起的流程
  - Assignment: 处理者收到的任务
    - Response: 处理者填写的数据
  - Moment: 一条流程所有的事件，发起、通过、拒绝、转交...

## 字段解释

| Flow Column | Meaning |
| --- | --- |
| title | 流程名称 |

| Field Column | Meaning |
| --- | --- |
| title | 字段名称 |
| description | 字段描述 |

| Vertex Column | Meaning |
| --- | --- |
| title | 节点名称 |
| type | 节点描述 |

| Edge Column | Meaning |
| --- | --- |
| from_vertex_id | 入节点id |
| to_vertex_id | 出节点id |

| Journey Column | Meaning |
| --- | --- |
| sn | 流程编号 |
| status | 状态 |
| current_vertex_id | 当前节点id |
| reviewer_vertex_ids | 已完成的节点ids |

| Journey Column | Meaning |
| --- | --- |
| vertex_id | 节点id |
| status | 状态 |
| categroy | `proposed`: 为发起人创建的; `processed`: 为每个处理人创建的; `cc`: 为抄送者创建的 |
| operation_data | 处理的相关数据 |
| operation_data[comment] | 处理意见 |
| operation_data[esignature] | 电子签名，base64编码的图片 |
| operation_data[next_vertex_id] | 下一节点id |
| operation_data[next_reviewer_ids]	 | 指定下一节点处理人id |
| operation_data[duration_thresholds]	 | 下一节点处理时间限制 |
| operation_data[carbon_copy_user_ids] | 抄送给其他用户id |

| Moment Column | Meaning |
| --- | --- |
| status | 意义参考journey status |
| comment | 处理意见 |
| esignature | 电子签名，base64编码的图片 |
| vertex_id | 处理节点id |
| user | 发起人或处理人 |

| User Column | Meaning |
| --- | --- |
| name | 姓名 |
| identifier | 识别码 |
| headimgurl | 头像 |

| Response Column | Meaning |
| --- | --- |
| cached_values	 | `json`数据 |

## 流程状态解释

  - 当流程发起时(Journey Create)，会为发起人创建一个proposed Assignment
  - 当流程到达处理人节点是，会为每一个处理人创建一个processed Assignment
  - proposed Assignment和Journey的状态是同步变化的，eg: Journey为finished, proposed Assignment也为finished
  - processed Assignment状态对Journey影响
    - 当所有节点都通过(approved)时，流程(Journey)变成finished
    - 处理人拒绝(refused)到开始节点，流程(Journey)变成receding

| 处理人(processed) Assignment Status | Meaning |
| --- | --- |
| processing | 任务正在处理中 |
| approved | 通过 |
| refused | 拒绝, 可能拒绝到开始节点；可能拒绝到上一节点 |
| transferred	| 转交 |
| skipped	| 被其他人处理 |

| 发起人(proposed) Assignment Status | Meaning |
| --- | --- |
| processing | 流程正在处理中 |
| cancelled | 发起人撤销流程 |
| receding | 被处理人回退到开始节点 |
| finished	| 所有节点通过，流程完成 |
| aborted	| 管理员手动终止流程 |
| suspended	| 流程异常，eg: 找不到下一节点；下一节点没有处理人... |

## Response cached_values 说明

- 展示建议使用text_value
- 附件的下载地址有权限限制，如果想获取附件真正的下载地址，通过附件[接口](https://github.com/GreenNerd/SLP-ChangeLog/wiki/%E9%99%84%E4%BB%B6api-v4)

```
一般字段
{
  `field_id`: {
    {
      value: [...],
      text_value: [...],
      exported_value: [...]
    }
  }
}
```

```
明细`(Field::Detail)`字段
{
  `detail_id`: {
    group_ids: [...],
    child_ids: [...]
  }
}
```

```
明细内的字段
{
  `child_id`: {
    grouped_ids: [...],
    grouped_values: [
      `group_id`: {
        group_id: `group_id`,
        value: [...],
        text_value: [...],
        exported_value: [...]
      }
    ]
  }
}
```
