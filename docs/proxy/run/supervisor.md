# 使用 Supervisor 运行和管理 Frpc

假设你已经完成了 Supervisor 的配置
我们假设你的 Frpc 和配置文件在 `/opt/lcf/` 中，配置文件名为 `frpc.ini`

## 给与 Frpc 运行权限

```sh
chmod +x /opt/lcf/frpc
```

## 配置服务

在 `/etc/supervisord.d/` 中新建一个 `.ini` 后缀的文件，并写入以下内容

```ini
[program:lcf_frpc]
command                 = /opt/lcf/frpc
directory               = /opt/lcf
autorestart             = true
startsecs               = 3
stdout_logfile          = /opt/lcf/frpc.log
redirect_stderr         = true
```

## 重载 Supervisor

```sh
supervisorctl update
```
