---
layout: post
title: Migrated to Jekyll!
date: '2018-02-05 00:00:00 +0800'
categories: meta
tags: [jekyll, github-pages]
description: A short account of my experience migrating a blog from Wordpress to Jekyll.
---
Well, **I did it!** Here is the customary *Welcome-to-my-Jekyll-blog* post, where I try to outline all the steps involved in creating my blog, powered by [Jekyll](https://jekyllrb.com/) and hosted on [Github Pages](https://pages.github.com/).

<!--excerpt-->

Migrating to Jekyll is possibly one of the best options for a blog. Its primary advantages over Wordpress.com are outlined on this [Quora post](https://www.quora.com/What-are-the-advantages-of-using-Jekyll-to-create-static-pages). Personally, I appreciate the ease at which I can customize this site's design, compared to other *freemium blogging platforms*.

## Installing Jekyll on Windows

This part here is considered to be rather tricky, since Jekyll is not officially supported on Windows. However, I managed to follow the [Official Jekyll Documentation's tutorial](https://jekyllrb.com/docs/windows/#installation) rather smoothly. The only issue I ran into was that Ruby commands aren't immediately executable after installing it. [This  guide](https://foundation.zurb.com/forum/posts/8142-gem-or-foundation-command-not-found-with-git-bash-try-this), which is based on [this stack](https://stackoverflow.com/questions/3426347/how-to-run-ruby-and-git-commands-in-one-place-on-windows/10159798#10159798), helped me correctly add the path to my Ruby bin folder to Windows' environment variables. I managed to install Jekyll soon after.

After installing Jekyll, the tutorial prompts you to run `jekyll new_my blog`, however I recommend **not** running this if you plan to select a theme outside of the [officially supported themes](https://pages.github.com/themes/) on Github Pages.

## Hosting with Github Pages & Choosing a theme

Theme selection might seem to be a bold jump so early on. But after messing around with the base files after running `jekyll new_my blog`, I realised that if you plan on using unofficial themes, it's much easier to **fork** the theme's base repository and build your site from there. Using `jekyll-remote-theme` causes a dependency error for those without [cUrl](https://curl.haxx.se/).

Forking is not without its issues though, especially if the repository is outdated, but they are usually limited to common issues that can be quickly solved with a bit of tweaking. [Here's a helpful video](https://www.youtube.com/watch?v=bty7LHm14CA) explaining how to install a theme by forking, set it up with Github Pages, and lastly solve those common issues.

For my theme recommendations, I would advocate [**Poole**](http://getpoole.com/), [**Lanyon**](https://github.com/poole/lanyon) or [**Hyde**](https://github.com/poole/hyde) for blogs. Since they are somewhat popular themes, there are quite a few resources out there to help with customizations. If you can't be bothered with customizing, then feel free to utilize some of the more elaborate themes easily found through a [Google Search](https://www.google.com.sg/search?q=jekyll+themes).

**Github Pages** is quite a common platform for hosting Jekyll sites, as it is free, and comes with its own repository for content management. However, there are several issues that can be encountered with it. Firstly, Github Pages uses a subdirectory URL structure that might interfere with running with `http://localhost:4000` when your code references `{{site.baseurl}}`. You will need to tweak the code using this format: [Project Page URL structure](https://jekyllrb.com/docs/github-pages/#project-page-url-structure). Else, you can use [multiple configuration files](http://sandeepbhardwaj.github.io/2015/10/17/jekyll-with-environment-variable-and-multiple-config-files.html). Set up a seperate `_config-dev.yml` and run the following  whenever you build locally.

```bash
jekyll serve -w --config _config-dev.yml
```

Also, Google Analytics docks Github Pages for not leveraging browser caching. Github Pages sets `cache-control: max-age` to 10 minutes in the header, and there is no way to change that as of now, unless you use your own CDN such as [Cloudflare](https://www.cloudflare.com/). There is, however, [a workaround]((https://diywpblog.com/leverage-browser-cache-optimize-google-analytics/)) that requires you to download the analytics script and host it locally.

## Customization Options

Technically there is no end to customization, but there are certain common ones used by many Jekyll blogs. Here are some resources that I used. Some of these are from blogs that also utilise Jekyll and the Poole family of themes.

#### [Post Excerpts](https://wesleytsai.io/2015/07/06/create-post-previews-for-jekyll-blogs/)
For when your main pages is loaded with content and you wish to condense the posts into bite-size previews.

#### [Tags](https://pavdmyt.com/how-to-implement-tags-at-jekyll-website/)
A typical blog feature not usually supported with Github Pages.

#### [Featured Image](https://blog.webjeda.com/fetch-image-jekyll/)
Brightens up the main page! Quite a popular Wordpress.com feature.

#### Poole/Lanyon/Hyde specific: [Patrick's outline](http://patricksteadman.ca/2014/08/04/lanyonsetup/) & [Kyle's walkthrough of it](http://kylestratis.com/2015/05/05/blog-setup-pt2/)
General customization guides for creating elegant blogs.
