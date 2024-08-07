<h1 align="center">- Serv00 Auto Renew -</h1>

<p align="center">
<img src="https://img.shields.io/github/license/amakerlife/serv00-auto-renew" alt="License" />
<img src="https://img.shields.io/github/last-commit/amakerlife/serv00-auto-renew">

在 Vercel 上部署 Serv00 保活。

---

## 快速开始

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Famakerlife%2Fserv00-auto-renew&env=BASIC_AUTH_USERNAME,BASIC_AUTH_PASSWORD,CRON_SECRET,HOST1,USERNAME1,PASSWORD1&project-name=serv00-auto-renew&repository-name=serv00-auto-renew)

填写完必需环境变量后部署，然后可在 Settings 里继续填写。

自行修改 vercel.json 以进行更多配置。

部署完毕可在 `https://your-domain.com/api/ssh-connect` 确认是否可用。

## 环境变量

> [!CAUTION]
> 环境变量格式已修改，请注意更改。


| 变量名              | 内容                                            |
| ------------------- | ----------------------------------------------- |
| BASIC_AUTH_USERNAME | HTTP 基本认证用户名                             |
| BASIC_AUTH_PASSWORD | HTTP 基本认证密码                               |
| CRON_SECRET         | Vercel 进行 Cron Jobs 时所用密码                |
| BARK（可选）        | BARK 推送密钥                                   |
| HOSTx               | 例如 `HOST1`，可配置多个，为 SSH 连接地址       |
| USERNAMEx           | 例如 `USERNAME1`，可配置多个，为 SSH 连接用户名 |
| PASSWORDx           | 例如 `PASSWORD1`，可配置多个，为 SSH 连接密码   |
| COMMANDx（可选）    | 例如 `COMMAND1`，可配置多个，为 SSH 执行的命令  |

注意可配置多个的环境变量需配套使用。

## 定时任务

如需更改定时任务设置，请修改 `vercel.json`。

默认 `ssh-connect` 在每月 10、20、28 日执行一次，`ssh-command` 每天一次。

> [!TIP]
> Vercel 免费版单 Cron Job 一天最多执行一次，即 `0 0 * * *`。
