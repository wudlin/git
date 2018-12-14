<pre>
<h1>初始化</h1>
git init															初始化
git config --global user.name "名字"	名字可以是中文但是不能和邮箱一样
git config --global user.email "      你的邮箱"
ssh-keygen -t rsa -C "你的邮箱地址" 	 生成公钥
ssh ~/							                  查看公钥目录(id_rsa.pub)

首次设置
git remote add origin "仓库下载地址"		添加远程仓库
git push -u origin master 						将本地仓库推送到远程仓库

git pull --rebase origin master				把远程库中的主干更新合并到本地库中
git pull --rebase origin 分支名				把远程库中分支的更新合并到本地库中
git clone "仓库下载地址"								克隆到本地工作区

<h1>常用设置</h1>
以上是第一次需要的操作，下面的是正常操作
git pull 												拉去远程仓库
git add . 											添加文件到工作区
git commit -m '提交更新日志' 		 添加文件到本地仓库
git push 												将本地仓库推送到远程仓库

git commit -am 									add与-m的简化
<h1>常用分支</h1>
git pull origin '分支名'					拉取远程分支到当前分支
git branch 											 查看本地所有分支 *为当前分支（-r远程分支）
git checkout -b '分支名'					新建/切换分支，并切换至分支上 （不加-b只是新建/切换）
git push origin '分支名'					将分支推送到远程仓库的分支上
分支相关
git merge '合并的其他分支名'				将当前分支和其他分支合并(本地仓库的内容进行合并)
git branch -d '删除的分支名'				删除本地分支
git push origin -d '删除的分支名'		删除远程分支

特性分支（合并）
例1.将b分支合并到a分支
git ckeckout b 
git pull --rebase
git commti -am 'b修改提交'
git checkout a
git commit -am 'a修改提交'
git rebase b 													这步的操作是创建一个特性分支，内容为a、b内容之和，有突出则修改
git commit -am '修改合并特性分支内容'		这步合并提交
git merge a 													将特性合并到a
git push origin a											将特性分支提交到a,此刻分支信息显示(a|REBASE 1/1)
git rebase --abort										停止重地位，回到正常分支（a）


其他命令
git log																查看所有版本号
git reset --mixed 版本号								回退某个版本，版本号可以缩短为前6位

git fetch																			拉取远程仓库分支跟新列表（git branch -r没找到远程仓库的分支前提下）
git branch --set-upstream-to=origin/分支名		设置分支跟踪信息

git commit --amend  							 进入编辑界面，输入(lo)进入插入状态，修改后按esc退出插入状态,输入(:wq)保存修改
git push --force origin 分支名  		非直推式，强制推送(替换远程仓库内容)
git branch -vv										查看设置的所有跟踪分支

git stash 							备份工作区
git stash pop						取出备份
git config -l						查看公钥设置信息

git log -p 文件名									查看单个文件所有修改记录
git checkout 哈希值 path/to/file		单文件还原

内部命令
--set-upstream-to 或 -u 		设置跟踪信息
--force 									非直推式合并
-b												新建并且切换，在创建分支命令checkout里不加-b表示切换
-d												删除	
--mixed				此为默认方式，不带任何参数的git reset，即时这种方式，它回退到某个版本，只保留源码，回退commit和add信息
 --soft				回退到某个版本，只回退了commit的信息。如果还要提交，直接commit即可
--hard				彻底回退到某个版本

Build:
Docs
Update
Fix:
New: 
Chore:
Upgrade:
</pre>
