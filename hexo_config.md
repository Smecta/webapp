
hexo 博客


# 环境安装
 git 主要用于上传博客页面到github 和命令操作

node 

npm

npm i -g hexo-cli

安装完成

# 生成本地博客
hexo init myblog
初始化myblog

cd myblog 
使用 npm i  进行安装所需依赖

npm i hexo-deployer-git --save
此模块用于将hexo本地博客上传到github页面必须

npm i hexo-server --save

安装hexo服务器模块，用于本地预览博客
搭建完毕，运行查看
hexo s 
是 hexo server 简写形式 启动本地服务

# 将本地博客上传到github
仓库名称如下：
yourname.github.io

注：yourname填写你的账户名

修改_config.yml文件
找到_config.yml文件，鼠标拉到最下面，修改成：
deploy:
  type: git
  repo: https://github.com/yourname/yourname.github.io.git
注：两处yourname都需要填写你的账户名
部署本地博客到github
生成静态页面
hexo g
这条命令是代码hexo generator的缩写，生成好之后，继续输入
hexo d
这条命令是代码hexo deploy的缩写，用于将生成的静态文件上传到github，等待完成之后在浏览器输入yourname.github.io就可以看到你的博客页面了
注意：首次使用git会询问github的账号信息，填写你对应的账户信息即可
