# 用户撞库检查接口

**简要描述：** 

- 撞库检查用于确认合作方是否已注册该用户

**请求URL：** 
- ` 规范path后缀：/userCheck，如无特殊要求不会变更 `
-  `生产环境: 合作方提供前缀`
-  `测试环境: 合作方提供前缀`


**请求方式：**
- POST 

**请求数据类型：** 
- `application/json`

**参数：** 

| 参数名      | 必选   | 类型     | 说明   |
| :------- | :--- | :----- | ---- |
| channel_code | 是    | string | 合作方渠道编号  |
| mobile_hash | 是    | string | MD5 加密过后的手机号(转换为小写)   |
| mec_id | 是    | string | 趣秒借分配的客户端id   |
| order_no     | 是    | string | 订单号   |
| sign | 是    | string |请参照[API签名规范](/api/sign)|

 **返回示例**
``` 
{
    "status": 0,
    "msg": "success",
    "data": {
        "bus_status": 0,
        "mobile_hash": "c17c402c57e170209975aa3dde64368c"
    }
}
```

 **返回参数说明** 

| 参数名   | 必选    | 类型   | 说明                   |
| :------ | :--- | :--- | -------------------- |
| status|  是 | int  | 状态码 0 成功, 1失败 |
| msg|  是 |  string  | 描述 成功success, 失败说明失败原因 |
| data|  是 | object  | 响应数据 |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;mobile_hash|  否 | string  | 命中结果 命中:返回手机号MD5  未命中:返回空  |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;bus_status|  是 | integer  | 业务状态码 0 未命中  1 命中  |


 **备注** 

- channel_code 、channel_secret	由合作方提供
