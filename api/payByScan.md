### 接口描述
主要用于商家`主动`展示付款码，用户通过`扫一扫`完成付款的场景
### 请求地址
> http(s)://api.huishouyin.cn/pay/payByScan

### 请求方式
`POST`
### 请求参数
|参数|类型|必填|最大长度|描述|
|-----|-----|-----|-----|-----|
|app_id|String|是|32|应用ID|
|service_id|String|是|32|服务商ID|
|sign|String|是|32|签名|
|order_id|String|是|128|业务单号|
|real_amount|String|是| - |实际支付金额|
|goods_list|Array|是||商品列表|
| └ barcode|String|是|32|国际条码|
| └ title|String||256|商品名称|
| └ num|int|是|32|商品数量|
| └ price|double|是| - |单价签名|
### 请求事例
```javascript
{
    app_id:'bT2CAkZUgoOr36BnZhuC1aTvXgxhvmhF',
    service_id:'HUpLsX7XQWFH3iktwFFMmi1GNdKH7Ef3',
    sign:'L4XYdVQWe0DROIQBxxtrYKWawTIrXofe',
    order_id:'2017102100151091',
    total_amount:11.00, 
    goods_list:[
        {
            barcode:'6983748939221',
            title:'可口可乐300ml',
            num:2,
            price:3.00
        },{
            barcode:'6987483920018',
            title:'康师傅big香辣牛肉面',
            num:1,
            price:5.00
        }
    ]
    
}
```
### 响应参数
|参数|类型|必填|最大长度|描述|
|-----|-----|-----|-----|-----|
|state|int|是|1|应用ID|
|msg|String|是|1|应用ID|
|order_id|String|是|32|服务商ID|
|total_amount|double|是|-|应付金额|
|pay_url|double|是|-|支付连接|
### 响应事例
```javascript
{
    code:'SUCCESS',
    msg:'支付成功',
    data:{
        order_id:'2017102100151091',
        total_amount:11.0,
        pay_url:'http://www.liantuo.com/xxx/xxx/xxx'
    }
}
```
### 异常响应
|名称|描述|
|-----|-----|
|SIGN_ERROR|签名错误|
|APPID_ERROR|APPID错误|
### 异常响应事例
```javascript
{
    code:'SIGN_ERROR',
    msg:'签名错误',
    data:{
        
    }
}
```