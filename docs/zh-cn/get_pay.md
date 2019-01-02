# 发起付款接口

> ## 接口地址

请求方式：`HTTP POST`

    http://www.xxx.com/get_pay

>## 请求参数

参数名称|含义|类型|必填/选填|说明
:--:|:--:|:--:|:--:|:--:
uid|用户UID|string|必填|您的唯一标识，注册后在“基本配置”页面里获得，一个32位字符串。
auth_code|授权码|string|必填|您的识别码，注册后在“接口参数配置”页面里获得。用于鉴别接口访问者。
total_amount|金额|double/float|必填|发起付款的金额，单位：元，精确到小数点后两位。
receive_way|支付类型|string|必填|支付宝或者微信，当前仅支持参数为 ALIPAY。
return_url|跳转地址|string|必填|用户支付成功后，我们会让用户浏览器自动跳转到这个网址。由您自定义。
order_id|订单号|string|必填|订单号，由您自定义，要求唯一性，不可重复。
key|加密字符串|string|必填|"格式为 MD5(uid + auth_code + total_amount + receive_way + return_url + order_id)"
plat_type|平台类型|string|选填|0：PC端支付,1：wap端跳转支付
user_msg|订单号|string|选填|备注

>## 响应参数

参数名称|含义|类型|说明
:--:|:--:|:--:|:--:
msg|请求状态描述|string|用于扫描状态码的说明信息，如：“创建成功”、“uid和auth_code 无法通过验证 请检查这两参数配置是否正确”。
code|返回状态码|string|状态码，用于标记接口的请求状态,200代表成功，其他代码表示请求失败，失败原因看msg字段
total_amount|金额|double/float|用户支付的金额
receive_way|支付类型|string|支付平台，支付宝或者微信 ALIPAY wechat 这两个值，当前仅会返回ALIPAY
re_url|跳转的支付链接|string|支付链接字符串，直接跳转到此链接即可支付。

>## 响应示例JSON

```json
{
                  "msg": "创建成功",
                  "code": 200,
                  "total_amount": "150",
                  "receive_way": "ALIPAY",
                  "re_url": "https://openapi.alipay.com/gateway.do?...."
                  }
```






