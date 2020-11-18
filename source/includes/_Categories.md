# Categories

## 获取当前空间下所有的分类

```http
GET /api/v4/categories HTTP/1.1
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
[
    {
        "id": 4,
        "name": "庆山社区",
        "depth": 1,
        "description": "",
        "icon": "fa-folder-open",
        "position": 2,
        "hidden": false,
        "external_link": null,
        "sort_type": "manual",
        "cms_variables": "",
        "ancestry": "1"
    },
    {
        "id": 114,
        "name": "办事指南",
        "depth": 5,
        "description": "",
        "icon": "fa-folder-open",
        "position": 1590572033,
        "hidden": false,
        "external_link": "http://wsq.cdyoue.com/namespaces/1/categories/111/pages/23",
        "sort_type": "manual",
        "cms_variables": "",
        "ancestry": "1/38/39/80/111"
    },
    {
        "id": 110,
        "name": "热线咨询",
        "depth": 5,
        "description": "",
        "icon": "fa-folder-open",
        "position": 1590571945,
        "hidden": false,
        "external_link": "12321",
        "sort_type": "manual",
        "cms_variables": "",
        "ancestry": "1/38/39/80/107"
    }
]
```

`GET /api/v4/categories`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |

## 获取某一个分类

```http
GET /api/v4/categories/:id HTTP/1.1
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
{
    "id": 4,
    "name": "庆山社区",
    "depth": 1,
    "description": "",
    "icon": "fa-folder-open",
    "position": 2,
    "hidden": false,
    "external_link": null,
    "sort_type": "manual",
    "cms_variables": "",
    "ancestry": "1"
}
```

`GET /api/v4/categories`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 分类 id | |

## 获取某一个分类下的分类

```http
GET /api/v4/categories/:id/children HTTP/1.1
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
{
    [
        {
            "id": 258,
            "name": "进行中",
            "depth": 3,
            "description": "",
            "icon": "fa-folder-open",
            "position": 1591236841,
            "hidden": false,
            "external_link": null,
            "sort_type": "manual",
            "cms_variables": "",
            "ancestry": "1/2/7",
            "created_at": "2020-06-04T10:14:01.858+08:00"
        },
        {
            "id": 259,
            "name": "已结束",
            "depth": 3,
            "description": "",
            "icon": "fa-folder-open",
            "position": 1591236849,
            "hidden": false,
            "external_link": null,
            "sort_type": "manual",
            "cms_variables": "",
            "ancestry": "1/2/7",
            "created_at": "2020-06-04T10:14:09.211+08:00"
        }
    ]
}
```

`GET /api/v4/categories/:id/children`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 分类 id |

## 获取某一个分类下的文章

```http
GET /api/v4/categories/:id/pages HTTP/1.1
Authorization: your_authorization
```

```http
HTTP/1.1 200 OK
[
    {
        "id": 38,
        "title": "123456y",
        "html_body": "<p>neirong</p>",
        "description": "3456",
        "position": 15974,
        "external_link": null,
        "cover": "http://fs.yqfw.cdyoue.com/FnFZ9AtEPQ-nZoNIxsi5QommGcBv",
        "hidden": false,
        "read_count": 2,
        "created_at": "2020-06-03T17:02:54.296+08:00"
    },
    {
        "id": 5,
        "title": "高县“群众最满意医师”“最美乡村医生”评选活动，又来啦！",
        "html_body": "<p> 活动详情 : </p><p>一、目的意义</p><p>加强行业文化建设，弘扬崇高职业精神，提振医疗卫生健康行业精气神，提升医疗卫生服务质量。以评选高县“群众最满意医师”“最美乡村医生”活动为载体，广泛宣传全县广大医务工作者恪尽职守、无私奉献、全心全意为患者服务的先进事迹，弘扬“大医精诚、救死扶伤”的卫生核心价值观，努力打造一支思想端正、业务过硬、作风扎实、爱岗敬业、无私奉献的医师队伍，为保障人民群众健康作出应有的贡献。</p><p>二、评选原则</p><p>坚持公平、公正、公开的原则，确保广泛的代表性和群众的公认度，面向临床第一线，面向工作业绩突出和医德医风高尚的优秀医务人员。</p><p>三、评选条件</p><p>（一）从事临床一线的在岗注册医师（含助师及聘用制医师)，在岗注册乡村医生。在本院（本村卫生室）工作满五年，医师定期考核和年度考核合格以上等次。</p><p>（二）具有道德行为的先进性，自觉践行社会主义荣辱观，遵守公民基本道德规范，社会形象好、群众认可度高，是医师（乡村医生）队伍的先进典型代表。</p><p>（三）爱岗敬业，乐于奉献，坚持以病人为中心，主动、热情为病人提供优质、满意、安全的诊疗服务，深受同事、病人及家属的充分肯定和高度认可，具有感人的先进事迹，无任何不良医疗纠纷。</p><p>（四）刻苦钻研业务认真履行岗位职责，医学理论知识扎实，临床业务技能熟练，经验丰富，无四、五级病历，三基理论等相关考试无不及格现象，致力于发展医疗卫生健康事业，为医疗卫生健康事业发展作出突出贡献。</p><p>（五）被推荐人选的工作、学习、生活等方面的经历或行为，代表时代发展方向、社会价值观取向，具有示范性和导向性，体现中国传统美德和良好社会风尚。</p><p>（六）无违法违纪行为，无收受和索要红包、回扣记录。</p><p>（七）服务态度好，具有良好的医患沟通技巧和团队协作精神，无被病人或家属投诉的记录。</p><p>四、评选范围及奖项设置</p><p>评选范围：各医疗卫生单位(含民营医疗机构)在岗注册的医师（含助师及聘用制医师)，在岗注册乡村医生。</p><p>奖项设置：“群众最满意医师”奖10名，提名奖5名；“最美乡村医生”5名，提名奖3名。</p><p>五、评选程序和步骤</p><p>（一)评选方法</p><p>采取综合评价法。按100分制计算，公众投票占总成绩的50%，综合评定占总成绩的50%。</p>",
        "description": "",
        "position": 150993,
        "external_link": null,
        "cover": "http://fs.yqfw.cdyoue.com/FnWzAvi2yclIi_cvyAV9PSbOe_Tx",
        "hidden": false,
        "read_count": 22,
        "created_at": "2020-05-26T16:16:33.915+08:00"
    }
]
```

`GET /api/v4/categories/:id/pages`

**Parameters**

| Name | Type | Description | Comments |
| --- | --- | --- | ---- |
| id | integer | 分类 id |

