### Git配置名字和仓库

#### 配置名字

`git config --global user.name "your name"`



#### 配置邮箱

 ` git config --global user.email "yourEmail"`

此处的--global表示本电脑上所有的仓库都使用这个配置，可以不要（这样表示只有本仓库这样配置）





### Git创建版本库

#### 创建目录

`mkdir <directory name>`



#### 进入目录

`cd <directory name>`

<strong> 注意： </strong>cd只能进入目录，不能用于打开文件



#### 将目录改成仓库

` git init`



#### 查看当前目录所在位置

`pwd`

<strong>pwd的全称为“print working directory”</strong>



#### 常看当前目录存在的文件、目录

`ls`

<strong>ls 的全称为 “list“ </strong>



#### 以vim模式打开文件

`vim <file name>`

<strong>当文件不存在时会创造文件然后再以vim模式打开</strong>



#### 将文件添加到暂存区中

`git add <file name>`

#### 将所有更改添加到暂存区

git add .



#### 将暂存区的更改提交到本地仓库

```git bash
git commit -m "说明"   	// 将暂存区的更改提交到本地仓库并附上修改

git commit 				 // 将暂存区的更改提交到本地仓库（-m "说明" 是用来附加修改的）
```







