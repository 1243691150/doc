# 状态回调接口
**简要描述：** 

- 合作方回调用户状态给趣秒借

**请求URL(趣秒借给出)：** 
-  `生产环境: /unionLoginApi/statusCallBack`
-  `测试环境: /unionLoginApi/statusCallBack`


**请求方式：**
- POST 

**请求数据类型：** 
- `application/json`

**参数：** 

| 参数名      | 必选   | 类型     | 说明   |
| :------- | :--- | :----- | ---- |
| mec_id | 是    | string | 趣秒借分配的客户端id   |
| order_no     | 是    | string | 订单号   |
| order_status | 是    | string |订单状态 (0:待审核，1:已取消，2:审核失败，4:待签约，5:签约失败，6:待放款，7:已放款，8:正常结清，10:逾期还清) |
| sign | 是    | string |请参照[API签名规范](/api/sign)|

 **返回示例**
``` 
{
    "status": 0,
    "msg": "success"
}
```

 **返回参数说明** 

| 参数名   | 必选    | 类型   | 说明                   |
| :------ | :--- | :--- | -------------------- |
| status|  是 | int  | 状态码 0 成功, 1失败 |
| msg|  是 |  string  | 描述 成功success, 失败说明失败原因 |


 
 **备注** 

- order_no为联合注册时趣秒借传给合作方的订单号