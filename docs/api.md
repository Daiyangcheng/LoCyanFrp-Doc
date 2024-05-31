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



|  返回值              |       解释  	      |
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
|  data.status    |      HTTP状态码      |

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

|  返回值              |       解释  	      |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|    data.msg    |    接口返回的消息        |
|  data.status    |      HTTP状态码      |

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
    "msg": "success",
    "data": {
        "msg": "",
        "qqSocialId": ,
        "reg_time": "",
        "id": ,
        "email": "",
        "username": "",
        "traffic": ""
    },
    "status": 200
}
```

|  返回值              |       解释  	      |
| :------------:     | :------------------: |
|      msg           |     接口请求状态         |
|    data.msg    |    接口返回的消息        |
|  data.qqSocialId  | QQ互联ID |
| data.reg_time | 用户注册时间戳 |
| data.id |    用户ID    |
| data.email |   用户邮箱 |
| data.username |       用户名       |
| data.traffic |       用户剩余流量(单位MB)       |
|  data.status    |      HTTP状态码      |