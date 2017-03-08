---
title: Hexo+github搭建个人博客
date: 2017-03-08 18:28:57
tags:
---
作为一名小白，大神请自行飘过。

hexo是一款基于Node.js的静态博客框架，和github一起联合使用。确实很不错的一个博客系统。

接触到hexo还是我的一位大神朋友介绍给我的，还把她Mac的配置给了我一份，但在windows上做配置确实遇到了好多坑。

###配置环境
- Node.js.如果没有`node.js`环境，请自行安装->[https://nodejs.org/en/](https://nodejs.org/en/ "Nodejs官方网站")

- Git.

- Github账号

- Gitbash或者sourceTree（Git客户端管理工具，或者其他更好的管理工具）

###配置Github
- 建立repository:
	- 建立与你用户名对应的仓库，仓库名必须`your_user_name.github.io`固定写法



- 将仓库通过Git拉取到本地文件夹 如blog

###安装Hexo
在拉取的仓库目录blog安装Hexo

- 安装Hexo:
	- `sudo npm install -g hexo`


- 初始化Hexo:
	- `hexo init`

至此，安装工作全部完成。blog就是你博客的根目录，所有的操作都是在这个文件夹中完成


-  生成静态页面：
	-  `hexo generate`或者`hexo g`

- 启动本地服务，进行文章博客预览调试：
	- `hexo server` 浏览器中输入[http://localhost:4000](http://localhost:4000 "localhost:4000")
	
###建立关联
在blog本地目录下，找到`_config.yml`文件</br>
*注意此处在windows下修改_config.yml文件不能直接找到文件使用notepad++等软件直接修改，需要在Git客户端中vi修改，Mac直接在终端修改即可*
	
- 修改**public_dir**为**./**

- 修改**deploy**为：</br>
	 `deploy:type: git repo: https://github.com/Aaronshuai/Aaronshuai.github.io branch: master`
    Site下可自行设置（博客的title、描述、作者等等）</br>
	`url: https://Aaronshuai.github.io`</br>

- 执行命令`npm install hexo-deployer-git --save`

- 执行命令`hexo deploy`

**浏览器中输入https://Aaronshuai.github.io即可**

###修改主题
- 选择主题，git clone到本地</br>
	这里有大量的主题列表[https://github.com/hexojs/hexo/wiki/Themes](https://github.com/hexojs/hexo/wiki/Themes "主题list") </br>
	大家选择自己喜欢的主题进行下载比如我下载的这个主题</br>	TKL - A responsive design theme for Hexo. 一个设计优雅的响应式主题

- 将主题代码复制到`blog/theme/`文件夹下

- 修改blog目录下的*_config.yml*文件：
	- `theme: TKL`

###修改主题内容
进入到blog/theme/TKL/路径下</br>
修改当前路径下的`_config.yml`,修改文案，图片，第三方连接等等

###修改部署：</br>1.更新本地静态页面</br>2.将deploy目录部署到github

- 更新`hexo g`

- 提交`hexo d`

常用的命令</br>hexo new”postName” #新建文章

hexo new page”pageName” #新建页面

hexo generate #生成静态页面至public目录

hexo server #开启预览访问端口（默认端口4000，’ctrl + c’关闭server）

hexo deploy #将.deploy目录部署到GitHub
本文的参考：[https://zhaixiaoou.github.io/2016/12/12/Hexo-github-搭建个人博客](https://zhaixiaoou.github.io/2016/12/12/Hexo-github-搭建个人博客 "翟晓鸥")</br>[http://www.jianshu.com/p/465830080ea9](http://www.jianshu.com/p/465830080ea9 "jianshu")