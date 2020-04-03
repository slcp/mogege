# mogege

[![Hugo](https://img.shields.io/badge/hugo-0.68.3-blue.svg)](https://gohugo.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

### A blog theme for [Hugo](https://gohugo.io).

![Screenshot](https://raw.githubusercontent.com/Mogeko/mogege/master/images/Screenshot.png)

**This project is based on [LeaveIt](https://raw.githubusercontent.com/liuzc/LeaveIt/)**

Because the author of [LeaveIt](https://raw.githubusercontent.com/liuzc/LeaveIt/) seems to have abandoned this project, but I prefer this theme, so I simply reopened a new project.

At this stage, I mainly integrate the part I modified with LeaveIt, and will add more features in the future.

## Features
- Automatically highlighting code (Support by [highlight.js] (https://highlightjs.org/))
- Dark/Light Mode
- Support for embedded BiliBili video
- Support hidden text
...


## Requirements
Hugo 0.68.3 or higher

**Hugo extended version**, read more [here](https://gohugo.io/news/0.48-relnotes/)

## Installation
Navigate to your hugo project root and run:

```bash
git submodule add https://github.com/Mogeko/mogege themes/mogege
```

Then run hugo (or set `theme: mogege` in configuration file)

```bash
hugo server --minify --theme mogege
```

## Creating site from scratch
Below is example how to create new site from scratch

```bash
hugo new site mydocs; cd mydocs
git init
git submodule add https://github.com/Mogeko/mogege  themes/mogege
cp -R themes/mogege/exampleSite/content .
```

```bash
hugo server --minify --theme mogege
```

## Embedded BiliBili video

You can embed BiliBili videos via Shortcodes, just provide the AV号 of the bilibili video

```txt
{{< bilibili [AV号] >}}
```

Click [here](https://mogeko.github.io/2020/079#biliplayer) for examples

## Hidden text

You can use "hidden text" to hide spoiler content

```txt
{{< spoiler >}} HIDDEN TEXT {{< /spoiler >}}
```

Click [here](https://mogeko.github.io/2020/080#spoiler) for examples

## Gitalk comment system
This blog supports the [gitalk](https://github.com/gitalk/gitalk) comment system. To use gitalk, you need to apply for a Github Application. For details, please refer to [here](https://mogeko.me/2018/024/#%E5%88%9B%E5%BB%BA-github-application).

Then enable gitalk in config.toml
```toml
[params]
    enableGitalk = true
```

Then provide your `Client ID` and `Client Secret` from Github Application in config.toml
```toml
[params.gitalk] # Github: https://github.com/gitalk/gitalk
    clientID = "[Client ID]" # Your client ID
    clientSecret = "[Client Secret]" # Your client secret
    repo = "" # The repo to store comments
    owner = "" # Your GitHub ID
    admin= "" # Required. Github repository owner and collaborators. (Users who having write access to this repository)
    id= "location.pathname" # The unique id of the page.
    labels= "gitalk" # Github issue labels. If you used to use Gitment, you can change it
    perPage= 15 # Pagination size, with maximum 100.
    pagerDirection= "last" # Comment sorting direction, available values are 'last' and 'first'.
    createIssueManually= true # If it is 'false', it is auto to make a Github issue when the administrators login.
    distractionFreeMode= false # Enable hot key (cmd|ctrl + enter) submit comment.
```

## Configuration
There are few configuration options you can add to your `config.toml` file.

```toml
baseURL = "" # <head> 里面的 baseurl 信息，填你的博客地址
title = "" # 浏览器的标题
languageCode = "zh-cn" # 语言
hasCJKLanguage = true # 开启可以让「字数统计」统计汉字
theme = "mogege" # 主题

paginate = 11 # 每页的文章数
enableEmoji = true # 支持 Emoji
enableRobotsTXT = true # 支持 robots.txt


preserveTaxonomyNames = true

[blackfriday]
  hrefTargetBlank = true
  nofollowLinks = true
  noreferrerLinks = true

[Permalinks]
  posts = "/:year/:filename/"

[menu]
  [[menu.main]]
    name = "Blog"
    url = "/posts/"
    weight = 1

  [[menu.main]]
    name = "Categories"
    url = "/categories/"
    weight = 2

  [[menu.main]]
    name = "Tags"
    url = "/tags/"
    weight = 3

  [[menu.main]]
    name = "About"
    url = "/about/"
    weight = 4

[params]
    since = 
    author = ""                         # Author's name
    avatar = "/images/me/avatar.jpg"    # Author's avatar
    subtitle = ""                       # Subtitle
    home_mode = ""                      # post or other
    enableGitalk = true                 # gitalk 评论系统

    google_verification = ""

    description = "" # (Meta) 描述
    keywords = "" # site keywords

    beian = ""
    baiduAnalytics = ""
    googleAnalytics = "" # Google 统计 id

    license= '本文采用<a rel="license" href="http://creativecommons.org/licenses/by-nc/4.0/" target="_blank">知识共享署名-非商业性使用 4.0 国际许可协议</a>进行许可'

[params.gitalk] # Github: https://github.com/gitalk/gitalk
    clientID = "" # Your client ID
    clientSecret = "" # Your client secret
    repo = "" # The repo to store comments
    owner = "" # Your GitHub ID
    admin= "" # Required. Github repository owner and collaborators. (Users who having write access to this repository)
    id= "location.pathname" # The unique id of the page.
    labels= "gitalk" # Github issue labels. If you used to use Gitment, you can change it
    perPage= 15 # Pagination size, with maximum 100.
    pagerDirection= "last" # Comment sorting direction, available values are 'last' and 'first'.
    createIssueManually= true # If it is 'false', it is auto to make a Github issue when the administrators login.
    distractionFreeMode= false # Enable hot key (cmd|ctrl + enter) submit comment.

```

---

> The name of this project comes from the game [*Mogeko Castle*](https://okegom.fandom.com/wiki/Mogeko_Castle), and the [author](https://github.com/Mogeko)'s name also comes from this game. (this is another story)