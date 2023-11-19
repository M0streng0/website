---
author: 
  name: "Henrique Oliveira"
title: Why create a website?
date: 2023-11-19
type: ["posts"]
categories: ["Random"]
tags:
  - why
draft: false
---
**Here are some reasons:**
- To use it as a portfolio
- To be able to share content
- To learn new things, such as
  - Hugo (static website generator)
  - To develop HTML and CSS a little better
  - Getting back to using JavaScript
  - Cloudflare (Pages)
- Being able to write and translate in different languages (EN - FR - PT)

## How was the site created?
Now that you know more about why I decided to create a website, I'll tell you how I did it...

### Hugo

I've always been interested in having a website in my name, but I've never really wanted to constantly create and modify HTML, CSS and some JS files whenever I wanted to add something new...

So what's the best solution?

[**HUGO**](https://gohugo.io/) - A static site generator, which means that it helps you create sites with pre-built HTML, CSS and JavaScript files, instead of generating pages dynamically on the server. You only need to use Markdown to build each web page, and everything is very modular.

A good video I recommend is that of Chris Titus, who talks about his approach with Hugo

{{< youtube id="xMv10E561WQ" >}}

### Hugo - Appearance

A great advantage of using Hugo is that you can find dozens and dozens of website themes with all the files already pre-built, which is spectacular! [Where you can find themes...](https://themes.gohugo.io/)

But I like to learn how to do it, so I took a theme I liked ([hello-friend-ng](https://themes.gohugo.io/themes/hugo-theme-hello-friend-ng/)), and customized it my way...

- I changed the colors to my preferred color palette ([Nord](https://www.nordtheme.com/))
- I created new HTML, CSS and JS files to better achieve what I wanted! Such as:
  - Photo gallery that adapts to the size of each image.
  - Text in columns (visible on the [About Me](https://m0streng0.com/about/) page).
  - Added math language rendering functionality.

If you're interested in my theme, you can see the files on [Github](https://github.com/M0streng0/website)

But the whole of the original page has been preserved, as it was already very well done!

### Cloudflare Pages

The next step was to find out where to host the website... I'd already tried Github Pages, hosting on an Amazon AWS VPS, but I'd never tried Cloudflare Pages.

Let me say that for a free service it's _**INCREDIBLE**_... Cloudflare Pages' approach is similar to the experience I had with Github Pages, but with many more features!

Once again, to learn about the relationship between Hugo and Cloudflare Pages, I once again recommend a video by Chris Titus (he 100% deserves all the recognition he can get!)

{{< youtube id="Cfr4YNbKrB8" >}}