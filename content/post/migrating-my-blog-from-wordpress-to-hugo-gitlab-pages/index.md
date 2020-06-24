---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Migrating My Blog From WordPress to Hugo & GitLab Pages"
subtitle: "Why and How I Made the Move"
summary: ""
authors: [suzanne]
tags: [technology]
categories: []
date: 2019-08-31T22:59:53-07:00
lastmod: 2019-08-31T22:59:53-07:00
featured: false
draft: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

## Beginnings of the Blog
Way back in the fall of 2014 I started a new blog, [suzanne.link](https://suzanne.link), for publishing my technical articles and random nerd humor. Unlike most websites I'd ever built before, I created this one with [WordPress 4](https://www.wordpress.org/) and later on added the [Layers](https://github.com/layers-wp/layerswp) theme, which allowed me to construct a homepage with a custom layout fairly easily and with zero code. My blog was hosted on the managed website platform [Pantheon](https://pantheon.io), where I'd worked, and this setup served me quite well for five years. Over this period I authored a few posts and migrated some articles over from my [OG blog](https://www.aigeanta.net).

## Reasoning for Change
Fast forward five years later to 2019, and with the release of WordPress 5 comes the Gutenberg editor, which aims to provide an intuitive page layout software in core without the need for contributed themes & plugins. While I like where this effort is headed, there were a few problems with the current implementation that informed my decision that WordPress wasn't worth supporting anymore for my particular blog. For the sake of obtaining my ideal authoring experience, I decided to look into a static site generator for the new implementation.

### Markdown Footnotes

Gutenberg doesn't yet properly support Markdown footnotes, which my posts utilize quite extensively. Here's an example of a footnote from one of my blog posts that I originally wrote in Markdown format:

```markdown
"Iranian President Mahmoud Ahmadinejad said [in November 2010] that malicious computer code launched by “enemies” of the state had sabotaged centrifuges used in Iran’s nuclear-enrichment program."[^1]
```

```markdown
[^1]: Kim Zetter, “Iran: Computer Malware Sabotaged Uranium Centrifuges,” Wired.com Threat Level, November 29, 2010, http://www.wired.com/threatlevel/2010/11/stuxnet-sabotage-centrifuges/.
```

Although the Jetpack implementation of Markdown still supports my articles' footnotes in a fashion, it doesn't allow me to edit the Markdown version anymore, instead presenting HTML for all these notations in the code editor. The same footnote now becomes an impossible-to-edit horror:

```html
<sup id="fnref-30-1"><a href="#fn-30-1" rel="footnote">1</a></sup>
```

```html
<div class="footnotes">

<hr />

<ol>
	<li id="fn-30-1">Kim Zetter, “Iran: Computer Malware Sabotaged Uranium Centrifuges,” Wired.com Threat Level, November 29, 2010, http://www.wired.com/threatlevel/2010/11/stuxnet-sabotage-centrifuges/. <a href="#fnref-30-1" rev="footnote">↩</a></li>
</ol>
```

Since part of the joy of having a blog should be authoring my content in whatever format suits me best, this lack of support demonstrates a fundamental misunderstanding of my needs and drove me to look for alternatives.

### Jetpack Dependency

Another reason to contemplate discontinuing the use of Jetpack is that it's a fairly [heavy dependancy](https://afearlessventure.com/blog/worried-about-site-speed-take-a-hard-look-at-jetpack/) with plenty of its share of [tech debt](https://github.com/Automattic/jetpack/issues/13048#issuecomment-512674269), just to only halfway support a Markdown feature that I feel should have been native in Gutenberg from the start. It does look like there is a lot of work going on to support [markdown in Gutenberg](https://github.com/Automattic/jetpack/issues/9201) and to [add footnotes support to blocks](https://github.com/WordPress/gutenberg/issues/1890) in the future. But I wasn't going to wait.

## WordPress Site vs. Static Site

It's not really a fair comparison, as there are many differences between what each kind of publishing system can accommodate in terms of editor experience, or personalized content. With WordPress, you're starting from a fully WYSIWYG editorial workflow integrated within the application, and producing a dynamically generated website utilizing this world-class content management system. Underlying this software is a thick stack of PHP application servers, databases, and file systems, and of course an operating system. With Hugo and GitLab Pages, you're moving to a Markdown formatted editorial experience driven by a Git and CI/CD workflow in order to generate static HTML and asset files that are served by a simple webserver with minimal configuration potential. There are a lot of security and performance metrics that will be affected by such a move, most of them in a positive direction. You're no longer worrying about OS and PHP security patches and optimizing the configuration and implementing caching at all levels to achieve a decent server response time, even if you were using managed services to mitigate a lot of the human toil involved in making that happen. Rather, this concern almost completely disappears. Instead, it's a matter of ensuring you have a development workflow following security best practices, and a fast CI/CD platform to deploy your project quickly. I think I've found that magical combination with GitLab Pages and Hugo, which I ultimately chose as the new solution for publishing my blog.

## Hugo

### Installing Hugo

brew install hugo
dependencies: go

### Starting With Hugo Academic Kickstart

[Academic Kickstart](https://github.com/sourcethemes/academic-kickstart)


### Planning Content Organization

### Customizing Hugo Academic Kickstart

## Hosting on GitLab Pages

https://gohugo.io/hosting-and-deployment/hosting-on-gitlab/

https://about.gitlab.com/2016/04/07/gitlab-pages-setup/

[What is GitLab Pages?](https://about.gitlab.com/product/pages/)

### Adding GitLab Project

### Configuring GitLab Pages

[GitLab Pages Documentation](https://docs.gitlab.com/ee/user/project/pages/)

[Exploring GitLab Pages](https://docs.gitlab.com/ee/user/project/pages/introduction.html)

### Adding .gitlab-ci.yml for Hugo

[GitLab Pages Hugo example](https://gitlab.com/pages/hugo)

Build site with Hugo extended.
Workaround for pages/hugo#32 bug
Git executable not found in $PATH
https://gitlab.com/pages/hugo/issues/32

```yaml
before_script:
  - apk add --update --no-cache git
```

## Migrating WordPress Posts

https://sourcethemes.com/academic/docs/migrate-from-wordpress/

### Installing WordPress to Jekyll Exporter Plugin
https://wordpress.org/plugins/jekyll-exporter/

### Importing Site Content Into Hugo
https://sourcethemes.com/academic/docs/migrate-from-jekyll/


## Writing with Hugo Academic

https://sourcethemes.com/academic/docs/writing-markdown-latex/