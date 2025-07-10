# Gospel Slides

Sharing gospel tracts and stories with implementation of [RevealJS](https://revealjs.com).

This site is powered by Hugo and is using [blowfish](https://github.com/nunocoracao/blowfish) theme and also implementing [Hugo Blox Builder Slides](https://github.com/HugoBlox/hugo-blox-builder) and [reveal-hugo](https://github.com/joshed-io/reveal-hugo).


## Setup

1. Clone the repository

```sh
git clone https://github.com/jeremejazz/gospelslides.git

```

2. Install [hvm](https://github.com/jmooring/hvm)
Then run the following
```sh
cd gospelslides
hvm status  
```
running status will prompt if you want to install the version specified in the `.hvm` file.

If the installation process is too complicated install Hugo instead but be sure to install the specific version `v0.147.5`. Be sure to use the extended version (`hugo_extended`);

3. To run locally

```
hugo server -D 
```

`-D` flag is optional to render draft content. 

In your browser, run `localhost:1313` which should be also indicated in the terminal.

## Creating new content


### New Article 

Standard post content.

```sh

hugo new content articles/article-name/index.md
```

### New Presentation

Presentations are content types with RevealJS integrated.

```sh
hugo new content presentations/your-slideshow/index.md
```

### New Page

Standard content page

```
hugo new content pagename.md
```



## Presentations

This website uses a custom content called `Presentations`, which implements RevealJS. The website automatically converts the content to presentation if created in the `content/presentation` directory.

You can still post standard articles if content is created on a different folder.


### Presentation Front Matter

```toml
+++
title = "Title"
date = 2025-07-07T10:04:54+08:00
lastMod = "2025-07-09"
draft = false

languageCode = "en" # language code. defaults to "en"
summary = "" # to be displayed on the list view
tags = []
categories = []

[reveal_hugo]
  custom_css="custom.css" 
  theme = "white" 
  checkOrientation = false

+++

```

- `languageCode` - if using another language other than `en`
- `reveal_hugo.custom_css` - for using custom css for specific presenation. Relative to permalink.
- `reveal_hugo.theme` - theme based on filename in revealjs [theme directory](static/lib/reveal-js/dist/theme)
- `reveal_hugo.checkOrientation` - check if presenation is in mobile device and in portrait mode. 


### Markdown
Presentations use markdown formatting. Use `---` to divide into sections.
For more information about markdown, refer to this [guide](https://www.markdownguide.org/cheat-sheet/).

HTML tags can alsoo be used for advanced formatting.


```md

# Slide 1

---


First Slide

___

```

### Presentation Controls
- Next: `Right Arrow` or `Space`
- Previous: `Left Arrow`
- Start: `Home`
- Finish: `End`
- Overview: `Esc`


### Shortcodes
Useful shortcodes that could be used in presentations 

#### fragment
Implementation of [Fragments](https://revealjs.com/fragments/).
```
{{< fragment >}}
"Not of works, lest any man should boast."  
<br/>
— Ephisians 2:9
{{< /fragment >}}
```

#### slide

The slide shortcode lets you set custom HTML and Reveal.js attributes for each slide - things like id, class, transition, background just to name a few. The names are the same as Reveal.js but without the 'data-' prefix. ([source](https://github.com/joshed-io/reveal-hugo?tab=readme-ov-file#slide-shortcode))

Add the shortcode above the slide content, below the --- separator. Do not place content inside of the shortcode.


```md
---

{{< slide id="hello" background="#FFF" transition="zoom" transition-speed="fast" >}}

# Hello, world!

---

```


Here's a list of documented slide attributes from the Reveal.js docs:

- `autoslide`
- `state`
- `background`
- `background-color`
- `background-image`
- `background-size`
- `background-position`
- `background-repeat`
- `background-opacity` (Opacity is on a 0-1 scale, by decimal. 0=transparent, 1=opaque.)
- `background-video`
- `background-video-loop`
- `background-video-muted`
- `background-interactive`
- `background-iframe`
- `background-transition`
- `transition` (can have different in and out transitions)
- `transition-speed`
- `notes` (can also use the note shortcode)
- `timing`

### Additional data attributes

[](https://github.com/joshed-io/reveal-hugo?tab=readme-ov-file#additional-data-attributes)

Check MDN for information about how these attributes work.

- data-background-image - URL of the image to show. GIFs restart when the slide opens.
- data-background-size
- data-background-position
- data-background-repeat
- data-background-opacity

You can also pass through your own, a `data-` prefix will be added automatically to each one (except for `id` and `class`).



### HTML slides

[](https://github.com/joshed-io/reveal-hugo?tab=readme-ov-file#html-slides)

If you need to create fancier HTML for a slide than you can do with markdown, just add `data-noprocess` to the <section> element.

```html
<section data-noprocess>
  <h1>Hello, world!</h1>
</section>
```
