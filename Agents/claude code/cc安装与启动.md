# Claude Code 安装与启动

由于网络原因，直接运行 `claude` 可能无法连接，需要先设置代理才能正常启动。

## Mac

```bash
export https_proxy=http://127.0.0.1:7897
export http_proxy=http://127.0.0.1:7897
claude
```

## Linux

```bash
export https_proxy=http://127.0.0.1:7897
export http_proxy=http://127.0.0.1:7897
claude
```

## Windows (PowerShell)

```powershell
$env:http_proxy="http://127.0.0.1:1080"
$env:https_proxy="http://127.0.0.1:1080"
claude
```

---

**说明**：文档中列出了两个常见的代理端口 **7897** 和 **1080**，对应不同代理软件（如 Clash、V2Ray 等）的默认端口。
