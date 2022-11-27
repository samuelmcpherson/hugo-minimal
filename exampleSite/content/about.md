---
title: About Hugo XMin
author: Yihui Xie
---

**XMin** is the first Hugo theme I have designed. The original reason that I wrote it was I needed a minimal example of Hugo themes when I was writing the  [**blogdown**](https://github.com/rstudio/blogdown) book. Basically I wanted a simple theme that supports a navigation menu, a home page, other single pages, lists of pages, blog posts, categories, tags, and RSS. That is all. Nothing fancy. In terms of CSS and JavaScript, I really want to keep them minimal. In fact, this theme does not contain any JavaScript code at all, although on this example website I did introduce some JavaScript code (still relatively simple anyway). The theme does not contain any images, either, and is pretty much a plain-text theme.

The theme name "XMin" can be interpreted as "**X**ie's **Min**imal theme" (Xie is my last name) or "e**X**tremely **Min**imal theme".

# config.yaml

For this example site, I defined permalinks for two sections, `post` and `note`, so that the links to pages under these directories will contain the date info, e.g., `https://xmin.yihui.org/post/2016/02/14/a-plain-markdown-post/`. This is optional, and it is up to your personal taste of URLs.

```yaml
permalinks:
  note: "/note/:year/:month/:day/:slug/"
  post: "/post/:year/:month/:day/:slug/"
```

You can define the menu through `menu.main`, e.g.,

```yaml
menu:
  main:
    - name: Home
      url: ""
      weight: 1
    - name: About
      url: "about/"
      weight: 2
    - name: Categories
      url: "categories/"
      weight: 3
    - name: Tags
      url: "tags/"
      weight: 4
    - name: Subscribe
      url: "index.xml"
```

Alternatively, you can add `menu: main` to the YAML metadata of any of your pages, so that these pages will appear in the menu.

The page footer can be defined in `.Params.footer`, and the text is treated as Markdown, e.g.,

```
params:
  footer: "&copy; [Yihui Xie](https://yihui.org) 2017 -- {Year}"
```

Here `{Year}` means the year in which the site is built (usually the current year).

# Custom layouts

There are two layout files under `layouts/partials/` that you may want to override: `head_custom.html` and `foot_custom.html`. This is how you inject arbitrary HTML code to the head and foot areas. For example, this site has a file `layouts/partials/foot_custom.html` to support LaTeX math via MathJax and center images automatically:

```html
<script defer src="//yihui.org/js/math-code.js"></script>
<script defer src="//mathjax.rstudio.com/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

<script defer src="//yihui.org/js/center-img.js"></script>
```

You can certainly enable highlight.js for syntax highlighting by yourself through `head_custom.html` and `foot_custom.html` if you want.

If you do not like the default fonts (e.g., `Palatino`), you may provide your own `static/css/fonts.css` under the root directory of your website to override the `fonts.css` in the theme.

# Other features

```yaml
permalinks:
  note: "/note/:year/:month/:day/:slug/"
  post: "/post/:year/:month/:day/:slug/"
```

I hope you can enjoy this theme. The source code is [on Github](https://github.com/yihui/hugo-xmin). Happy hacking!
