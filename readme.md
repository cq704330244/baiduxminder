百度脑图

准备工作
计算机环境准备，必备软件：node,npm,git,浏览器
全局npm包准备，必备模块：grunt, bower
部署环境：静态web服务器（Apache,tomcat,node server,nginx等）

搭建过程
# 进入D盘
$ cd /d
# 创建baidunaotu文件夹，并进入该文件夹
$ mkdir baidunaotu && cd baidunaotu
# 克隆项目
$ git clone https://github.com/fex-team/kityminder.git
# 等待项目克隆完成......
# 进入项目目录
$ cd kityminder
# 初始化子模块
$ git submodule init
$ git submodule update

# 安装项目的依赖
$ npm install
$ bower install
# 等待项目的依赖安装完成......
# 执行编译
$ grunt
# 等待编译结果......
# 这时可以发现在该目录中多了一个文件夹dist
# dist文件夹中就是可以运行的百度脑图

# 进入上一级目录，并创建文件夹naotu
$ cd ../ && mkdir naotu
# 将kityminder中的dist文件夹拷贝到naotu文件夹下
$ cp -r kityminder/dist naotu/
# 进入naotu目录
$ cd naotu
# 初始化可运行的脑图项目
$ npm init -y
# 安装express
$ npm install --save express
# 创建node服务器文件
$ touch server.js
# 编辑server.js文件
$ vim server.js
# ......编辑中......
# server.js文件内容看下面
# 编辑完成
# 执行server.js脚本，开启web服务器
$ node server.js
# 在浏览器中打开项目：localhost:3000