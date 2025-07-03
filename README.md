# Gospel Slides

Sharing gospel tracts with RevealJS Slides.

This site uses the [blowfish](https://github.com/nunocoracao/blowfish) theme while also 
implementing some code copied from Hugo Blox Builder and reveal-hugo.



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





## Setup

1. Clone the repository

2. Install [hvm](https://github.com/jmooring/hvm)
Then run the following
```sh
hvm status  
```
running status will prompt if you want to install the version specified in the `.hvm` file.

If the installation process is too complicated install Hugo instead but be sure to install the specific version `v0.147.9`. Be sure to use the extended version (`hugo_extended`);

3. To run locally

```
hugo server -D 
```

In your browser, run `localhost:1313` which should be also indicated in the terminal.

## Creating new content

### New Presentation
```sh
hugo new content presentations/your-slideshow/index.md
```

### New Page

```
hugo new content pagename.md
```


