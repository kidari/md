# 1. 设备管理

## 1.1. 表结构

### 1.1.1. t_product  设备类型

> 见附件

### 1.1.2. t_equipment 设备详细信息表

> 见附件


## 1.2. 设备添加导入

|     |                                                                                                                                         |     |
| --- | --------------------------------------------------------------------------------------------------------------------------------------- | --- |
|     | 必填项                                                                                                                                  |     |
| 1   | IMEI ；                                                                                                                                 |     |
| 2   | ~~设备类型~~产品类型：a 独立式烟感；b 可燃气体探测器；c 剩余电流探测器； d 测温式探测器； e 组合式探测器；f:阻性漏电式探测器；g：协议转换与消息中间件 |     |
| 3   | 设备型号:每类设备各暂一个设备型号，型号名称待定                                                                                              |     |
|     | 选填项：                                                                                                                                |     |
| 1   | 安装位置                                                                                                                                |     |
| 2   | 经纬度信息                                                                                                                               |     |
| 3   | 设备别名                                                                                                                                |     |
| 4   | 设备编号                                                                                                                                |     |

## 1.3. 注册设备/批量注册设备

### 1.3.1. Restful api

   > /api/addequ
   >
   > /api/addequ_csv
   >
   > /api/download_temple

### 1.3.2. fpmp_platform所属类


| Controller          | Service          | Entity/Mapper |
| ------------------- | ---------------- | ------------- |
| EquipmentController | EquipmentService | Equipment     |
|                     |                  | Product       |
|                     |                  |               |

### 1.3.3. 批量注册设备文件位置

   ```properties
   #上传保存位置
   resource/static/csv/temporary/
   #模板位置
   resource/static/csv/template/
   ```

### 1.3.4. kafka消息格式

| topic | 格式                               |      |
| ----- | ---------------------------------- | ---- |
| test  | addEquipment%{Equipment}%{Product} |      |
|       |                                    |      |
|       |                                    |      |

### 1.3.5. 对接信息

|参数|选填|类型|位置|描述|表字段|
| ---- | ---- | ---- | ---- | ---- |---- |
| RegDirectDeviceInDTO2 |  | 输入值 |      |      |     |
|   deviceInfo   |  可选    |   DeviceInfoDTO   |    Body  |   设备信息。见下方DeviceInfo结构体说明。   |      |
|  imsi|可选|String(1-64)   |  Body    |NB-IoT终端的IMSI。      |equipment.IMSI|
|verifyCode|可选|String(256)|body|设备验证码，若指定verifyCode，则响应中返回指定的verifyCode；若不指定verifyCode，则由物联网平台自动生成。在NB-IoT中，verifyCode为必填参数，且必须与nodeId设置成相同值。|equipment.IMSI|
|nodeId |必选| String(256)| body |设备的唯一标识，必须与设备上报的设备标识一致。通常使用MAC地址，Serial No或IMEI作为nodeId。| equipment.IMSI|
|timeout |可选| Integer|Body|超时时间。当调用北向接口对设备开户，在超时时间内可绑定设备，若超过timeout时间且未绑定设备，则会删除超时的开户信息。取值范围：0～2147483647。若填写为“0”，则表示设备验证码不会失效（建议填写为“0”）单位：秒。 |0|
|productId |可选| String(256) |Body| 设备所属的产品ID。 |无法获取|
|DeviceInfoDTO||输入值||||
|manufacturerId |可选| String(256) |Body |厂商ID，唯一标识一个厂商。| product.manufacture_id|
|manufacturerName |可选| String(256)| Body |厂商名称。 |product.manufacture_name|
|deviceType| 可选| String(256) |Body |设备类型，大驼峰命名方式，如MultiSensor、ContactSensor、CameraGateway。 |product.dev_type|
|model |必选| String(256)| Body |设备型号Z-Wave：ProductType + ProductId，16 进制格式 XXXX-XXXX 补0对齐，如：001A-0A12，其他协议的格式待定。 |product.dev_model|
|protocolType| 可选 |String(256)| Body| 设备使用的协议类型，当前支持的协议类型：CoAP，huaweiM2M，Z-Wave，ONVIF，WPS，Hue，WiFi，J808，Gateway，ZigBee，LWM2M。| product.protocol_type|
|RegDirectDeviceOutDTO|  |返回值||||
|deviceId || String(256) | |设备ID，用于唯一标识一个设备。| equipment.dev_id|

