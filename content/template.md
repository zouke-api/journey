### 1. /{{book.module}}/template/get-themes

**描述**：获取行程主题

**response**

``` json
{
  "code": 0,
  "list": [
    {
      "id": "find-usa",
      "image": "https://cdn1.zouke.com/journey/collection/usa.jpg",
      "title": "发现北美"
    },
    {
      "id": "nice-asia",
      "image": "https://cdn1.zouke.com/journey/collection/asia.jpg",
      "title": "缤纷亚洲"
    }
  ]
}
```

### 2. /{{book.module}}/template/query-by-theme

**描述**：查找主题下的行程模版

**request**：

``` json
{
    "id": "find-usa"
}
```

**response**

``` json
{
  "code": 0,
  "title": "发现北美",
  "list": [
    {
      "id": 360017,
      "days": 5,
      "title": "温哥华极致公园、魅力峡湾5日游",
      "image": "https://cdn1.zouke.com/journey/edit/1495508116037_9086_NjY2NjYuanBn.jpg-guidefixwid",
      "countries": [
        "加拿大"
      ]
    },
    {
      "id": 360022,
      "days": 5,
      "title": "休士顿浪漫挚美5日游",
      "image": "https://cdn1.zouke.com/journey/edit/1495177389923_2513_5rOi5aOr6aG_LmpwZw.jpg-guidefixwid",
      "countries": [
        "美国"
      ]
    }
  ]
}
```

### 3. /{{book.module}}/template/get-countries

**描述**：获取所有国家

**response**：

``` json
{
  "code": 0,
  "list": [
    {
      "area": "欧洲",
      "subareas": [
        {
          "area": "西欧",
          "countries": [
            { "code": "FR", "name": "法国" },
            { "code": "DE", "name": "德国" }
          ]
        },
        {
          "area": "南欧",
          "countries": [
            { "code": "IT", "name": "意大利" },
            { "code": "ES", "name": "西班牙" }
          ]
        },
        {
          "area": "东欧",
          "countries": [
            { "code": "CZ", "name": "捷克" },
            { "code": "AT", "name": "奥地利" }
          ]
        },
        {
          "area": "北欧",
          "countries": [
            { "code": "SE", "name": "瑞典" },
            { "code": "NO", "name": "挪威" }
          ]
        }
      ]
    },
    {
      "area": "北美",
      "countries": [
        { "code": "US", "name": "美国" },
        { "code": "CA", "name": "加拿大" }
      ]
    },
    {
      "area": "大洋洲",
      "countries": [
        { "code": "AU", "name": "澳大利亚" },
        { "code": "NZ", "name": "新西兰" }
      ]
    },
    {
      "area": "亚洲",
      "countries": [
        { "code": "JP", "name": "日本" },
        { "code": "LK", "name": "斯里兰卡" }
      ]
    }
  ]
}
```

### 4. /{{book.module}}/template/query

**描述**：查询行程模板

**request**：

``` json
{
    "days": "1-2",
    "countries": ["FR"],
    "p": 0,
    "ps": 20
}
```

**response**：

``` json
{
  "code": 0,
  "list": [
    {
      "id": 60139,
      "days": 8,
      "title": "法国1国8日游南法浪漫之旅",
      "image": "https://cdn1.zouke.com/library/50011/1465367143498_3449_%25u89C2%25u5149%25u5DF4%25u58EB%25uFF0D%25u5C3C%25u65AF%25uFF0D04.jpg-guidefixwid",
      "countries": [
        "法国"
      ]
    },
    {
      "id": 60154,
      "days": 8,
      "title": "南法8日艺术之旅",
      "image": "https://cdn1.zouke.com/library/50011/1472536422223_5320_stock%252dphoto%252d138925279.jpg-guidefixwid",
      "countries": [
        "法国"
      ]
    }
  ],
  "total": 500
}
```

### 5. /{{book.module}}/template/query-by-countries

**描述**：查询行程模板

**request**：

``` json
{
    "countries": ["FR"]
}
```

**response**：

``` json
{
    "code": 0,
    "list": [
        { 
            "id": 1000, 
            "days": 7,
            "title": "xxxxx", 
            "image": "https://xxx", 
            "countries": ["巴黎"] 
        }
    ]
}
```

### 6. /{{book.module}}/template/get-detail

**描述**：查看模板详情

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
