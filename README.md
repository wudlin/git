<h1 align="center">git命令说明</h1>

## 目录

- [初始化](#初始化)
- [首次设置](#首次设置)
- [常用设置](#常用设置)
- [常用分支](#常用分支)
- [合并分支相关](#合并分支相关)
- [其他命令](#其他命令)
- [修饰符](#修饰符)
- [对比 svn 流程整合](#对比-svn-流程整合)

## 初始化

<a href="https://git-scm.com/downloads" target='_blank'>git 官方下载地址</a>

<table>
<tr>
<td>git init</td>
<td>初始化</td>
</tr>
<tr>
<td>git config --global user.name "名字"</td>
<td>名字可以是中文但是不能和邮箱一样</td>
</tr>
<tr>
<td>git config --global user.email "邮箱"</td>
<td>你的邮箱</td>
</tr>
<tr>
<td>ssh-keygen -t rsa -C "你的邮箱地址"</td>
<td>生成公钥</td>
</tr>
<tr>
<td>ssh ~/</td>
<td>查看公钥目录(id_rsa.pub</td>
</tr>
<tr>
<td>git config --global core.ignorecase false</td>
<td>全局设置区分大小写，针对 Windows  系统</td>
</tr>
</table>

<br>

## 首次设置

> Note:新建文件夹 `git init` 后，目录下会生成 `.git` 隐藏文件相当于本地仓库作用

<table>
<tr>
<td>git remote add origin "仓库下载地址"</td>
<td>添加远程仓库</td>
</tr>
<tr>
<td>git push -u origin master</td>
<td>将本地仓库的主干推送到远程仓库上，如果远程仓库上有内容，则先执行 pull 拉取的操作</td>
</tr>
<tr>
<td>git pull --rebase origin master</td>
<td>把远程库中的主干更新合并到本地库中</td>
</tr>
<tr>
<td>git pull --rebase origin 分支名</td>
<td>把远程库中分支的更新合并到本地库中</td>
</tr>
<tr>
<td>git clone "仓库下载地址"</td>
<td>克隆到本地工作区</td>
</tr>
</table>
								
## 常用设置

> Note：以上是第一次需要的操作，下面的是正常操作

<table>
<tr>
<td>git pull</td>
<td>拉去远程仓库</td>
</tr>
<tr>
<td>git add .</td>
<td>添加文件到工作区</td>
</tr>
<tr>
<td>git commit -m '提交更新日志'</td>
<td>添加文件到本地仓库</td>
</tr>
<tr>
<td>git push</td>
<td>将本地仓库推送到远程仓库</td>
</tr>
<tr>
<td>git commit -am</td>
<td>add与-m的简化</td>
</tr>
</table>
							
## 常用分支
<table>
<tr>
<td>git pull origin '分支名'</td>
<td>拉取远程分支到当前分支</td>
</tr>
<tr>
<td>git branch</td>
<td>查看本地所有分支 *为当前分支（-r远程分支）</td>
</tr>
<tr>
<td>git checkout -b '分支名'</td>
<td>新建/切换分支，并切换至分支上 （不加-b只是新建/切换）</td>
</tr>
<tr>
<td>git push origin '分支名'</td>
<td>将分支推送到远程仓库的分支上</td>
</tr>
<tr>
<td>git fetch</td>
<td>拉取远程仓库分支跟新列表（git branch -r 没找到远程仓库的分支前提下）</td>
</tr>
</table>
					
## 合并分支相关

> Demo1：将 `a分支` 合并到 `b分支` ，首先切换到 `a分支` ，将代码拉取并提交到 `a本地仓库` ，这里不进行 `git push` ，然后切换到 `b分支` 进行相同操作，然后执行 `git merge b` ，就能起到合并 `a分支` 作用

这里是将两个本地仓库带代码进行合并

> Demo2：将 `a分支` 合并到 `b分支` ，首先切换到 `b分支` ，将代码拉取并提交到 `b本地仓库` ，这里不进行 `git push` ，然后执行 `git pull origin a` ，就能起到合并 `a分支` 作用

这里是将 `远程仓库a` 的内容直接拉取到 `b工作区` 然后 `commit` 后进行推送

<table>
<tr>
<td>git merge '合并的其他分支名'</td>
<td>将当前分支和其他分支合并(本地仓库的内容进行合并)</td>
</tr>
<tr>
<td>git branch -d '删除的分支名'</td>
<td>删除本地分支</td>
</tr>
<tr>
<td>git push origin -d '删除的分支名'</td>
<td>删除远程分支</td>
</tr>
</table>

## 其他命令

<table>
<tr>
<td>git log</td>
<td>查看所有版本号</td>
</tr>
<tr>
<td>git reset --hard 版本号</td>
<td>回退某个版本，版本号可以缩短为前 6 位</td>
</tr>
<tr>
<td>git branch --set-upstream-to=origin/分支名</td>
<td>设置分支跟踪信息</td>
</tr>
</table>

<table>
<tr>
<td>git commit --amend</td>
<td>进入编辑界面，输入(lo)进入插入状态，修改后按 esc 退出插入状态,输入(:wq)保存修改</td>
</tr>
<tr>
<td>git push --force origin 分支名</td>
<td>非直推式，强制推送(替换远程仓库内容)</td>
</tr>
<tr>
<td>git branch -vv</td>
<td>查看设置的所有跟踪分支</td>
</tr>
</table>

<table>
<tr>
<td>git stash</td>
<td>备份工作区</td>
</tr>
<tr>
<td>git stash pop</td>
<td>取出备份</td>
</tr>
<tr>
<td>git config -l</td>
<td>查看公钥设置信息</td>
</tr>
</table>
 
<table>
<tr>
<td>git log -p 文件名</td>
<td>查看单个文件所有修改记录</td>
</tr>
<tr>
<td>git checkout 哈希值 path/to/file </td>
<td>单文件还原</td>
</tr>
<tr>
<td>git rm --cached 文件名 -r</td>
<td>删除暂存区上的文件， --cached 表示保留工作区的文件，不加会删除工作区文件</td>
</tr>
</table>

## 修饰符

<table>
<tr>
<td>--set-upstream-to 或 -u</td>
<td>设置跟踪信息</td>
</tr>
<tr>
<td>--force</td>
<td>非直推式合并</td>
</tr>
<tr>
<td>-b</td>
<td>新建并且切换，在创建分支命令 checkout 里不加-b 表示切换</td>
</tr>
<tr>
<td>-d</td>
<td>删除</td>
</tr>
<tr>
<td>--mixed</td>
<td>此为默认方式，不带任何参数的 git reset，即时这种方式，它回退到某个版本，只保留源码，回退 commit 和 add 信息</td>
</tr>
<tr>
<td>--soft</td>
<td>回退到某个版本，只回退了 commit 的信息。如果还要提交，直接 commit 即可</td>
</tr>
<tr>
<td>--hard</td>
<td>彻底回退到某个版本</td>
</tr>
</table>

<table>
<tr>
<td>--hard</td>
<td>彻底回退到某个版本</td>
</tr>
</table>

## 对比 svn 流程整合

<img src="https://github.com/wudlin/git/blob/master/img/git%E5%AF%B9%E6%AF%94svn.jpg?width=890">

- Note:关于 `commit` 提交规范，未整理完成
- [Build]
- [docs]
- [Fix]
- [new]
- [Chore]
- [upgrade]

<a href="http://note.youdao.com/noteshare?id=e176d987566e724739ff48ed0b977e26" target="_blank">内容文本</a>
