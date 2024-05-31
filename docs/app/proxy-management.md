# 隧道管理
本章会教你如何创建一条用于使用的隧道

## 创建隧道
1. 打开[后台-创建隧道](https://dashboard.locyanfrp.cn/proxies/addproxies)

![1716086568972.png](https://alist.locyan.cn/p/pics/docs/2024/05/19/1716086568972.png)

2. 选择一个适合自己的节点 （开设 MC 服建议首选距离自己近且负载低的节点）
3. 输入隧道基本信息

| 字段名 | 注释 |
| - | - |
| 隧道名 | 隧道的名称，同节点不可重复，不同的节点可重复 |
| 隧道类型 | 选择适合的网络协议，例如：Minecraft-Java 为 TCP，Bedrock 为 UDP |
| 本地IP | 通常填写 127.0.0.1，如需要映射内网其他设备可修改 |
| 本地端口 | 本地服务运行的端口号 |
| 远程端口 | 节点上为你使用的端口，若无特殊需求随机即可 |
| 域名 | HTTP(S) 类型隧道需要填写，使用国内节点建站需在网站左侧添加域名白名单 |

4. 点击添加按钮，大功告成！

### 常见游戏协议及端口对照表

| 游戏名 | 协议 | 端口 |
| - | - | - |
| Minecraft-Java | TCP | 25565 |
| Minecraft-Bedrock | UDP | 19132 |
| 泰拉瑞亚 | UDP | 7777 |
| Palworld | UDP | 8211 |

## 隧道列表
你可以在 [隧道列表](https://dashboard.locyanfrp.cn/proxies) 页面管理你的隧道

### 隧道列表常见问题
暂无

## 启动隧道

### 下载软件
LoCyanFrp 提供了许多平台的客户端供各位用户使用

1. [Nya LoCyanFrp!](https://nyalcf.1l1.icu/)
2. [PureApp 原版 GoLang 客户端](https://download.locyan.cn/locyanfrp/PureFrpc)
3. [Python 客户端](https://github.com/LoCyan-Team/LoCyanFrpPyLauncher)

### 启动隧道常见报错对照表

| 报错内容 | 注释 |
| - | - |
| 403 Forbidden | 没有权限连接至此服务器，通常为没有[实人](/app/account#一级认证) |
| 404 Not Found | 如果是使用 [Nya LoCyanFrp!](https://nyalcf.1l1.icu/) 启动的游戏，那么请在隧道列表删除自定义配置文件后重试 |
| no such host | 更新客户端版本即可 |
| i/o timed out | 服务器崩了, [联系管理员](/app/contact.html)等待修复 |
| cannot connect to local service X.X.X.X:XXXXX, target machine actively refused it | 检查本地服务是否还在运行, 本地设备能否直接连接到 X.X.X.X:XXXXX |