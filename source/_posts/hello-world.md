---
title: Hello World
---

Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).

## Quick Start

### Modify NPM image source

```cmd
npm config set registry https://registry.npm.taobao.org
```

### Initialize project

```cmd
d:
cd dev/workspace/hexo       #Enter the workspace
cnpm install -g hexo-cli    #Install hexo
hexo init                   #Initialize project
code .                      #Open project with VS Code
```

### Create a new post

```bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

```bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Project introduction

```
scaffolds #md mould
source/_ports  #Articles and pages md
themes.hexo-theme-matery  #themes
  source
    medias
      banner   #banner img
      featureimages   #24 featured pictures
  layout
    _partial
      footer.ejs    #footer info
      socila-link.ejs   #Modify social links info
      bg-cover-content.ejs  #banner img change js
  _config.yml   #Topic related configuration
_config.yml     #hexo configuration
```

### Change themes

```
git clone https://github.com/blinkfox/hexo-theme-matery.git
```

- Modify the value of theme in \_config.yml of Hexo's root folder:

```_config.yml
theme: hexo-theme-matery
```

- More info: [Hexo-theme-matery](https://github.com/blinkfox/hexo-theme-matery/blob/develop/README_CN.md)

### Code highlighting

```
cnpm i -S hexo-prism-plugin
```

- Then,modify the value of highlight.enable to false in _config.yml file of Hexo root folder, and add the configuration of prism plugin as follows:

```_config.yml
highlight:
  enable: false

prism_plugin:
  mode: 'preprocess'    # realtime/preprocess
  theme: 'tomorrow'
  line_number: false    # default false
  custom_css:
```

### Install hexo-generator-search

```terminal
npm install hexo-generator-search --save
```

- Add configuration of _config.yml file in Hexo root folder as follows：

```
search:
  path: search.xml
  field: post
```

### Translate Chinese Link to Pinyin (Recommend)

```terminal
npm i hexo-permalink-pinyin --save
```

- Add such configurations in _config.yml file of Hexo:

```_config.yml
permalink_pinyin:
  enable: true
  separator: '-' # default: '-'
```

### Post word count statistics plugin

```terminal
npm i --save hexo-wordcount
```

- Then just activate the following configuration items in the theme _config.yml file:

```themes/hexo-theme-matery/_config.yml
postInfo:
  date: true
  update: false
  wordCount: false # 设置文章字数统计为 true.
  totalCount: false # 设置站点文章总字数统计为 true.
  min2read: false # 阅读时长.
  readCount: false # 阅读次数.
```

### Regenerate the blog file

```terminal
hexo clean && hexo g
```

### Modify website footer

- Website footer may need to be customized, and it is not convenient to make configuration information, So need to modify and process it by yourself. The changes are in the /layout/_partial/footer.ejs file, including the site, the theme used, the amount of traffic and so on.

### Modify social links

- In the theme _config.yml file, the configurations of QQ, GitHub and mailbox and more are supported by default. In the /layout/_partial/social-link.ejs file of the theme, you can add or modify the social link address as you need. To add a link, please refer to the following code:

### deploy

```_config.yml
deploy:
  type: git
  repo: https://github.com/willasas/willasas.github.io
  branch: master
```

```terminal
git init
git remote add origin https://github.com/willasas/willasas.github.io.git
npm install hexo-deployer-git
npm run deploy
```

### 部署GitHub Page

- 选择仓库名称下面一行选项中的"settings"进入到仓库的设置界面中。在github pages选项中提示你的网站已经发布在仓库名字对应的网址上了

### 源代码提交到dev分支

```bash
git checkout -q -b dev  #创建并切换到dev分支
git add .
git commit -m "dev demo"

```