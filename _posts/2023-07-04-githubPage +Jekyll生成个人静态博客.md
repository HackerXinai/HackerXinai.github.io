---
---
Jekyll需要前端web开发经验。
Jekyll具有丰富的主题，而不是只使用gem默认主题。

说明：基本就是官网的翻译。可以直接看官网。
# 步骤如下：
## 1. 建项目
根据gitpages官网指示创建仓库和index.html，并clone拉到本地，假设在myblog文件夹下。以下命令，没有特殊说明的话，都是在myblog文件夹下执行。
## 2. 安装前置条件ruby,
## 3. 安装jekyll
在myblog文件夹下，为你的项目，安装jekyll。
```bash
# 安装jekyll和bundler。
gem install jekyll bundler
# cd myblog下后。初始化文件夹，生成Gemfile。
bundle init
# 打开Gemfile, 在末尾添加如下内容，增加Jekyll依赖。
gem 'jekyll'
# 为你的项目初始化jekyll。生成Gemfile.lock。
bundle
```
## 4. 构建
```bash
# 构建网络，生成_site文件夹，可以在htpp://localhost:4000看到网页，并且可以实时更新。在界面上看到helloworld，你就成功了。
bundle exec jekyll serve
```
## 5. 编辑你的文章index.html - 增加[liquid](#liquidId)
在你的根目录下创建index.html，填入如下内容：
```html
{% raw %} 
---
---
<!-- # 文章内容可以使用Liquid模板语言。 -->
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Home</title>
  </head>
  <body>
  <!-- 这个模板语言，表示将字母小写，最终会在网页上看到hello world! -->
    <h1>{{ "Hello World!" | downcase }}</h1>
  </body>
</html>
{% endraw %}
```
## 6. 编辑你的文章index.html - 增加Front Matter，例如设置变量title及其调用
注：文章头部加两行---，代表Front Matter区域，代表这个文章需要被jekyll解析, 计算liquid等。
```html
{% raw %} 
---
title: Home
---

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ page.title }}</title>
  </head>
  <body>
    <h1>{{ "Hello World!" | downcase }}</h1>
  </body>
</html>
{% endraw %}
```
## 7. 使用markdown，而不是html编辑你的文章。-layouts
- 设置layout: 在根目录下创建_layouts文件夹，进入_layouts文件夹，创建default.html，内容如下。

```html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ page.title }}</title>
    <style>
        body { background-color: aqua;  }
    </style>
  </head>
  <body>
  {% raw %}  {{ content }} {% endraw %}
  </body>
</html>
```

- 在项目根目录创建markdown文件,about.md，输入：

```
---
title: about
---
hello world.Markdown for Jekyll.
```

- 使用layout：在index.html和about.md文件的在Front Matter区域，增加layout: deafult，即：

```
---
layout: default
---
```

然后访问localhots:4000和localhost:4000/about就会发现背景色不再是白色的，而是layout default.html中设置的颜色。
## 8. 导航。-学习includes
_includes


# <span id='liquidId'>Liquid：模板语言</span>
包含三个主要组件：
- Objects对象。objects对象告诉liquid要输出**预定义变量**。
        用4个大括号表示{{}}，比如{{ page.title }}表示要输出page.title变量。
- tags标签。tags标签定义了**模板的逻辑和控制流**。
        用{% raw %} {% %} {% endraw %}表示。
        例如，用变量控制html页面下列元素是否展示。

```html
{% raw %} {% if page.show_sidebar %}
    <div class="sidebar">
        sidebar content
    </div>
{% endif %} {% endraw %}
```

- filters过滤器。过滤器能够改变liquid的输出。示例:{{ page.date | date_to_string }}

# Front Matter 前置事件
```
---
---
```
Front Matter就是其中间的YAML片段。

```bash
---
# 设置变量。可以使用liquid调用。调用时使用：{{page.my_number}}
my_number: 5
---
```
## 变量
- page.url: 当前文章的url路径，是以_site为根目录的相对路径。比如/about.html，/2023/07/01/article.html
- site.data.navigation： data目录下navigation.yml里的内容，返回array
- site.posts： _post目录下的文件
    post.excerpt： 默认情况下是文章的第一段


