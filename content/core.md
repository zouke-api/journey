### 1. /{{book.module}}/journey/get-list

**描述**：获取订制师行程列表

**request**：

``` json
{ 
    "p": 0,   // 必填
    "ps": 50, // 必填
    "startDate": "2017-12-03",
    "endDate": "",
    "title": "",
    "stat": "all" //all|started|pending
}
```

**response**：

``` json
{
    "code": 0,
    "list": [
        { 
            "id": 10000,
            "title": "标题",
            "departure": "2017-05-03",
            "days": 5 
        }
    ],
    "total": 100
}
```

### 2. /{{book.module}}/journey/delete

**描述**：删除行程

**request**：

``` json
{
    "id": 10000
}
```

**response**：

``` json
{
    "code": 0
}
```

### 3. /{{book.module}}/journey/get-detail

**描述**：获取行程详情

**request**：

``` json
{
    "id": 10000
}
```

**response**：

``` json
{
    "code": 0,
    "detail": {
        // 行程结构
    }
}
```

### 4. /{{book.module}}/journey/create

**描述**：创建行程

**request**：

``` json
{
    //行程结构
}
```

**response**：

``` json
{
    "code": 0,
    "id": 10000
}
```

### 5. /{{book.module}}/journey/update

**描述**：更新行程

**request**：

``` json
{
    "id": 10000,
    // 行程结构
}
```

**response**: 

``` json
{
    "code": 0
}
```

**说明**：请求体中的days字段只传修改过的天，其中每一天中的字段只传更改过的内容，如只传content或cities

#### 6. /{{book.module}}/journey/get-notice

**描述**：获取出行提示

**request**：

``` json
{
    "countries": ["NZ"]
}
```

**response**：

``` json
{
  "code": 0,
  "list": [
    {
      "id": 60024,
      "type": "sys",
      "name": "新西兰",
      "content": "【安全提示】\n1.有心脑血管疾病或者特殊病史者请随身备好药品...",
      "country_code": "NZ"
    },
    {
      "id": 60049,
      "type": "user",
      "name": "自定义模板",
      "content": "自定义出行题示内容",
      "country_code": ""
    }
  ]
}
```

### /{{book.module}}/journey/create-notice

**描述**：添加自定义出行提示模板

**request**：

``` json
{ "name": "自定义模板标题" }
```

**response**：

``` json
{
  "code": 0,
  "id": 60049
}
```

### 7. /{{book.module}}/journey/update-notice

**描述**：更改出行提示

**request**：

``` json
{ "content": "行程模板内容", "id": 60049 }
```

**response**：

``` json
{
    "code": 0
}
```

### 8. /{{book.module}}/journey/query-city

**描述**：查询城市

**request**：

``` json
{ "keyword": "巴黎" }
```

**response**

``` json
{
  "code": 0,
  "list": [
    {
      "code": 387523,
      "name": "巴黎",
      "gps": {
        "lng": 2.3522219000000177,
        "lat": 48.856614
      },
      "days": 4,
      "country_code": "FR",
      "country_name": "法国"
    },
    {
      "code": 3102790,
      "name": "巴里",
      "gps": {
        "lng": 16.871871499999997,
        "lat": 41.1171432
      },
      "country_code": "IT",
      "country_name": "意大利"
    }
  ]
}
```

**说明**：城市的days是推荐游玩天数，作为创建行程时的默认天数，在行程编辑中选择每天的城市，该字段无用

### 9. /{{book.module}}/journey/add-city-history

**描述**：将城市添加进查询历史

**request**：

``` json
{
    //查询的城市结构
}
```

**response**：

``` json
{
    "code": 0
}
```

### 10. /{{book.module}}/journey/query-city-history

**描述**：获取查询城市的历史记录

**response**：

``` json
{
    "code": 0,
    "list": [
        {
            "code": 387523,
            "name": "巴黎",
            "gps": {
                "lng": 2.3522219000000177,
                "lat": 48.856614
            },
            "days": 4,
            "country_code": "FR",
            "country_name": "法国"
        }
    ]
}
```

### 11. /{{book.module}}/journey/delete-city-history

**描述**：删除城市历史记录

**request**：

``` json
{
    "code": 10000
}
```

**response**：

``` json
{
    "code": 0
}
```

### 12. /{{book.module}}/journey/clean-city-history

**描述**：清空城市历史记录

**response**：

``` json
{
    "code": 0
}
```

### 13. /{{book.module}}/journey/export-pdf

**描述**：给客人发送pdf

**request**

``` json
{
    "addr": "自己邮箱，默认是行程详情中的auth_mail",
    "formId": "小程序需要传该参数，其它忽略",
    "guestAddr": "客人邮箱，默认是行程详情中的guest_mail",
    "id": 93660,
    "watermark": true //图片是否要加个人水印
}
```