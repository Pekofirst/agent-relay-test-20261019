# agent-relay-test-20261019

Relay test: Hermes -> PC -> Hermes -> public server -> Hermes -> GitHub

这个仓库是 **Hermes 统一调用模型** 一次真实接力测试的产物：一个文件依次经过
中枢服务器 → 个人电脑 → 中枢服务器 → 公网服务器 → 中枢服务器，
**每一站都由该站自己盖上本地时间戳**，最后发布到这里。

## 接力记录

| # | 站点 | 主机名 | 当地时间 | 平台 |
|---|---|---|---|---|
| 1 | `hub-server-start` | `pekoserver` | 2026-10-19T00:43:37.436+08:00 | Linux 5.15.0-177-generic |
| 2 | `pc-windows` | `PEKO` | 2026-10-19T00:43:46.559+08:00 | Windows 11 |
| 3 | `hub-server-mid` | `pekoserver` | 2026-10-19T00:44:04.105+08:00 | Linux 5.15.0-177-generic |
| 4 | `public-server` | `VM-0-13-ubuntu` | 2026-10-19T00:44:05.587+08:00 | Linux 5.15.0-160-generic |
| 5 | `hub-server-final` | `pekoserver` | 2026-10-19T00:44:14.719+08:00 | Linux 5.15.0-177-generic |

## 文件

- `relay.json` —— 原始接力数据（含每站的 CN/UTC 时间戳、epoch、单调时钟、stamp_id）

## 说明

每一条时间戳都由**那一站自己的机器**生成并写入，中枢只负责排序与转发。
