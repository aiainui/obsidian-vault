# xint 安装教程

> X Intelligence CLI - X/Twitter 搜索工具

## 获取 X API Key

1. 访问 https://developer.x.com
2. 创建开发者账号（如没有）
3. 创建 Project 和 App
4. 获取 Bearer Token (X_BEARER_TOKEN)

## 环境变量配置

在 `~/.zshrc` 或 `~/.bashrc` 中添加：

```bash
export X_BEARER_TOKEN="你的Bearer Token"
```

## 安装 xint

```bash
# 方法1: curl 安装
curl -fsSL https://raw.githubusercontent.com/0xNyk/xint/main/install.sh | bash

# 方法2: Homebrew
brew tap 0xNyk/xint
brew install xint

# 方法3: 手动安装
git clone https://github.com/0xNyk/xint.git
cd xint
bun install
```

## 使用方法

```bash
# 搜索 AI 相关推文
xint search "AI" --limit 10

# 查看趋势
xint trends

# 分析情感
xint analyze "AI news"
```

## 参考链接

- 官网: https://github.com/0xNyk/xint
- X 开发者平台: https://developer.x.com
