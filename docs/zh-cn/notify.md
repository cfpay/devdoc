# 付款成功通知接口

> ## 回调地址

接受方式：`HTTP POST`

    您在发起付款接口里传入的通知接口 即后台的回调地址

>## 您需接收的参数列表

参数名称|含义|类型|说明
:--:|:--:|:--:|:--:
msg|请求状态描述|string|"用于扫描状态码的说明信息，如：“查询成功”、“uid和auth_code 无法通过验证 请检查这两参数配置是否正确”"
code|返回状态码|string|状态码，用于标记接口的请求状态,200代表成功，其他代码表示请求失败，失败原因看msg字段
money|金额|double/float|用户支付的金额
receive_way|支付类型|string|支付平台，支付宝或者微信 ALIPAY wechat 这两个值，当前仅会返回ALIPAY
order_no|商户编号|string|后台返回的商户编号
order_id|订单编号|string|您在发起付款接口里传入的订单号
pay_status|支付状态|string|"支付状态，PAYING:支付中,TRADE_SUCCESS:已支付,TRADE_CLOSE:支付关闭"
add_time|创建时间|string|订单创建的时间
pay_time|支付时间|string|订单支付的时间
user_msg|备注|string|


>## 返回样例JSON

```json
{
              "msg": "查询成功",
              "code": 200,
              "money": 150,
              "usr_msg": "测试24",
              "add_time": "2018-12-29T18:27:49",
              "pay_status": "PAYING",
              "order_no": "201812291827484061231484",
              "order_id": "1113111111",
              "receive_way": "ALIPAY",
              "pay_time": null
              }
```






