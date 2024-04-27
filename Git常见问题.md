# Git 常见问题

## 使用多个远程仓库时

1. 一个 ssh 密钥对只能对应一个远程仓库，当 ssh 密钥对被使用了之后想要使用 ssh 传输文件，需要重新创建一个 ssh 密钥对

2. 当使用第 2 个 ssh 密钥对进行推送文件时，系统只会使用默认的（第一个） ssh 密钥对，此时的 push 操作会失败，但是可以正常 pull，要想避免这种状况，对代理添加<font color = red>标识</font>，使用 `ssh-add ~/.ssh/ssh_key` 指令可以为代理添加标识(identities)，此时再 push 就能推送成功了

   另外，使用 `ssh-add -l` 可以查看代理情况，若是 `The agent has no identities.` 则表明此时需要为代理添加标识，此时就需要使用 2 所述的指令了



## git push 推送失败时

### 情况1: 本地与远程出现冲突

例如：

```bash
wuming@wumingdeMacBook-Air AlgorithmDesignandAnalysisExperiment % git push
To github.com:AnankeKS/AlgorithmDesignandAnalysisExperiment.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'github.com:AnankeKS/AlgorithmDesignandAnalysisExperiment.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
wuming@wumingdeMacBook-Air AlgorithmDesignandAnalysisExperiment % 
```

在这种情况下不能直接拉取，因为系统也不知道怎么处理拉取后产生的冲突，这和下面所说的 `git pull` 拉取失败的情况 1 是一样的

我们需要选取合适的选项让系统知道如何处理冲突，拉取完毕后再推送

## git pull 拉取失败时

在这种情况下，系统会给我们三个选项让我们重新 pull

1. git config pull.rebase false	#merge

   这就是指令 `git pull --rebase=false / git pull`，表示不变基，直接合并（合并是系统创建一个新的分支，然后将本地分支和远程分支合并到新的分支上，在合并过程中，系统能改则自己该，不能改则用户手动改，改完后就会创建新的提交，提交完后这个分支就会作为原本的本地分支存在，此时再 push 就能成功了）

2. git config pull.rebase true    #rebase

   这就是指令 `git pull --rebase=true`，表示变基（这会将本地的修改先恢复到修改之前，然后将远程分支嫁接上去，然后将本地的修改一步步填充上去，遇到冲突时能合并的内容系统直接合并，不能直接合并的交给我们来该。这样做的缺点是合并后的本地分支原本的提交会被本次变基后的提交覆盖掉）

> 合并和变基的区别在与：合并会将新的提交放在本地分支原本的最新提交之后，也就是说它不会覆盖原本的记录；
>
> 而变基提交会覆盖原本的最新提交的记录，这就像它的名字一样，将“基础”变掉，这个新的变基提交的内容就是变成的部分。