---
title: Contributing to the NPPS Web Site
author: Michel Jouvin, Torre Wenaus
layout: default
---

# Contributing to the NPPS Web Site
{:.no_toc}

* auto-gen TOC:
{:toc}

*This documentation was originally written by Michel Jouvin for the HSF website. Adapted slightly by Torre Wenaus for NPPS.*

The NPPS web site is hosted by [GitHub Pages](https://pages.github.com) which relies on a framework called 
[Jekyll](https://jekyllrb.com). This page documents a few useful hints that help contributing to the web site 
and assessing the result of your contributions. Refer to the linked documentations for details about [
GitHub Pages](https://pages.github.com) and [Jekyll](https://jekyllrb.com).

The website source is in the [BNL NPPS GitHub](https://github.com/BNLNPPS), repository [BNLNPPS.github.io](https://github.com/BNLNPPS/BNLNPPS.github.io).

## Content Format

Jekyll expects the web site contents to be written in [Markdown](https://guides.github.com/features/mastering-markdown/), file type `.md`, with 
a special section at the beginning of the file called `frontmatter`. This section contains attribute definitions used to render the file. It is delimited by a pair of `---` lines. A typical frontmatter section is:

```
---
title: Contributing to the NPPS Web Site
author: Michel Jouvin
layout: default
---
```

After the frontmatter section, write the rest in markdown (or generate markdown from another format, see below).

Note however that it works just as well to write html files, with the same `frontmatter` section.

Jekyll uses the [Liquid](https://shopify.github.io/liquid/) template language, with some Jekyll extensions, which supports convenient features like includes. Browse the `_includes` directory in the website source to see how they are used on this site.


### File Name Format

Markdown files are organized by categories: events, newsletter, organization (meeting notes)...
Markdown files in these categories are stored in a `_post` subdirectory. Jekyll expects the markdown file names 
in these `_post` directories to follow the following convention:

```
YYY-MM-DD-some-text.md
```

with:

* `YYYY`: the year
* `MM`: the month number
* `DD`: the day number


### Adding a TOC

To generate a table of contents of the file, you need to add the following lines where you want to insert it:

```
* auto-gen TOC:
{:toc}
```

If you don't want a heading, for example the page title (heading level 1), to be inserted into the TOC, you need to insert the following line right after the heading:

```
{:.no_toc}
```

Look at the source of this page for an example.


### Converting Contents from Word or GoogleDoc

[pandoc](http://pandoc.org) is the swiss-army knife for the conversion between text formats. In particular it supports a very good conversion from Microsoft Word (`docx`) format to Jekyll markdown. The typical command to do this conversion is:

```
pandoc -t markdown_github --base-header-level=2 --atx-headers -o organization/_posts/2016-05-19-startup.md document.docx
```

This method can be used to convert a GoogleDoc document to markdown. To do it, use the GoogleDoc menu `File->Download as` and export the GoogleDoc document as a `docx` file. Then use the command above to convert to markdown.


### Inserting images

To insert an image, add it (as a PNG or JPEG file) to the `images` directory. Then in the page where you want to insert
it, add the following line:

```
![Replacement text](/images/file){:height="400px" width="600px" .centered-image}
```

where:

* `Replacement text` is the text displayed when the cursor is on the image and the image cannot be displayed.
* `/images/file` is the path to the image file, relative to the top directory of the web site. Images are typically in
`/images` directory.
* `{...}` are optional rendering instructions, using CSS attributes. `height` and `width` are used to define the size of the
rendered image (whatever is its orignal size), `px` meaning the unit is pixel. `.centered-image` is a CSS class that
allows to center horizontally the image (everything starting with a `.` is interpreted as a CSS class, typically defined
into `css/npps.css`).

## Checking the Results of Your Contribution

It is often desirable to assess the result of changes before publishing them. There is no services at GitHub to do that: 
you can only render the markdown contents, without all the CSS and other things. To achieve this, you need to install 
Jekyll on your local machine. Detailed instructions can be found on Jekyll [web site](https://jekyllrb.com/docs/installation/) 
but the short story is:

* Install [Ruby](https://www.ruby-lang.org/en/downloads/) and [RubyGems](https://rubygems.org/pages/download)
* Install Bundler (a Ruby package manager):

  ```bash
  gem install bundler
  ```

* If you don't have one yet, create a clone of the GitHub NPPS web site repository and move to the directory created (by default `BNLNPPS.github.io`):

  ```bash
  git clone https://github.com/BNLNPPS/BNLNPPS.github.io.git
  cd BNLNPPS.github.io
  ```

* Install/update your Jekyll installation (must be done regularly):

  ```bash
  bundler update
  ```

* Run Jekyll installation:

  ```bash
  bundler exec jekyll serve
  ```


Once Jekyll has been started you can view the web site by connecting to `localhost:4000`.
Changes made to files are immediately reflected on the displayed site (at the next page load). This makes it extremely efficient to make changes and debug entirely locally before uploading the final changes to GitHub.

At this point, pushes are allowed for site developers. A pull request/approval process may be put in place later if needed.

## Preview builds with Netlify

A 2025 update: [Netlify](https://www.netlify.com/) is a service that can be used to preview your changes to the site without needing to install Jekyll locally. It can be set up to automatically build the site from the GitHub repository and provide a preview URL. You can set up a personal account for free and have it build previews of your PRs. You may have to tweak your Gemfile to have Ruby build correctly (as always necessary with Ruby).
