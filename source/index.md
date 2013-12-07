---
title: API 参考文档

language_tabs:
  - shell: CURL
  - php: PHP 
  - c: ANDROID
  - java: JAVA


toc_footers:
 - <a href='#'>Sign Up for a Developer Key</a>
 - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>
---
# 产品简介
## 功能时序图

# 新手上路
## Android 集成引导

### 聚易付SDK替您完成...

1. 向用户展示适用于支付的动态UI
2. 处理支付操作
3. 向应用返回支付信息

### 您只需...

1. 从聚易付SDK接收支付信息反馈
2. 发送支付信息到您的服务器并验证
3. 为用户提供支付订单匹配的产品和服务

#### 初始化设置
## PHP 集成引导

# 授权机制说明
## 获取Token
<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

# 支付订单
## 订单创建
生成一个支付订单

```shell
curl "https://api.example.com/v1/payments/new"
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

```c
android code here
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

# 变更记录

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`


