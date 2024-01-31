## Git指令表

#### git config --global user.name "name"：配置git的名字

#### git config --global user.email "email name"：配置git的邮箱

#### mkdir \<directory name> : 创建一个目录（文件夹）

#### cd \<directory name>: 进入当前目录下的一个目录

#### pwd：查看当前目录的绝对路径

#### ls：查看当前目录下的目录以及文件

#### git init：将当前目录转为仓库

#### vi / vim \<file name>: 以vi / vim模式打开文件

#### cat \<file name>：查看文件内容

#### git add \<file name>：将文件保存到暂存区

#### git commit -m "message"：将文件全部提交并附加上本次修改的信息

#### git status：查看当前仓库文件的情况，看是否有修改后未保存到暂存区，未提交的文件

#### git diff：查看文件修改前后的差异

#### git log <--pretty=oneline>：查看日志（不加--pre...显示日志的完全体，加了只显示日志最重要的部分，将其放在同一行显示）

#### git reflog：查看从仓库建成到现今的所有日志

#### git reset --hard HEAD（版本）：重置到某个版本

#### git checkout -- \<file name>：将文件还原到最近的版本（修改后的文件未上传到暂存区时使用）

#### git reset HEAD \<file>：将文件还原到最近的版本（修改后的文件上传到了暂存区，但还未上传到版本库时使用）

#### 若修改后的文件上传到了版本库后想要修改的话就执行撤销操作

