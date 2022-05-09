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
draft: false

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
“Iranian President Mahmoud Ahmadinejad said [in November 2010] that malicious computer code launched by “enemies” of the state had sabotaged centrifuges used in Iran’s nuclear-enrichment program.”<sup id="fnref-30-1"><a href="#fn-30-1" rel="footnote">1</a></sup>
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

It's not really a fair comparison, as there are many differences between what each kind of publishing system can accommodate in terms of editor experience, or personalized content. With WordPress, you're starting from a fully WYSIWYG editorial workflow integrated within the application, and producing a dynamically generated website utilizing this world-class content management system. Underlying this software is a thick stack of PHP application servers, databases, and file systems, and of course an operating system. With Hugo and GitLab Pages, you're moving to a Markdown formatted editorial experience driven by a Git and CI/CD workflow in order to generate static HTML and asset files that are served by a simple webserver with minimal configuration potential. There are a lot of security and performance metrics that will be affected by such a move, most of them in a positive direction. You're no longer worrying about OS and PHP security patches and optimizing the configuration and implementing caching at all levels to achieve a decent server response time, even if you were using managed services to mitigate a lot of the human toil involved in making that happen. Rather, this concern almost completely disappears. Instead, it's a matter of ensuring you have a development workflow following security best practices, and a fast site building platform to generate your project quickly. I'd found that magical combination with GitLab Pages and Hugo, which I ultimately chose as the new solution for publishing my blog.

## Hugo

