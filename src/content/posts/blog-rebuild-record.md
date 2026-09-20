---
title: "博客重构记录"
published: 2026-09-20T17:10:00+08:00
draft: false
description: "把博客从 Jekyll + Chirpy 迁到了 Astro + Firefly，顺便加了个项目展示区。记一下这次重构的缘起和结果。"
tags: [随笔, 博客]
category: 个人感悟
lang: zh_CN
---

前一阵子社区上面很多人提到用AI重构博客，学习到了一些知识，所以打算把博客美化一下，全程依然是祈祷式开发。这次重构主要目的有两点一是界面美化，二是首页增加项目展示框。重构方案选择了Astro 7（Node）+ CuteLeaf/Firefly。

原来的博客用的是Jekyll + Chirpy，跑了不到半年。主题本身挺好，但有两个问题：一是它是个纯博客主题，没有"作品集"这个概念，我手上那几个自己做的小工具一直没地方放；二是它基于Ruby，而我电脑上没装Ruby环境，所以这么久以来我一直没法本地预览，每次改点东西都只能推上去看线上效果，错了再改再推，来回折腾。

换成Astro之后最直接的收益就是这个坑填上了，本地起个服务就能实时看效果，改完刷新一下就行。附带的好处是可以本地预览了。

技术栈这块简单说一下：Astro是构建框架，负责把Markdown和组件编译成静态HTML；Firefly是主题，底层是Astro + Svelte + Tailwind CSS，配色是色相驱动的——改一个hue值全站颜色就跟着换，不用挨个改CSS。这个设计挺好用，我现在的青绿色主题就是调了这一个数字出来的。

## 迁移过程

结构上变化不小，从Jekyll的约定式目录换成了Astro的内容集合：

| | 改版前 | 改版后 |
|---|---|---|
| 框架 | Jekyll（Ruby） | Astro 7（Node） |
| 主题 | jekyll-theme-chirpy | CuteLeaf/Firefly |
| 文章位置 | `_posts/YYYY-MM-DD-标题.md` | `src/content/posts/标题.md` |
| 配图位置 | `assets/img/posts/` | `public/assets/img/posts/` |
| 配图引用 | `{{ site.baseurl }}/assets/...` | `/assets/...` |
| CI | `pages-deploy.yml`（Ruby） | `deploy.yml`（Node + pnpm） |

内容上做了加减法。加的是首页那个横向项目区，在文章列表上方，一行四列带"全部/已发布/开发中"的筛选标签。减的是关掉了主题自带的音乐播放器和11个我用不上的页面（友链、留言板、相册、追番、打赏这些）。另外把浏览器图标换了。

## 结果

最后结果还是比较满意。跑一阵试试。距离上次写blog又过去了很久，很多想写的懒了放下就没写，争取近期写一下。好了就到这吧，算是小小的记录。
