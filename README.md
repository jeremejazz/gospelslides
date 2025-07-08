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

```sh

hugo new content article/article-name/index.md
```

### New Presentation
```sh
hugo new content presentations/your-slideshow/index.md
```

### New Page

```
hugo new content pagename.md
```


### Front Matter

```toml
[reveal_hugo]
  custom_css="custom.css" # should be same folder or relative to index.md
  theme = "white" # refer to the filenames in static/lib/reveal-js/dist/theme

languageCode = "en" # language code
```

## Presentations

A custom content type has been added called presentations. This uses RevalJS

### Markdown


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


## Shortcodes

### fragment
Implementation of [Fragments](https://revealjs.com/fragments/).
```
{{< fragment >}}
"Not of works, lest any man should boast."  
<br/>
— Ephisians 2:9
{{< /fragment >}}
```

### slide

Customize the current slide

```md
---

{{< slide id="hello" background="#FFF" transition="zoom" transition-speed="fast" >}}

# Hello, world!

---

```

