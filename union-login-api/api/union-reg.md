# 联合注册接口

**简要描述：** 

- 撞库检查用于确认合作方是否已注册该用户

**请求URL：** 
- ` 规范path后缀：/collisionRegLogin，如无特殊要求不会变更 `
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
| mobile | 是    | string | 手机号   |
| platform | 是    | string | 平台: 0 未知 1 android ；2 ios ； 3 H5；   |
| mec_id | 是    | string | 趣秒借分配的客户端id   |
| order_no     | 是    | string | 订单号   |
| timestamp     | 是    | string | 时间戳(毫秒 ）|
| sign | 是    | string | 请参照[API签名规范](/api/sign)|

 **返回示例**

``` 
{
    "status": 0,
    "msg": "success",
    "data": {
        "url": "http://www.txt.com/"
    }
}
```

 **返回参数说明** 

| 参数名   | 必选    | 类型   | 说明                   |
| :------ | :--- | :--- | -------------------- |
| status|  是 | int  | 状态码 0 成功, 1失败 |
| msg|  是 |  string  | 描述 成功success, 失败说明失败原因 |
| data|  是 | object  | 响应数据 |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;url|  是 | string  | 注册登录成功后跳转url |


 **备注** 

- channel_code 、channel_secret	由合作方提供
