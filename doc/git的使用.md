# git的使用

## 1.git的安装

 使用库安装：

sudo apt update

sudo apt-get install git

测试:git  --version

## 2.git概念和工作流程

![image-20211124172552854](image-20211124172552854.png)

概念：

工作区：就是你在电脑里能看到的目录。
暂存区：英文叫 stage 或 index。一般存放在 .git 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
版本库：工作区有一个隐藏目录 .git，这个不算工作区，而是 Git 的版本库。

![image-20211124173559532](image-20211124173559532.png)

![image-20211128161622676](image-20211128161622676.png)

## 3.git常用命令

1）git项目创建

新建一个目录，在此目录下执行：git  init

执行后，会创建一个隐藏的.git目录：

![image-20211124173110025](image-20211124173110025.png)

2)add

<img src="image-20211128162900843.png" alt="image-20211128162900843" style="zoom:50%;" />

3)commit

提交文件到本地库。

提交所有在staging area中的文件到registory：

git commit -m [message]

message是提交时的备注。

<img src="image-20211128163342259.png" alt="image-20211128163342259" style="zoom:50%;" />

<img src="image-20211128163938882.png" alt="image-20211128163938882" style="zoom:50%;" />

4)push

上传远程代码到远程仓库并合并。

前提：远程有仓库。

![image-20211128170001044](image-20211128170001044.png)

url栏里就是远程仓库地址。

先添加远程仓库：

git remote add 别名  远程仓库url

![image-20211128170714459](image-20211128170714459.png)

错误的原因是没有指定远程的branch，需要指定为master。

注意：github页面上将master分支名改成了“main”，但push时还是需要用master，master对应web页面上的main。

<img src="image-20211128170745587.png" alt="image-20211128170745587" style="zoom:50%;" />

push时命令正确，认证失败：

![image-20211128171430603](image-20211128171430603.png)

获取token的方法：

![image-20211128171708114](image-20211128171708114.png)

点击右上角代表自己的图标，选择settings：

<img src="image-20211128171839652.png" alt="image-20211128171839652" style="zoom:50%;" />

选Developer settings：

![image-20211128171929633](image-20211128171929633.png)

选择Personal access tokens:

![image-20211128172032683](image-20211128172032683.png)

点击右侧的蓝色![image-20211128172111620](image-20211128172111620.png)

在页面上填写相关信息后：

![image-20211128172420880](image-20211128172420880.png)

点击Generate token:

![image-20211128172753558](image-20211128172753558.png)

关闭页面之前，需要把token拷贝出来，以后当成密码使用：

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

再次push：

![image-20211128173114028](image-20211128173114028.png)

passeord需要输入token。

5)clone

将远程仓库clone到本地：

git clone 远程仓库url

clone后操作步骤：

（1）修改文件（project正常进程）

（2）add

（3）commit

（4）远程同步：

分支问题：从本地开始创建的项目，主分支是master；从远程开始，主分支是main。

a）添加远程仓库：

git remote add 别名  远程仓库url

![image-20211201164711957](image-20211201164711957.png)

注意：password不能输入github的用户密码，而要输入token。

6)diff

查看工作区文件和staging area文件的区别。

7）查看提交历史log

8）恢复reset

git reset --hard HEAD^1

回退到上一个版本，--hard 将直接修改工作区文件内容。

### 4.在scode中使用git

1）用命令行进行git初始化

在scode打开项目之前，已经执行了：git init，git  add

在此目录下打开，可以直接用scode的版本管理。

2）用scode进行git初始化