### 1.3.6. 错误码

   
### 1.3.7. equipment表添加信息
|     |                 |     |
| --- | --------------- | --- |
|     | id              |     |
|     | IMEI            |     |
|     | dev_id          |     |
|     | type_name       |     |
|     | dev_model       |     |
|     | product_id      |     |
|     | project_id      |     |
|     | another_name    |     |
|     | active_status   |     |
|     | commission_time |     |
|     | service_life    |     |
|     | position        |     |
|     | longitude       |     |
|     | latitude        |     |
|     |                 |     |
|     |                 |     |
## 1.4. 查询设备

### 1.4.1. 显示项

| 序号 |                                                                    条目                                                                     |     |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------ | --- |
| 1    | ~~设备类型~~产品类型<br/> a 独立式烟感；b 可燃气体探测器；c 剩余电流探测器； d 测温式探测器； e 组合式探测器；f:阻性漏电式探测器；g：协议转换与消息中间件 |     |
| 2    | 设备注册状态：已注册/未注册                                                                                                                    |     |
| 3    | 投运时间                                                                                                                                    |     |
| 4    | IMEI                                                                                                                                       |     |
| 5    | 设备别名                                                                                                                                    |     |
| 6    | 安装位置                                                                                                                                    |     |
| 7    | 设备编号                                                                                                                                    |     |
| 8    | ~~设备ID~~ 序列号                                                                                                                            |     |
| 9    | 操作：见设备配置管理任务                                                                                                                      |     |


## 1.5. 设备配置管理

### 1.5.1. 安装信息

|      |     |
| ---- | --- |
| 备注 |图片上传|

   

### 1.5.2. 删除

   从iot平台删除

### 1.5.3. 设置

|       烟感       | 剩余电流探测器（4路） | 测温式探测器（4路） | 组合式探测器（1路剩余电流\+1路测温） |                              阻性漏电探测器                               |
| --------------- | ------------------- | ----------------- | -------------------------------- | ----------------------------------------------------------------------- |
| 心跳周期（h）     | 心跳周期（h）         | 心跳周期（h）       | 心跳周期（h）                      | 心跳周期（h）                                                             |
| 重传次数          | 重传次数             | 重传次数           | 重传次数                          | 重传次数                                                                 |
| 搜网周期时长（s） | 搜网周期时长（s）     | 搜网周期时长（s）   | 搜网周期时长（s）                  | 搜网周期时长（s）                                                         |
| 事务定时器时长(s) | 事务定时器时长(s)     | 事务定时器时长(s)   | 事务定时器时长(s)                  | 事务定时器时长(s)                                                         |
|                 | 漏电值设定（mA）      | 温度值设定（℃）    | 漏电值设定（mA）                   | 漏电值设定（mA）                                                          |
|                 |                     |                   | 温度值设定（℃）                   | 检测方式（0x00 - 单相I0r ；0x01 - 三相四线I0r；0x10 -<br/>I0；0x11 - 关闭） |

### 1.5.4. 查看/编辑


|     |                                                                                                                                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| 1   | ~~设备类型~~产品类型<br> a 独立式烟感；b 可燃气体探测器；c 剩余电流探测器； d 测温式探测器； e 组合式探测器；f:阻性漏电式探测器；g：协议转换与消息中间件 |
| 2   | 设备型号                                                                                                                                    |
| 3   | 设备别名                                                                                                                                    |
| 4   | 设备编号                                                                                                                                    |
| 5   | 安装位置                                                                                                                                    |
| 6   | 所属场所：下拉菜单形式，选择已添加的场所                                                                                                       |
| 7   | 投运时间                                                                                                                                    |
| 8   | 使用期限                                                                                                                                    |

### 1.5.5. 输入
