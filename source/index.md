---
title: API 参考文档

language_tabs:
  - shell
  - php
  - java

toc_footers:
 - <a href='#'>Sign Up for a Developer Key</a>
 - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>
---

# 简介

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in CURL, JAVA, and PHP! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](http://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# 变更记录

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace `meowmeowmeow` with your personal API key.
</aside>

# 授权认证

## 获取Token
<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

# 支付订单
## 订单创建
生成一个支付订单

```shell
curl "http://api.example.com/v1/payments/new"
  -d "product_id=123" \
  -d "product_name=apple" \
  -d "amount=10.00"
```

```php
curl "http://api.example.com/v1/payments/payment"
  -d "product_id=123" \
  -d "product_name=apple" \
  -d "amount=10.00"
```

```java
curl "http://api.example.com/v1/payments/payment"
  -d "product_id=123" \
  -d "product_name=apple" \
  -d "amount=10.00"

  //响应示例:

  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }

```


### HTTP 请求

`POST http://api.example.com/v1/payments/payment`

### 请求参数

必选参数 | 类型 | 说明
--------- | ------- | -----------
source_id | Long | 渠道代码
product_id | String | 商品代码
product_name | String | 商品名称
amount | Int | 金额


可选参数 | 类型 | 说明
--------- | ------- | -----------
external_ext | String | 外部扩展字段
memo | String | 备注


## 订单查询
# 已售商品
## 查询已售
## 退款
# 退款处理
## 查询退款
# 渠道路由
## 添加渠道
## 删除渠道
## 查询渠道
# 错误代码

The Kittn API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The kitten requested is hidden for administrators only
404 | Not Found -- The specified kitten could not be found
405 | Method Not Allowed -- You tried to access a kitten with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The kitten requested has been removed from our servers
418 | I'm a teapot
429 | Too Many Requests -- You're requesting too many kittens! Slown down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.
