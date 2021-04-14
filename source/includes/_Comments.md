# Comments

## 新增评论

```http
Post /api/v4/comments HTTP/1.1
Authorization: your_authorization

{
    "comment": {
        "body": "2345678765434567"
    },
    "user_id": 690,
    "cms_page_id": 341
}
```

```http
HTTP/1.1 200 OK

{
    "id": 265,
    "author_id": 690,
    "commentable_id": 341,
    "commentable_type": "Cms::Page",
    "body": "2345678765434567",
    "status": "pending",
    "handled_user_id": null,
    "replied_comment_id": null,
    "created_at": "2020-07-07T16:49:03.868+08:00",
    "author": {
        "id": 690,
        "name": "郑薛林",
        "nickname": "贤独丨🤺",
        "phone": "15883535414",
        "identifier": "15883535414",
        "qq": null,
        "headimgurl": "http://thirdwx.qlogo.cn/mmopen/vi_32/KU6FI52PPicLT6iaZ88S49btibcTic2OcnSg4gObibYyxc92giafHRwjpNgaPZKRiaRGt47sdoulxO3fqzdn69EjmyTwQ",
        "openid": "oXDm5s0XDReFEqbMcAddC_CQGrNY",
        "imported_alias": "郑薛林",
        "from_wechat": false,
        "tags": [],
        "profile_submission": {
            "entries": []
        }
    }
}
```

`Post /api/v4/comments`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| body | string | 评论详情 |  |
| user_id | integer | 评论用户 ID |  |
| cms_page_id | integer | 文章 ID |  |

## 查询评论

```http
Post /api/v4/comments HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 200 OK

[
    {
        "id": 261,
        "author_id": 690,
        "commentable_id": 341,
        "commentable_type": "Cms::Page",
        "body": "2345678765434567",
        "status": "approved",
        "handled_user_id": 690,
        "replied_comment_id": null,
        "created_at": "2020-07-07T16:45:41.098+08:00",
        "author": {
            "id": 690,
            "name": "郑薛林",
            "nickname": "贤独丨🤺",
            "phone": "15883535414",
            "identifier": "15883535414",
            "qq": null,
            "headimgurl": "http://thirdwx.qlogo.cn/mmopen/vi_32/KU6FI52PPicLT6iaZ88S49btibcTic2OcnSg4gObibYyxc92giafHRwjpNgaPZKRiaRGt47sdoulxO3fqzdn69EjmyTwQ",
            "openid": "oXDm5s0XDReFEqbMcAddC_CQGrNY",
            "imported_alias": "郑薛林",
            "from_wechat": false,
            "tags": [],
            "profile_submission": {
                "entries": []
            }
        }
    }
]
```

`Get /api/v4/comments`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |

## 查询评论

```http
Delete /api/v4/comments/:id HTTP/1.1
Authorization: your_authorization

```

```http
HTTP/1.1 204 OK
```

`Destroy /api/v4/comments/:id`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 评论 id | |
