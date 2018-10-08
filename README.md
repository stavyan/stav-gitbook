## GitBook 使用

出于博客总结归纳的想法，于是找到了 GitBook，我把它做为博客的备份。顺带学习了 GitBook用法。[预览地址](https://www.stavtop.club/stavblog)。


## 准备工作

### 安装 Node.js

1.  GitBook 是基于 Node.js 的命令行工具，下载安装 Node.js。详见[安装Nodejs 及 npm环境](https://stavtop.club/blog/NodeJS/installing-nodejs-and-npm-environment)

2. 检测安装是否成功：
`node -v`

### Gitbook 安装

1. Gitbook 是用 npm 安装的
`npm install -g gitbook-cli`

2. 检测安装是否成功
```
gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```

3. 更新最新版本：
`gitbook update`

4. 卸载
```
npm uninstall -g gitbook
GitBook Editor
```
官方编辑器，[下载](https://www.gitbook.com/editor) ，正常注册登录使用就行了。

5. 插件
> book.json
新建一个 book.json 文件，可以配置网站信息、在 plugins 和 pluginsConfig 字段添加插件等。

插件命名方式为：
gitbook-plugin-X: 插件；
gitbook-theme-X: 主题。

可以在 npmjs 或 GitBook 插件 直接搜索插件或者主题。
book.json 内容大概如下：

```
{
  "gitbook": "3.2.3",
  "title": "斯塔夫部落格",
  "description": "https://stavtop.club",
  "author": "stanyan",
  "language": "zh-hans",
  "links": {
    "sidebar": {
    }
  },
  "plugins": ["github",
    "donate",
    "splitter",
    "anchor-navigation-ex",
    "-sharing",
    "sharing-plus",
    "-highlight",
    "prism"
  ],
  "pluginsConfig": {
    "sharing": {
      "douban": false,
      "facebook": false,
      "google": false,
      "hatenaBookmark": false,
      "instapaper": false,
      "line": false,
      "linkedin": false,
      "messenger": false,
      "pocket": false,
      "qq": false,
      "qzone": false,
      "stumbleupon": false,
      "twitter": false,
      "viber": false,
      "vk": false,
      "weibo": false,
      "whatsapp": false,
      "all": [
        "weibo","qq","qzone","google","douban"
      ]
    },
    "github": {
      "url": "https://github.com/WuXiaolong"
    },
    "donate": {
      "wechat": "https://stavyan.github.io/stav-gitbook/img/dashang.JPG",
      "title": "",
      "button": "赏",
      "wechatText": "微信打赏"
    },
    "anchor-navigation-ex": {
      "associatedWithSummary":false,
      "showLevel":true,
      "multipleH1": true,
      "mode": "float",
      "pageTop": {
        "showLevelIcon": false,
        "level1Icon": "fa fa-hand-o-right",
        "level2Icon": "fa fa-hand-o-right",
        "level3Icon": "fa fa-hand-o-right"
      }
    },
    "theme-default": {
      "showLevel": true
    },
    "fontsettings": {
      "theme": "white",
      "family": "serif",
      "size": 2
    },
    "prism": {
      "css": [
        "prismjs/themes/prism-tomorrow.css"
      ]
    }
  }

}
```
6. 说明：
```
github：添加 GitHub 图标；
Donate：添加赞赏按钮；
splitter：使侧边栏的宽度可以自由调节；
anchor-navigation-ex：添加Toc到侧边悬浮导航以及回到顶部按钮；
theme-default：将 showLevel 设为 true， 就可以显示标题前面的数字索引，默认不显示。
```
7. 安装插件
`gitbook install ./`
不要忘记这步，根目录 node_modules 文件下能看到安装那些插件。

8. 单独安装插件
`npm install gitbook-plugin-anchor-navigation-ex --save`

9. 默认插件
GitBook 默认带有5个插件：
- highlight
- search
- sharing
- fontsettings
- livereload
9. 如果要去除自带的插件，可以在插件名称前面加 -
```
"plugins": [
"-search"
]
```
如果想配置直接在 pluginsConfig 配置。

## GitBook 输出
### 本地预览
> 进入你的 GitBook 书籍根目录
`gitbook serve `
然后浏览器打开 http://localhost:4000 就能预览了，Ctrl + C退出。

### 输出静态网站
`gitbook build`
> 以上都会在书籍目录生成 _book，前者能实时预览。

### 输出 PDF 文件
1. 下载 Calibre
生成 PDF 文件依赖于 ebook-convert，需要安装 Calibre

2. 配置 Calibre 环境变量
如何配置环境变量参考这里，在 .bash_profile 文件加入
`export PATH=/Applications/calibre.app/Contents/MacOS:$PATH`

3. 更新刚配置的环境变量
`source .bash_profile`

4. 查看所有的配置路径
`$ echo $PATH`

5. 输出 PDF 文件
`gitbook pdf`
> 将在根目录下生成了 book.pdf 文件

## 发布

### 打包上传
> 使用`gitbook build`输出静态网站，然后上传至服务器即可。

### gitbook 官网发布
1. 上传的远程 git

2. 设置 GitBook 域名

3. 填入自己的域名

4. 配置 DNS

5. 详见gitbook官方文档 

### 交流

笔者热爱新技术学习、热衷分享。

- QQ：617946852
- Email：stavyan@qq.com
- WeChat stav_yan
<div align="center">
	<img width="300" height="400" src="https://stavyan.github.io/stav-gitbook/img/wx.JPG" />
</div>
### 最后
> 欢迎进入笔者的私人空间---[斯塔夫部落格](https://stavtop.club)
