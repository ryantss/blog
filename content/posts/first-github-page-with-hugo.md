---
title: "First Github Page With Hugo"
date: 2018-03-26T00:28:21+08:00
draft: false
---

This is my first post in GitHub Page. I had my first attempt in just following [GitHub Pages](https://pages.github.com) guide and it led me to [Jekyll](https://jekyllrb.com), which GitHub Pages is [deeply integrated](https://help.github.com/articles/about-github-pages-and-jekyll/) with. I came across with other coder's blog hosted in GitHub Page and found that it is deployed via [Hugo](https://gohugo.io/hosting-and-deployment/hosting-on-github/#types-of-github-pages)!

I am considered new to GitHub Page, Jekyll and [Hugo](https://gohugo.io) and I couldn't resist to try it out now.

First, I followed [GitHub Pages](https://pages.github.com) guide and create [User Site](https://help.github.com/articles/user-organization-and-project-pages/) `https://<USERNAME>.github.io` and spent 10 minutes to choose the theme. Then, I realized it is using Jekyll. Played with for awhile and found that I could use **Hugo** to deploy my own GitHub Page so I am tempted to give it a try.

I was following Hugo's [Host on GitHub](https://gohugo.io/hosting-and-deployment/hosting-on-github/#types-of-github-pages) guide to create my own Hugo site on GitHub page. As suggested, I followed Hugo [quickstart guide](https://gohugo.io/getting-started/quick-start/) and selected **[pickles](https://themes.gohugo.io/hugo_theme_pickles/)** theme for my new site. I checked those code into my `blog` repo and deleted my previous code from `skyfish81.github.io` repo.

As documentation of `pickles` theme suggested, I should copy `config.toml` from its `exampleSite/config.toml` and update it with my configuration. For instance, 
changed `baseURL` (must end with the `/`!), `title`, `enableEmoji`, social account ids, and so on. I have disabled a bunch of social accounts integration and also commented the navigation menus that I do not have the page yet.

```
blog$ cp themes/hugo_theme_pickles/exampleSite/config.toml .
```

For hugo to generate the content of `blog` into my GitHub Page, I need to add submodule to map `skyfish81.github.com` repo to `public` folder. 

```
blog$ git remote -v
origin	git@github.com:skyfish81/blog.git (fetch)
origin	git@github.com:skyfish81/blog.git (push)

blog$ git submodule add -b master git@github.com:skyfish81/skyfish81.github.io.git public
```

When I run `hugo` command, it builds my site to `public` as static pages and I could host it on GitHub with that directly. There's sample `deploy.sh` script provided by Hugo to make our life easy!

```
blog$ ./deploy.sh
```

And I shall see the updated changes at https://skyfish81.github.io ! That's it! 
