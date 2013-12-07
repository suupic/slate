---
title: API 参考文档

language_tabs:
  - shell: CURL
  - java: JAVA
  - php: PHP 
  - python: PYTHON
  - ruby: RUBY

toc_footers:
 - <a href='/'>Android SDK文档</a>
---

# 简介
## 系统需求
## 功能时序图

# 授权机制说明
## 获取Token
<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

# 支付订单
## 订单创建
生成一个支付订单

```shell
curl "https://api.example.com/v1/payments/payment"
  -H "access_token=xxxxx"
  -d "product_id=123" \
  -d "product_name=apple" \
  -d "amount=10.00"
```


```php
<?php
  print("Hello {$world}");
?>
```

```java
public class java {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
BasicAmountType billingAmount = new BasicAmountType(
                                CurrencyCodeType.USD, "3.00");
```

### HTTP 请求

`POST https://api.example.com/v1/payments/create`

### 请求参数

必选参数 | 类型 | 说明
--------- | ------- | -----------
source_id | Long | 商户代码
product_id | String | 商品代码
product_name | String | 商品名称
amount | Int | 金额
<aside class="notice">
这是一个notice
</aside>

可选参数 | 类型 | 说明
--------- | ------- | -----------
external_ext | String | 外部扩展字段
memo | String | 备注

## 订单查询

查询订单详情

### HTTP 请求

`GET https://api.example.com/v1/payments`

### 请求参数

必选参数 | 类型 | 说明
--------- | ------- | -----------
order_id | String | 订单代码

# 渠道路由
## 添加渠道
## 删除渠道
## 查询渠道
# 清算
## 账单查询
# 错误代码

在运行过程中，可能返回如下错误代码：

代码 | 含义
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
0000| 成功

# 变更历史

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`