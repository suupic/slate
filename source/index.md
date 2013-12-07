---
title: Android SDK 参考文档

language_tabs:
  - java: 示例代码

toc_footers:
 - <a href='/restapi'>REST API文档</a>
---
# 新手上路
## 简介
### 功能时序图

### SDK替您完成...

1. 向用户展示适用于支付的动态UI
2. 处理支付操作
3. 向应用返回支付信息

### 您只需...

1. 从SDK获得支付订单反馈
2. 发送反馈信息到您的服务器并验证
3. 向用户提供匹配的产品和服务

## 系统需求
# 准备工作
## 下载SDK
## 配置系统环境
# 项目工程配置
# 授权证书
# 功能示例
## 发起支付

当用户点击“支付”按钮时，调用此操作

```java
public class java {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
BasicAmountType billingAmount = new BasicAmountType(
                                CurrencyCodeType.USD, "3.00");
```
### 方法
Payment.create

### 参数

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

# 测试 

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

0.1 - 文档测试


