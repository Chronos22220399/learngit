# Git 常见问题

## 使用多个远程仓库时

1. 一个 ssh 密钥对只能对应一个远程仓库，当 ssh 密钥对被使用了之后想要使用 ssh 传输文件，需要重新创建一个 ssh 密钥对

2. 当使用第 2 个 ssh 密钥对进行推送文件时，系统只会使用默认的（第一个） ssh 密钥对，此时的 push 操作会失败，但是可以正常 pull，要想避免这种状况，对代理添加<font color = red>标识</font>，使用 `ssh-add ~/.ssh/ssh_key` 指令可以为代理添加标识(identities)，此时再 push 就能推送成功了

   另外，使用 `ssh-add -l` 可以查看代理情况，若是 `The agent has no identities.` 则表明此时需要为代理添加标识，此时就需要使用 2 所述的指令了