---
layout: post
title: Syntax Highlighting with Prism in Jekyll
date: 2019-11-19
categories:
- technical
- blogging
tags:
- jekyll
- blog
status: publish
type: post
published: true
author: BRG
thumbnail_path: blog/syntaxhighlight/banner.png
cover_img: blog/syntaxhighlight/banner.png
---

{% include blogs/opening-para.html
            para="Code readability has become one of the important topic in the programming world in the
            past few years. People have started to realize its importance from the perspective of overall software development. A readable code is much easier to understand and easily adoptable by any
            developer. It gives a easy path for newcomer to dive into the development.
            <br>
            Syntax highlighting is the feature of displaying certain text specially source code in different
            colors and fonts to 'stand out' from the rest of the code. It is \"must have\" feature for text editor."
%}

In this blog, I am going to share my experience of implementing syntax highlighting using
[Prism](https://prismjs.com/) in [Jekyll](https://jekyllrb.com). Prism is a JavaScript based lightweight, extensible syntax highlighter and
built with modern web standards in mind. Apart from the core features of supporting many different
languages, pure CSS based syntax highlighting, wide browser support, I really liked the plugins it provides
to enhance the syntax highlighting ability. Out of many, I liked the plugins like [`Command Line`](https://prismjs.com/plugins/command-line/), [`Copy to Clipboard Button`](https://prismjs.com/plugins/copy-to-clipboard/), [`Download Button`](https://prismjs.com/plugins/download-button/) and
[`Diff Highlight`](https://prismjs.com/plugins/diff-highlight/). I feel, these will really going to help my
readers to easily read the code snippet and test at their end.

#### What I achieved using Syntax Highlighting

First of all, let's see how adding syntax highlighting totally changed the look and feel of the code snippets in my blog.

{% include multi-image.html
           img1="/blog/syntaxhighlight/old.png"
           caption1="Syntax Highlight with no CSS"
           img2="/blog/syntaxhighlight/new.png"
           caption2="Syntax Highlight with Prism"
%}

## I hope you found the second one more readable than the first one.

The first one is my old syntax highlighting with Jekyll's default highlighter `Rouge` which lacks the proper
highlighting theme.

Read [`Syntax Highlighting in Jekyll with Rouge`](https://sangsoonam.github.io/2019/01/20/syntax-highlighting-in-jekyll.html) in order to use the Jekyll's default highlighter.

### How to use Prism

#### Step 1: Add the required CSS and JS files

Get the required CSS and JS files from the [Prism's website](https://prismjs.com/) and place it
into your assets folder. Choose the required plugins as per your choice.

I added into `assets/css/prism.css` and `assets/js/prism.min.js`. Then, added the required lines to load these files

```html
<link rel="stylesheet" href="{{ "/assets/css/prism.css" | relative_url }}">

and

<script type="text/javascript" src="{{ "/assets/js/prism.min.js" | relative_url }}"></script>
```

#### Step 2: Using the Prism.js syntax highlighter in post

Just wrap the code with triple backticks or pass the language to use language specific syntax
highlighting.

{% highlight raw %}
```javascript
Some code.
```
{% endhighlight %}

{% include blogs/ending-note.html
           para="Congratulations! Now you have Prism.js based syntax highlighting."
%}
