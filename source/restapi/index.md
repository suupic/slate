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
创建一个支付订单

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
````

```shell
curl "https://api.example.com/v1/orders"
  -H "access_token=xxxxx"
  -d "app_id=123" \
  -d "pay_type=1" \
  -d "amount=10.00" \
  -d "sign=387120464"
```

```json
{
    "code":0,
    "message":"支付成功",
    "data":{
        "status":0,
        "type":0,
        "created_at":"2003-1-1 00:00:00",
        "updated_at":"2003-1-1 00:00:01",
        "expire_at":"2003-1-2 00:00:00",
        "app":{
            "id":29232,
            "merchant_id":33221
        },
        "payment":{
            "type":1,
            "platform":1,
            "amount":100,
            "currency":"CNY"
        },
        "product":{
            "id":1231422,
            "name":"金币"
        },
        "client":{
            "ip":"8.8.8.8"
        },
        "ext_data":{
        }
    }
}
```

### HTTP 请求

`POST https://api.example.com/v1/orders`

### 请求参数

必选参数 | 类型 | 说明
--------- | ------- | -----------
app_id     | long   | 商户代码
pay_type   | int    | 支付方式
amount     | int    | 金额
sign       | string | 签名

可选参数 | 类型 | 说明
--------- | ------- | -----------
product_id   | string | 商品代码
product_name | string | 商品名称
ext_data     | string | 外部扩展字段
memo         | string | 备注
sign_type    | int    | 签名方式
os           | string | 操作系统
os_version   | string | 操作系统版本
source_id    | long   | 渠道编码

### 返回结果
基本属性     | 类型 | 说明
--------- | ------- | -----------
code       | int    | 状态码
message    | string | 消息
data       |        | 数据体

data    | 类型   | 说明
--------- | -------  | -----------
type         | int    | 订单类型
status       | int     | 状态
created_at   | string  | 创建时间
updated_at   | string  | 修改时间
expire_at    | string  | 过期时间

data['app'] | 类型   | 说明
----------- | --------  | -----------
id     | long    | 应用ID
merchant_id| long    | 商户ID

data['payment'] | 类型   | 说明
----------- | --------  | -----------
type   | int     | 支付方式
platform   | int     | 支付平台 
amount     | int     | 金额
currency   | int     | 币种

data['product'] | 类型   | 说明
----------- | --------  | -----------
product_id   | int     | 商品编码
product_name | string  | 商品名称

data['client'] | 类型   | 说明
----------- | --------  | -----------
ip  | string    | 客户端IP

data['ext_data'] | 类型   | 说明
----------- | --------  | -----------

<aside class="notice">
这是一个notice
</aside>

## 订单查询

查询订单详情

```shell
curl "https://api.example.com/v1/orders"
  -H "access_token=xxxxx"
  -d "app_id=123" \
  -d "pay_type=1" \
  -d "amount=10.00" \
  -d "sign=387120464"
```

```json
{
    "code":0,
    "message":"success",
    "count":2,
    "data": [
         {
            "status":0,
            "type":0,
            "created_at":"2003-1-1 00:00:00",
            "updated_at":"2003-1-1 00:00:01",
            "expire_at":"2003-1-2 00:00:00",
            "app":{
                "id":29232,
                "merchant_id":33221
            },
            "payment":{
                "type":1,
                "platform":1,
                "amount":100,
                "currency":"CNY"
            },
            "product":{
                "id":1231422,
                "name":"金币"
            },
            "client":{
                "ip":"8.8.8.8"
            },
            "ext_data":{
            }
         },
         {
            "status":0,
            "type":0,
            "created_at":"2003-1-1 00:00:00",
            "updated_at":"2003-1-1 00:00:01",
            "expire_at":"2003-1-2 00:00:00",
            "app":{
                "id":29232,
                "merchant_id":33221
            },
            "payment":{
                "type":1,
                "platform":1,
                "amount":100,
                "currency":"CNY"
            },
            "product":{
                "id":1231422,
                "name":"金币"
            },
            "client":{
                "ip":"8.8.8.8"
            },
            "ext_data":{
            }
         }    
    ]
}
```


### HTTP 请求

`GET https://api.example.com/v1/orders`

### 请求参数

必选参数 | 类型 | 说明
--------- | ------- | -----------
ids       |  array  | 订单ID的数组
app_id    |  long   | 应用ID
sign      |  string | 签名

可选参数 | 类型 | 说明
--------- | ------- | -----------
sign_type |  int    | 签名方式

### 返回结果

基本属性     | 类型 | 说明
--------- | ------- | -----------
code       | int    | 状态码
message    | string | 消息
total      | int    | 包含数据条数
data       |        | 数据体

data    | 类型   | 说明
--------- | -------  | -----------
type         | int    | 订单类型
status       | int     | 状态
created_at   | string  | 创建时间
updated_at   | string  | 修改时间
expire_at    | string  | 过期时间

data['app'] | 类型   | 说明
----------- | --------  | -----------
id     | long    | 应用ID
merchant_id| long    | 商户ID

data['payment'] | 类型   | 说明
----------- | --------  | -----------
type   | int     | 支付方式
platform   | int     | 支付平台 
amount     | int     | 金额
currency   | int     | 币种

data['product'] | 类型   | 说明
----------- | --------  | -----------
product_id   | int     | 商品编码
product_name | string  | 商品名称

data['client'] | 类型   | 说明
----------- | --------  | -----------
ip  | string    | 客户端IP

data['ext_data'] | 类型   | 说明
----------- | --------  | -----------


  
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