```html
{% raw %}{% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      {{ post.excerpt }}
    </li>
{% endfor %}{% endraw %}
```



# jekyll目录结构：
_site: 存储Jekyll生成的文件，最终会呈现在网页上，不需要改动。
Gemfile: 使用```bundle init```命令能够生成Gemfile。如果存在Gemfile的话，执行的命令前会自动加上bundle exec，比如你执行```jekyll server```,实际上执行的是```bundle exec jekyll serve```
Gemfile.lock
_layouts: 样式模板。
    default.html,调用导航模板html，调用css文件。在文章内容中的Front Matter区域中使用: layout:default。
    layout可以继承
_includes: 导航模板。navigation.html。 对标签样式特殊标记。
_data:
    - navigation.yml 存储所有的导航链接，每一组由name、link组成。调用变量site.data.navigation，返回链接的迭代器。
asset:
    css
        styles.scss：指向_sass路径下的scss文件。jekyll调用，会将其转换为style.css.
    images
    js
_sass:
    main.scss：包含样式的scss文件。
_posts:放置你的文章。必须按照特殊的格式：发表时间（不能是未来时间，否则显示不出来）、标题   
      title、后缀。2023-07-02-hello-world-article.md
      变量site.posts是所有文章对象，可以用迭代器循环。
      最终文章会被Jekyll构建到_site目录下。
_config.yml: 配置文件，构建网站时的设置。没有配置时，会自动使用默认配置，比如网站名、markdown转html默认使用Kramdown Markdown filter。
```ruby
# frozen_string_literal: true
source "https://rubygems.org"

gem "jekyll"
```
```yml
# _config.yml
collections:
  authors:
```

最简单的目录结构只需要如下：
![Alt text](asset/jekyll/image-1.png)

# 主题
结构html、样式css、和交互js的组合, 这种组合会呈现不一样的视觉效果，这就称为主题。
在jekyll中，这样组合存储在asset、_data、_layouts、_includes、_sass等文件夹下。
基于gem依赖，开发者可以开发出很多样式，只需要引入gem依赖，即可更改主题文件和文件夹，即可更改样式，非常方便。
1. 引入主题到Gemfile
2. 执行```bundle update```

**[主题的国际化][主题的国际化]**

# 再进一步 - 自己定制主题
成为一个主题开发者。
你可以将你的主题打包到RubyGems上，允许用户通过Bundler安装。
不需要熟悉rubyGems，仅使用jekyll就可以[定制自己的主题]。

Bundler是Ruby依赖管理工具。
```bundle init```用来初始化文件夹。将会在文件夹下新建Gemfile，这个自动生成的Gemfile默认会包含rubygem的源。
Gemfiles最少需要一个gem源。
Gemfileges文件结构:
```ruby
# frozen_string_literal: true
# A sample Gemfile
# 源
# 需要下载的依赖
source "https://rubygems.org"
gem "rails"
```
# 再进一步 - 将任何html网站转换成Jekyll的主题
1. default.html

# 其他 -  ruby介绍
Jekyll是ruby的一个gem,jekyll的插件、jekyll-seo-tag、jekyll-feed、jekyll-archives都是gem。gem允许用户将代码分享到ruby包管理工具，gem可以将ruby项目转换成json、Pagination、用API进行交互。
Gemfile: 
Bundler是一个gem, 它可以安装Gemfile里指定的gem。

```bundle```生成Gemfile.lock文件

<br>
<br>
更多请查看[Jekyll官网][Jekyll官网]。
<br>
<br>
开始时间-结束时间：2023-06-30 -> 2023-07-03


[Jekyll官网]:https://jekyllrb.com/
[按步骤学习]:https://jekyllrb.com/docs/step-by-step/01-setup/
[主题的国际化]:https://jekyllrb.com/docs/themes/#themes-with-data-directory
[定制自己的主题]:https://jekyllrb.com/docs/themes/#creating-a-gem-based-theme