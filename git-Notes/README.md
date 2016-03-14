创建本地仓库
git init 

添加到暂存区
git add <filename>
git add *

git commit -m "代码提交信息"

将你的仓库连接到某个远程服务器
git remote add origin <server>

将改动提交到远程仓库
git push origin master

------------
分支创建
创建一个叫做“feature_x”的分支，并切换过去：
git checkout -b feature_x
切换回主分支：
git checkout master
再把新建的分支删掉：
git branch -d feature_x
除非你将分支推送到远端仓库，不然该分支就是 不为他人所见的：
git push origin <branch>

更新与合并
要更新你的本地仓库至最新改动，执行：
git pull <remote> <branch>
以在你的工作目录中 获取（fetch） 并 合并（merge） 远端的改动。
要合并其他分支到你的当前分支（例如 master），执行：
git merge <branch>

间接合并方式：git checkout test README.txt 【把test分支的文件 更新到当前分支上】
然后在git commit -m"修改文件"

在这两种情况下，git 都会尝试去自动合并改动。遗憾的是，这可能并非每次都成功，并可能出现冲突（conflicts）。 这时候就需要你修改这些文件来手动合并这些冲突（conflicts）。改完之后，你需要执行如下命令以将它们标记为合并成功：
git add <filename>
在合并改动之前，你可以使用如下命令预览差异：
git diff <source_branch> <target_branch>

标签
为软件发布创建标签是推荐的。这个概念早已存在，在 SVN 中也有。你可以执行如下命令创建一个叫做 1.0.0 的标签：
git tag 1.0.0 1b2e1d63ff
1b2e1d63ff 是你想要标记的提交 ID 的前 10 位字符。可以使用下列命令获取提交 ID：
git log
你也可以使用少一点的提交 ID 前几位，只要它的指向具有唯一性。


替换本地改动
假如你操作失误（当然，这最好永远不要发生），你可以使用如下命令替换掉本地改动：
git checkout -- <filename>
此命令会使用 HEAD 中的最新内容替换掉你的工作目录中的文件。已添加到暂存区的改动以及新文件都不会受到影响。

假如你想丢弃你在本地的所有改动与提交，可以到服务器上获取最新的版本历史，并将你本地主分支指向它：
git fetch origin
git reset --hard origin/master

查看仓库信息
git remote show origin 
git push origin test:master         // 提交本地test分支作为远程的master分支
git push origin test:test              // 提交本地test分支作为远程的test分支

拉取
当 git fetch 命令从服务器上抓取本地没有的数据时，它并不会修改工作目录中的内容。 它只会获取数据然后让你自己合并。 然而，有一个命令叫作 git pull 在大多数情况下它的含义是一个 git fetch 紧接着一个 git merge 命令。 
由于 git pull 的魔法经常令人困惑所以通常单独显式地使用 fetch 与 merge 命令会更好一些。

删除远程分支
 可以运行带有 --delete 选项的 git push命令来删除一个远程分支。 如果想要从服务器上删除 serverfix 分支，运行下面的命令：
$ git push origin --delete serverfix

查看分支的信息
git branch -v

rebase使用 
http://wiki.sankuai.com/pages/viewpage.action?pageId=145064463

### 参考资料
* [Git 常用命令详解](http://blog.csdn.net/sunboy_2050/article/details/7529022)
* <https://git-scm.com/book/zh/v2>
* [Git - 简易指南](http://rogerdudler.github.io/git-guide/index.zh.html)
* [Git-Cheat-Sheet](https://github.com/flyhigher139/Git-Cheat-Sheet) （感谢 @flyhigher139 翻译了中文版）
* [Git Community Book 中文版](http://gitbook.liuhui998.com)
* [git-flow 备忘清单](http://danielkummer.github.io/git-flow-cheatsheet/index.zh_CN.html)
* [Git 参考手册](http://gitref.justjavac.com)
* [Github帮助文档](https://github.com/waylau/github-help)
* [GitHub秘籍](https://snowdream86.gitbooks.io/github-cheat-sheet/content/zh/)
* [Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000) （本文由 [@廖雪峰](http://weibo.com/liaoxuefeng) 创作，如果觉得本教程对您有帮助，可以去 [iTunes](https://itunes.apple.com/cn/app/git-jiao-cheng/id876420437) 购买）
* [Got GitHub](https://github.com/gotgit/gotgithub)
* [GotGitHub](http://www.worldhello.net/gotgithub/index.html)
* [HgInit (中文版)](http://bucunzai.net/hginit/)
* [Mercurial 使用教程](https://www.mercurial-scm.org/wiki/ChineseTutorial)
* [Pro Git](https://git-scm.com/book/zh/v2)
* [Pro Git 中文版](https://www.gitbook.com/book/0532/progit/details) (整理在gitbook上)
* [svn 手册](http://svnbook.red-bean.com/nightly/zh/index.html)
* [学习 Git 分支](http://pcottle.github.io/learnGitBranching/) (点击右下角按钮可切换至简体及正体中文)
* [沉浸式学 Git](http://igit.linuxtoy.org/index.html)
* [猴子都能懂的GIT入门](http://backlogtool.com/git-guide/cn/)