#  Git文件状态

## Git中文件的三种状态：
committed（已提交） ： 表示该 文件已经被安全地保存在本地数据库中了
modified（已修改）： 表示修改了某个文件，但还没有提交保 存
staged （已暂存）： 表示把已修改的文件放在下次提交时要保存的清单中  

## Git基本工作流程

在工作目录中修改某些文件

保存到暂存区域

提交更新，转储到 git 目录中  

## 初次运行Git前的配置  

1、配置用户信息

2、设置文本编辑器 

3、设置差异分析工具  

## Git常用命令  

（1） 创建git仓库

从现有目录创建：切换到现有目录， git init
从现有仓库创建： git clone [url网址]

（2） 检查文件状态：git status
（3）添加文件到暂存区域
git add 文件名
git add -A :提交所有文件到暂存区域

（4）提交文件到git目录
将暂存区域提交： git commit -m “文件说明”

（5）移除文件
git rm 文件名
git rm -f 文件名 ：删除暂存区的文件
（6）比较文件修改的差异
git diff
（7）移动文件或者重命名文件
git mv origin_filename rename_filename
（8）查看提交历史
git log
（9）回退到以前的版本
git reset –hard 版本号
（10）添加远程库
1）创建 SSH key: ssh-keygen –t rsa –C “Your Email”

2）查看.ssh目录，找到id_rsa和id_rsa.pub两个文件

3）登录GitHub账户，输入id_rsa.pub公钥
4）测试是否成功 ssh -T git@github.com
5）在github上创建一个与本地仓库同名的空仓库
6）运行命令： git remote add origin git@github.com:用户名/learngit.git
origin可修改成其他名字
7） git push -u origin master： 推送到远程仓库  

（11）删除远程库
git remote rm 项目仓库名称  

（12）从远程库克隆
git clone 项目仓库地址  

## Git的分支管理  

Git 中的分支，其实本质上仅仅是个指向 commit 对
象的可变指针  

### 创建与合并分支  

（1）查看分支
git branch
（2）创建分支
git branch 分支名  

（3）切换分支
git checkout 分支名  

（4）创建+切换分支
git checkout -b 分支名
（5）合并某分支到当前分支
git merge 分支名
git merge --no -ff 分支名
（6）删除分支
git branch -d 分支名  

### 冲突管理和远程分支  

冲突管理：手动打开冲突文件，留下自己需要的内容，再次提交文件
推送远程分支： git push origin 分支名称
在本地创建和远程分支对应的分支： git checkout –b 分支名称 origin/分支名称
建立本地分支和远程分支关联： git branch --set-upstream-to origin/分支名称 分支名称
抓取远程分支的更新与本地分支合并： git pull <远程主机名> <远程分支名>:<本地分支名>

## 忽略特殊文件  

• 创建并编写.gitignore文件：输入你想忽略的文件,例如： .obj、 .tmp
• 将.gitignore文件提交到git  

# GitHub  

## GitHub基本概念   

1、 Repository（仓库）： 用来存放你的项目代码，每个项目对应一
个仓库。
2、 Star（收藏） ：即收藏别人的项目，方便查看
3、 Fork: 复制克隆项目，与所克隆的项目是独立存在的
4、 Pull Request：发起请求，等待原项目负责人查看，考虑是否合
并到源仓库中
5、 Watch：如果你watch了一个项目，如果以后这个项
目有更新时可及时接收到通知。
6、 Issue:发现代码有Bug时，向项目负责人提提案，讨
论解决问题
7、 gist:用来粘贴数据（代码）  

## 开源项目贡献流程  

1、 通过新建Issue提交使用问题或者建议给作者
2、 通过Pull Request
Fork 作者项目
对项目进行修改并提交Pull Request
等待作者审核  

## 团队合作开发项目  

1、通过 Collaborators  

2、 Fork & Pull Request
1） Fork别人的项目到自己仓库
2）将项目clone到本地进行修改，并更新到远程仓库
3）向项目作者提Pull Request
4）作者merge合并项目  