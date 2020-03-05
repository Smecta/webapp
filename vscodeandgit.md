#VSCode下Git与Github同步

##预先准备
+ 安装vscode
+ 安装git
+ 注册GitHub账号
+ 创建一个GitHub项目

##设置Git

+ code 主菜单-终端-新建终端，打开命令行
+ ```git init``` 初始化git,执行后会新增.git隐藏文件夹，里面记录git的配置信息文件
+ 删除git配置文件，用```rm -rf .git ```命令或手工直接删除文件夹即可
+ ```git config --global user.name "ch"``` 配置全局用户名
+ ```git config --global user.email "12345@gmail.com"``` 配置全局邮箱

##关联Github项目

+ ```git remote add origin https://github用户名:github登录密码@github.com/github用户名/项目名称.git```,设置git的远程地址
+ 修改命令为 ```git remote set-url origin https://github用户名:github登录密码@github.com/github用户名/项目名称.git ```
+ 删除设置使用```git remote remove origin```,或者手工修改.git/config文件
+ 拉取远程项目（从GitHub复制到本地），使用命令git pull origin master

##将修改内容推送到GitHub

+ 先推到本地git，方法是直接在左侧源代码管理面板输入任意记录，然后ctrl+回车提交
+ 再推送到远程GitHub，方法是同样从左侧源代码管理面板的菜单-推送到...



## 更新（最新流程）
+ 本地：安装git 
+ 打开要同步的目录
+ ```git init``` 初始化整个项目
+ ```git config --global user.name "Smecta"``` 配置全局用户名
+ ```git config --global user.email "chchengeng@gmail.com"``` 配置全局邮箱
+ 生成本机ssh-key ```ssh-keygen``` 直接敲回车默认就可以，直到生成key复制使用
+ ```cat ~/.ssh/id_rsa.pub``` 查看本机已生成的key
+ 去github上，设置里面找到settings-SSH and GPG keys - new SSH key 添加即可
+ 本地：```git add .``` .是代表添加全部
+ ```git commit -am "初始化"``` ""引号包含的是提交的名字或者是原因
+ ```git remote add origin git@github.com:Smecta/django-web.git``` 其中 origin 是源头，大家都这么起名，可以是任何名称 后面代表的github上该仓库的ssh连接
+ 如果出现fatal: remote origin already exists. 代表已存在origin 删除即可 ```git remote rm origin``` 再次提交即可
+ ```git push -u origin master``` 推送到github上

## git 从远程拉取代码、推代码的步骤
### 如果是几个人共同管理项目，并且你的队友在你之前推过代码，那你就需要 git pull 一下，把代码拉到本地，解决一下冲突，再执行以下步骤，将本地代码推到远程仓库。

+ 第一步：查看当前的git仓库状态，可以使用git status。

  ```git status```
+ 第二步：把更新的代码添加到暂存区。

  ```git add *```
+ 第三步：将暂存区的更新提交到仓库区。

  ```git commit -m "更新说明" ```（更新说明，是本次推送代码的标识，写什么都可以，只要自己看得懂）
+ 第四步：先git pull,拉取远程仓库所有分支更新并合并到本地。

  ```git pull```
+ 第五步：将本地分支的更新全部推送到远程仓库。

  ```git push origin master```
+ 第六步：再次使用```git status```查看当前的git仓库状态，已经没有改动，证明更新成功
