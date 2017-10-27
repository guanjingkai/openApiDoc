### 接口描述
主要用于商家`主动`扫描/输入用户`付款码`完成收款的场景
### 请求地址
> http(s)://api.huishouyin.cn/pay/refund

### 请求方式
`POST`
### 请求参数
|参数|类型|必填|最大长度|描述|
|-----|-----|-----|-----|-----|
|app_id|String|是|32|应用ID|
|service_id|String|是|32|服务商ID|
|sign|String|是|32|签名|
|order_id|String|是|128|原支付业务单号|
|refund_order_id|String|是|128|退款业务单号|
|refund_amount|String|是| - |实际退款金额，如传0则代表全额退款，退款金额不得大于实际支付金额|
### 请求事例
```javascript
{
    app_id:'bT2CAkZUgoOr36BnZhuC1aTvXgxhvmhF',
    service_id:'HUpLsX7XQWFH3iktwFFMmi1GNdKH7Ef3',
    sign:'L4XYdVQWe0DROIQBxxtrYKWawTIrXofe',
    order_id:'2017102100151091',
    refund_order_id:'2017102100151091',
    refund_amount:11.00
}
```
### 响应参数
|参数|类型|必填|最大长度|描述|
|-----|-----|-----|-----|-----|
|state|int|是|1|应用ID|
|msg|String|是|1|应用ID|
|refund_order_id|String|是|32|退款业务单号|
### 响应事例
```javascript
{
    code:'SUCCESS',
    msg:'退款成功',
    data:{
        refund_order_id:'2017102100151091'
    }
}
```
### 异常响应
|名称|描述|
|-----|-----|
|SIGN_ERROR|签名错误|
|APPID_ERROR|APPID错误|
|REFUND_AMOUNT_ERROR|退款金额大于实际金额|
### 异常响应事例
```javascript
{
    code:'REFUND_AMOUNT_ERROR',
    msg:'退款金额大于实际金额',
    data:{
        
    }
}
```