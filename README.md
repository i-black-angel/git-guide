# 快速上手 git

## 安装

命令行执行安装命令:

```bash
sudo apt install -y git gitk
```

## 基本操作

### 全局配置

配置 git 提交时所使用的用户名与邮箱地址:

```bash
git config --global user.name "Your Name"
git config --global user.email "your@mail.com"
```

### 创建仓库

使用当前目录作为 git 仓库，初始化:

```bash
git init .
```

### 添加新文件

将当前目录下的所有文件添加到缓存区:

```bash
git add .
```

### 提交版本

将缓存区的文件提交到 git 仓库:

```bash
git commit -m 'init import'
```

如果不使用 `-m` 参数，会弹出编辑器让你写注释信息。

## 远程仓库

### 克隆

将远程服务器上的 git 仓库克隆到本地:

```bash
git clone https://gitee.com/iblackangel/git-guide.git
```

### 推送改动

好了，你的改动已经通过 `git add` 与 `git commit` 提交到本地仓库了，现在将本地仓库同步到远程仓库去:

```bash
git push origin master
```

可以将 *master* 换成你想要推送的其他分支。

### 获取更新

获取当前分支的远程更新内容到本地:

```bash
git pull
```

获取所有的远程更新（包括其他分支）到本地:

```bash
git pull --all
```

## 分支管理

### 新建分支

从当前分支创建新的分支 *dev*:

```bash
git checkout -b dev
```

### 查看分支

列出所有分支，包括当前分支及远程分支:

```bash
git branch -a
```

### 切换分支

从 *dev* 分支切换回 *master* 分支:

```bash
git checkout master
```

### 合并分支

将 *dev* 分支的改动合并到 *master* 分支:

```bash
git merge dev
```

或者在合并分支时让提交以线性的方式进行合并:

```bash
git rebase dev
```

### 删除分支

清理合并之后的分支:

```bash
git branch -d dev
```

清理还未合并的分支:

```bash
git branch -D <BranchName>
```

## 提交与修改

### 查看状态

不指定目录查看整个 git 仓库的工作区状态:

```bash
git status
```

查看当前目录的状态:

```bash
git status .
```

### 配置别名

用别名代替常用指令，简化指令操作:

```bash
git config --global alias.st status
```

后面即可使用别名来操作 `git st` 等效于 `git status`

### 删除文件

将文件/目录从暂存区和工作区删除:

```bash
git rm -r <file>
```

### 移出版本控制

将文件/目录从暂存区移除，不再参与 git 版本控制:

```bash
git rm -r --cached <file>
```

### 撤销修改

撤销当前工作区的修改:

```bash
git restore .
```

### 查看日志

查看历史提交记录

```bash
git log
```

### 版本回退

回退到指定版本，工作区文件内容保持不变:

```bash
git reset f5dccef
```

回退某个文件的版本到上一个版本:

```bash
git reset HEAD^ hello.cpp
```

## 参考网站

[1] [Git 教程](https://www.runoob.com/git/git-tutorial.html)
