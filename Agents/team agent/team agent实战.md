
# 安装与配置tmux

```
brew install tmux
```

# 配置文件
## tmux配置
- 
```
# chuan'jia增加如下配置

# 激活配置

tmux source-file ~/.tmux.conf
```


```

```
- 配置代理：其他详见[[cc安装与启动]]
- 
```
export https_proxy=http://127.0.0.1:7897
export http_proxy=http://127.0.0.1:7897
export CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1
claude --teammate-mode tmux
```

# 分屏模式（可选）
```
claude --teammate-mode in-process
claude --teammate-mode auto
claude --teammate-mode tmux
```

[https://szzdzhp.blog.csdn.net/article/details/157903022](https://szzdzhp.blog.csdn.net/article/details/157903022)

示例：

创建一个3人团队的AgentTeams.前端开发，后端开发，产品经理兼职UI设计，然后一个测试
具体需求是帮我创建一个专门用于分析Claude code Agent Teams 工作方式，沟通，协同的一个分析平台。用户只要启动这个平台，就能自动分析每个会话，里面是否使用了AgentTeams功能，以及看到每个团队工作的形式，主要还是要清晰的追踪到每个会话直接的交互链路，可以按照时间线展示，或者用各种可视化图谱展示。这样能够清晰的知道Agent teams 是如何完成任务的，你可以先试用 /brainstorming  skill来先确定任务，请一次性多问问题，不要一个问题问一次。


示例2

创建一个4人团队的AgentTeams.前端开发，后端开发，产品经理兼职UI设计，然后一个测试
具体需求: 
1.设计一个标注网站支持数据的标注，数据为文本数据，除了文本，还有其他一些描述信息，比如；ID，来源等等
2.标注内容为文本是否有效即可
你可以先试用 /brainstorming  skill来先确定任务，请一次性多问问题，不要一个问题问一次。


1.去掉上侧的数据集和标注按钮，让其仅在数据集列表的右侧展示；
2.为admin增加权限控制模块，可随时增加人员，并为人员赋予权限的功能
3.权限包括查看、标注、审核、分配权，admin默认所有权限都有，标注人员默认仅有查看、标注权限