Why [Hugo](https://gohugo.io/), you might ask? Hugo is built with Go, which is known for having a fast runtime. I'd used Jekyll (Ruby) and Sculpin (PHP) previously, but both generators were slow to build large amounts of content. Another compelling reason for using Hugo was the large ecosystem of themes and starter kits, a passionate user community, and extensive documentation built around the project that would surely would make it easier for developers like me to get up and running, and find support when I had any issues.

### Installing Hugo

First thing's first: getting Hugo installed. Assuming you're using Homebrew (you ARE using [Homebrew](https://brew.sh/), aren't you?!?) 

```
brew install git golang hugo
```

{{% callout note %}}
Dependencies: go, git
{{% /callout %}}

You'll want to make sure to follow any specific instructions provided by Homebrew about completing the installation & configuration of `go`, including appending the binary location to the `PATH` in your shell configuration.

### Starting With Hugo Academic Kickstart

To make life a lot easier, I used the [Academic Kickstart](https://wowchemy.com/docs/getting-started/), which provided a script that gets you up and running with a very nice looking academic portfolio, and supported all the features I needed out of the box.

{{% callout note %}}
Hugo Extended is required for building your site with Academic Kickstart.
{{% /callout %}}

First I cloned the repository to my local dev system:

```
git clone git@github.com:sourcethemes/academic-kickstart.git
```

Next, I ran the provided script to initialize my new site with a curated assortment of useful homepage widgets and portfolio pages:

```
./scripts/init_kickstart.sh
```

### Customizing Hugo Academic Kickstart

With this framework in place, I was able to alter all the default site configuration, homepage widgets, and other provided examples to suit my needs, and remove or comment out items I didn't need. Here is an example of a custom widget for the homepage Experience section:

```
[[experience]]
  title = "Owner"
  company = "SJA Consulting"
  company_url = "https://www.sjaconsulting.com/"
  location = "Northern California"
  date_start = "1997-06-01"
  date_end = ""
  description = """
  SJA Consulting provides small organizations with comprehensive services from website development to IT consulting. Designing a usable web requires a commitment to high standards of form and function. Specializing in developing aesthetic solutions utilizing open-source technologies, we’ve succeeded in delivering cost-effective systems that are easy to use.

  * Expert Drupal, WordPress, and Hugo implementations, upgrades, maintenance, and support.
  * Custom theme and module development.
  * Usable and secure sites that stand the test of time.
  * Genuine interest in client requirements and user needs.
  """
```

At the end of this process, my site was already looking a lot cleaner, and loading much faster, than it ever did with WordPress. Plus, no more application servers! Like I keep saying: the Easy Button. Use it.

### Planning Content Organization

I had a fairly simple content use case on my WordPress site, primarily consisting of posts and a couple of static images included in some posts. So, all the old content could live under the `/post` folder, and I could use [Cloudflare Page Rules](https://support.cloudflare.com/hc/en-us/sections/200805137-General) to redirect users from the old URLs to the new ones.

## Hosting on GitLab Pages

Getting setup on GitLab to build and host your Hugo site is fairly straightforward with all the great guides. I used these tutorials and documentation to get me up and running and to customize my configuration:

* [Hosting on GitLab](https://gohugo.io/hosting-and-deployment/hosting-on-gitlab/)

* [GitLab Pages Setup](https://about.gitlab.com/2016/04/07/gitlab-pages-setup/)

* [What is GitLab Pages?](https://about.gitlab.com/product/pages/)

* [GitLab Pages Documentation](https://docs.gitlab.com/ee/user/project/pages/)

* [Exploring GitLab Pages](https://docs.gitlab.com/ee/user/project/pages/introduction.html)

### Adding GitLab Project

The first step is to add a project in GitLab. You'll want to choose a good username and project name, as these will be used to access your pages before you assign a custom domain name.

### Configuring GitLab Pages

GitLab Pages needs to be given specific instructions on how to build your particular project using a `.gitlab-ci.yml` GitLab CI (Continuous Integration) configuration file. You have some choices for how to get started. You can fork a sample GitLab Pages project, start with a GitLab Pages project template, create a `.gitlab-ci.yml` file from scratch, or use a template for this type of configuration file. 

### Adding .gitlab-ci.yml for Hugo

Since my site was already built with the Hugo Academic template, it made the most sense to add the GitLab CI configuration file from a template for Hugo built Pages. The [GitLab Pages Hugo example](https://gitlab.com/pages/hugo) got me started, but since the Hugo Academic template required the extended Hugo version, I needed to find a workaround so that I could build my site properly on GitLab Pages, without error. Luckily, I found the [fix documented in this issue](https://gitlab.com/pages/hugo/issues/32):

#### Workaround for pages/hugo#32 bug Git executable not found in $PATH

```yaml
before_script:
  - apk add --update --no-cache git
```

## Migrating WordPress Posts

Now we get to the really fun part: content migration. This was actually quite enjoyable, as I'd done a really good job in planning out the new site structure to accommodate my old site content. The main work was a matter of extracting all the posts I'd written out of the WordPress database, converting my content to Markdown format, and downloading the converted content as text files. Then, I needed to place it all into the correct locations in the new site structure, so that my posts would be built with the Hugo Academic template. Because I chose new URLs at easy-to-redirect locations, I could minimize any "file not found" errors for potential visitors. I had an excellent guide to follow to get the [WordPress to Hugo migration](https://wowchemy.com/docs/import/migrate-from-wordpress/) completed fairly quickly.

### Installing WordPress to Jekyll Exporter Plugin

The main ingredient for the migration is the Jekyll Exporter. Jekyll is a popular static site generator, that, like Hugo, expects MarkDown formatted content. I decided to [install this WordPress to Jekyll Exporter plugin](https://wordpress.org/plugins/jekyll-exporter/) on a development version of my website, with a fresh copy of the production site's database, since it's unnecessary, and arguably dangerous, to install or run any migration from the prod instance. I ended up with a ZIP file of all the site's content in my Downloads folder. It's also possible to run a migration through the commandline using `wp-cli`, and this methodology will be particularly useful if you have a lot of content to export, and don't want to risk a timeout or incomplete dump. Further instructions on how to accomplish this, as well as documentation for more advanced features of the exporter, are located on the WordPress to Jekyll Exporter plugin download page.

### Importing Site Content Into Hugo

Luckily for me, I had found a [very helpful guide](https://wowchemy.com/docs/import/migrate-from-jekyll/) to get me started on the content import portion of my big project. Once all the Markdown files were downloaded, I needed to massage them into place. My posts were inside a `_posts` folder in the ZIP, and each was named with its publish date. I created a new batch of folders under Hugo's `content/post` area, one for each of my blog posts. I named each folder with the post title slug, and each content file was renamed to `index.md`, then placed into its respective folder. For example, `/jekyll-export/_posts/1997-05-27-the-status-of-women-in-computer-science.md` became `/content/post/the-status-of-women-in-computer-science/index.md` and any  associated image content for that post was stored in the same folder as the Markdown file.

I also went to the trouble of editing the front matter of each post to conform to Hugo's standards, while removing any WordPress-specific items. The front matter for the Jekyll Export of one of my articles originally looked like this:

```
---
id: 97
title: How an Equation Changed Warfare
date: 1995-05-01T12:00:36-07:00
author: suzanne
layout: post
guid: https://dev-suzanne.pantheonsite.io/?p=97
permalink: /1995/05/01/how-an-equation-changed-warfare/
layers:
  - 'a:1:{s:9:"video-url";s:0:"";}'
categories:
  - Essays
---
```

You can see in the Hugo header for this migrated article that I've added some additional fields, removed other irrelevant bits, and altered the format of fields like categories in my article's front matter:

```
---
title: 'How an Equation Changed Warfare'
subtitle: ''
summary: ''
authors:
- suzanne
tags:
- technology
categories: [Essays]
date: "1995-05-01T00:00:00Z"
lastmod: "1995-05-01T00:00:00Z"
featured: false
draft: false
---
```

The only modification to my migration process that I would recommend for someone trying to accomplish this for a ton of content would be to alter the Jekyll Exporter code, and ensure that the front data transformations and file naming conventions are tailored for your purposes.

## Writing with Hugo Academic

And that's it! Once your fresh spanking new Hugo site is building without errors, you can go ahead and add new content easily enough. I like using the command line to create posts, so I can just use the following command to add a new post to my blog in my desired organizational structure:

```
hugo new  --kind post post/my-article-name/index.md
```

In order to provide more rich content, it can be useful to study writing with Markdown, including embedding widgets. I found that the Academic theme has a really nice documentation page to help with exactly that:

[Page Elements: Writing content with Markdown, LaTeX, and Shortcodes](https://wowchemy.com/docs/content/writing-markdown-latex/)

## Migration: Conclusion

I hope you've enjoyed taking this WordPress to Hugo journey with me. Since I moved my blog from a hosted application to a static implementation, I've not wasted any more time updating a CMS or plugins, wrestled with tech debt and all its overhead, or worried about getting hacked. All my content and configuration is in code, and backing up my database is just not a thing anymore. I couldn't be any more pleased with the results, and I'll keep you updated on any future migration journeys I might embark upon with this site. Until then, happy migrating!

