## Bug分支

**由于转换分支前需要提交更改，否则不会报错，所以在面对一个模块写了一半时突然发现前面的一个模块有bug，这是需要去修改，否则会导致后续工作无法正常进行，而当前模块只写了一半，此时提交只能提交半成品，会使得版本库的版本变复杂且不符合设计理念，所以这时需要使用stash功能“储藏”现在的工作现场，等以后在恢复了**

`git stash`

当使用了这个语句后，在使用`git status`语句会发现工作区是干净的，因为stash语句将工作区的内容藏（存储）起来了，这样就能放心的创建分支修改bug了



#### 查看存储的列表

`git stash list`



#### 恢复存储的内容

1. `git stash apply stash@{number}`

   通过这种方式恢复，其stash内容并不会删除，要删除则需使用

   `git stash drop stash@{number}`

2. `git stash pop stash@{number}`

   通过这种方式恢复，stash内容也会删除掉（因为是从stash中弹出）



#### 复制一次commit上的更改

`git cherry-pick <commit>`

