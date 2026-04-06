参见：https://github.com/anomalyco/opencode

# 删除旧版 node
apt remove nodejs -y

# 安装 Node.js 20
curl -fsSL https://deb.nodesource.com/setup_20.x | bash -
apt install -y nodejs

npm i -g opencode-ai@latest
