# 前言
open-Estuary是基于github.io的博客网站。github.io默认采用Jekyll作为建站工具，Jekyll是一款当前非常火热的开源的静态网站建站工具，用你喜欢的标记语言书写内容。它利用模板创建一个静态网站，在整个处理过程中，你可以调整你想要的网址样式，在模板中显示哪些数据等等，它拥有非常庞大的社区和使用群体。Jekyll不需要数据库支持，但可以配合第三方服务,例如Disqus等。

## 技术栈

Jekyll + HTML + CSS + JQuery + Node + Layui + Markdown  


## 开发环境搭建

1.  安装Jekyll
```
 下载Ruby 地址：https://rubyinstaller.org/downloads/

 安装rubyinstaller-devkit-2.6.3-1-x64.exe 注:不能安装在有中文字符的文件夹下，否则会识别不了。
```
2.  配置RubyGems源
```
 使用"gem sources" 查看默认源

 使用"gem sources -r 默认源" 将默认源删除

 使用"gem sources -a http://rnd-mirrors.huawei.com/rubygems/" 将华为镜像源加入

```
3.  安装Github pages
Github pages其实就是github基于Jekyll用来构建github.io的工具，安装好Ruby之后可以执行

```
 gem install github-pages
```

4.  下载项目源码

```
git clone https://github.com/open-estuary/open-estuary.github.io
```

5.  启动运行
```
 进入项目根目录：cd  open-estuary

 启动命令：jekyll serve –watch 或者npm run dev

 查看网页：http://127.0.0.1:4000
 
 如果你想其它电脑可连接访问你的本地服务器，可以使用npm run pro
 
 访问地址：http://要访问的服务器ip:4000

```
6.  相关文档链接
Jekyll教程地址：http://wiki.jikexueyuan.com/project/jekyll/
# 说明

>  如果对您有帮助，您可以点右上角 "Star" 支持一下 谢谢！ ^_^
