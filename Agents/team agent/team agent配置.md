参考教程：[https://szzdzhp.blog.csdn.net/article/details/157903022](https://szzdzhp.blog.csdn.net/article/details/157903022)
# tmux配置
```
# 安装

brew install tmux

# 创建文件，增加如下配置


# 激活配置

tmux source-file ~/.tmux.conf
```
# 代理配置：其他详见[[cc安装与启动]]
```
export https_proxy=http://127.0.0.1:7897
export http_proxy=http://127.0.0.1:7897
```

# 多agent配置Claude配置
```
export CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1
claude --teammate-mode tmux
```
