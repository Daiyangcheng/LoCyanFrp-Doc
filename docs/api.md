# API

::: warning
该页面还未完成
:::

## 登录

#### 请求URL: `/api/v2/users/login`

#### 请求方式: **POST**

#### 请求参数:

#### Header

*None*

#### Body

| 字段名 | 解释 |
| ---- | ---- |
| username | 用户名 |
| password | 密码 |

#### **Params**

*None*

#### 返回值:

```json
{
    "msg": "success",
    "data": {
        "msg": "",
        "inbound": 14657792,
        "outbound": 14657792,
        "reg_time": "1651299025",
        "frp_token": "ajmfijmawisjfijkmwiskf",
        "avatar": "https://cravatar.cn/avatar/541",
        "email": "example@example.com",
        "username": "testuser",
        "token": "afaiwjnfmiaiw",
        "traffic": "999999",
        "group": "default"
    },
    "status": 200
}` 
```

|  返回值              |       解释         |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|    data.msg    |    接口返回的消息        |
|  data.inbound  |  下行流量限速 |
| data.outbound   |   上行流量限速 |
| data.reg_time   |    用户注册时间戳        |
| data.frp_token  |       frp令牌          |
|  data.avatar    |       用户头像       |
|   data.email    |       用户邮箱       |
| data.username   |        用户名        |
|   data.token    |       用户令牌       |
|  data.traffic   | 用户剩余流量(单位MB)   |
|   data.group    |        用户组        |
|  status    |      HTTP状态码      |

## 重置密码

#### 请求URL: `/api/v2/users/reset/password`

#### 请求方式: **POST**

#### 请求参数:

#### Header

| 字段名 | 值 |
| :-: | :-: |
| Authorization | 登录接口返回的 data.token |

#### Body

|    字段名     |              值               |
| :-----------: | :---------------------------: |
|    username     |           用户名            |
|    old_password     |           原密码            |
|    new_password     |           新密码            |

#### 返回值:

```json
{
    "msg": "success",
    "data": {
        "msg": ""
    },
    "status": 200
}
```

|  返回值              |       解释         |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|    data.msg    |    接口返回的消息        |
|  status    |      HTTP状态码      |

## 用户信息

#### 请求URL: `/api/v2/users/info`

#### 请求方式: **GET**

#### 请求参数:

#### Header

| 字段名 | 值 |
| :-: | :-: |
| Authorization | 登录接口返回的 data.token |

#### Param

|    字段名     |              值               |
| :-----------: | :---------------------------: |
|    username     |           用户名            |

#### 返回值:

```json
{
{
    "msg": "success",
    "data": {
        "qq": "",
        "msg": "",
        "qq_social_id": "",
        "inbound": 0,
        "outbound": 0,
        "reg_time": "",
        "id": 0,
        "email": "",
        "username": "",
        "traffic": ""
    },
    "status": 200
}
}
```

|  返回值              |       解释         |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|    data.msg    |    接口返回的消息        |
|  data.qq_social_id  | QQ互联ID |
| data.qq | 用户注册QQ |
| data.inbound | 限速下行, 单位 Kbps |
| data.outbound | 限速上行, 单位 Kbps |
| data.reg_time | 用户注册时间戳 |
| data.id |    用户ID    |
| data.email |   用户邮箱 |
| data.username |       用户名       |
| data.traffic |       用户剩余流量(单位MB)       |
|  status    |      HTTP状态码      |

## 吊销指定用户全部登录 Token

#### 请求URL: `/api/v2/users/reset/token/all`

#### 请求方式: **DELETE**

#### 请求参数:

#### Header

| 字段名 | 值 |
| :-: | :-: |
| Authorization | 登录接口返回的 data.token |

#### Param

|    字段名     |              值               |
| :-----------: | :---------------------------: |
|    username     |           用户名            |

#### 返回值:

```json
{
    "msg": "success",
    "data": {
        "msg": ""
    },
    "status": 200
}
```

|  返回值              |       解释         |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|    data.msg    |    接口返回的消息        |
|  status    |      HTTP状态码      |

## 吊销指定用户指定 Token

#### 请求URL: `/api/v2/users/reset/token/single`

#### 请求方式: **DELETE**

#### 请求参数:

#### Header

| 字段名 | 值 |
| :-: | :-: |
| Authorization | 登录接口返回的 data.token |

#### Param

|    字段名     |              值               |
| :-----------: | :---------------------------: |
|    username     |           用户名            |

#### 返回值:

```json
{
    "msg": "success",
    "data": {
        "msg": ""
    },
    "status": 200
}
```

|  返回值              |       解释         |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|    data.msg    |    接口返回的消息        |
|  status    |      HTTP状态码      |

## 查询签到状态

#### 请求URL: `/api/v2/sign/check`

#### 请求方式: **GET**

#### 请求参数:

#### Header

| 字段名 | 值 |
| :-: | :-: |
| Authorization | 登录接口返回的 data.token |

#### Param

|    字段名     |              值               |
| :-----------: | :---------------------------: |
|    username     |           用户名            |

#### 返回值:

```json
{
    "msg": "success",
    "data": {
        "msg": "",
        "status": false
    },
    "status": 200
}
```

|  返回值              |       解释         |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|    data.msg    |    接口返回的消息        |
|  status    |      HTTP状态码      |
|  data.status    |      是否已签到, 已签到返回 **true**, 没签到返回 **false**      |

## 签到

#### 请求URL: `/api/v2/sign/sign`

#### 请求方式: **GET**

#### 请求参数:

#### Header

| 字段名 | 值 |
| :-: | :-: |
| Authorization | 登录接口返回的 data.token |

#### Param

|    字段名     |              值               |
| :-----------: | :---------------------------: |
|    username     |           用户名            |

#### 返回值:

```json
{
    "msg": "success",
    "data": {
        "signTraffic": 0,
        "firstSign": true,
        "msg": "",
        "totalSignCount": 0,
        "totalSignTraffic": 0
    },
    "status": 200
}
```

|  返回值              |       解释         |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|  status    |      HTTP状态码      |
|    data.signTraffic    |    本次签到获得了多少流量, 单位 GB        |
|  data.firstSign    |      是否是第一次签到, 是返回 **true**, 不是返回 **false**      |
|    data.totalSignCount    |    签到总次数        |
|    data.msg    |    签到获得了多少流量, 单位 GB        |
|    data.totalSignTraffic    |    签到总获得流量, 单位 GB        |