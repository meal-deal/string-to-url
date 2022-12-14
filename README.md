<p align="center">
    <img src="logo.png" width="250">
</p>

# What is StringToURL? 

[StringToURL](https://hot-meal.github.io/string-to-url/) is a pastebin-like app that allows you to share any text-based file as an encrypted URL.

Your data is not stored anywhere but the link itself. No databases, logs or any other permanent record beside the Link you have only.

### This means:

- Your links cannot be deleted.
- Your links cannot be censored.
- Your links are accessible forever.
- Google cannot index your data as it is obscured within the link.

## How it works

It uses the [LZMA algorithm](https://en.wikipedia.org/wiki/Lempel%E2%80%93Ziv%E2%80%93Markov_chain_algorithm), then encodes it with [Base64](https://en.wikipedia.org/wiki/Base64).

When you open a link, StringToURL reads, decodes, then decompresses whatever is after the `#` in the URL.

This is done entirely **in browser**, and the web server hosting StringToURL never has access to your data.

### Embedded StringToURL snippets

You can include StringToURL code snippets into your own website by clicking the _Embed_ button and using the generated HTML code.

Here is an example of generated code and how it looks (click on the screenshot to see the interactive version)

```html
<iframe
    width="250"
    height="250"
    frameborder="0"
    src="https://hot-meal.github.io/string-to-url/#XQAAAQAxAQAAAAAAAAAmG8pGZ1ryd7h9hoRflit8ct5gajQnTXx9c3swhoQps2M58+m1uzfhI+D8foaB1aKZaMHh6ZaCSAeHI8FpM+Xr/aItZkvcdblf9mBLvbPTqd6YJLrYLJQQtlcDDPbtzbMLMYTVNiDfbTzI9xuzRUa0QUniHw0bBDuH/yR2OSuW5X5VgL627HgBLr/oa2N+g7LhcjMDuYS7WSiBMmCwvJZvQyX5BfJkn/C7Tj5o3QaU+NoYaq4rifHLOQfeB4H0T989GzRUbQZB0ip1dZ/pCebwlfcuM1X8/SKzBhGd35908J0dIIsP6//2039Y"
></iframe>
```

### Offline

StringToURL uses pre-caching and localstorage to ensure that it works offline, if you need it. Even without an internet connection.


### Editor

-   Syntax highlighting with language selector
-   Line wrapping 
-   Delete a line (`Ctrl+D`)
-   Multiple cursors (`Ctrl+Click`)
-   Usual keyboard shortuts (`Ctrl+A`, `Ctrl+Z`, `Ctrl+Y`...)

## Maximum lengths for links

These are the maximum link lengths on some apps and browsers.

| App     | Max length |
| ------- | ---------- |
| Reddit  | 10,000     |
| Twitter | 4,088      |
| Slack   | 4,000      |
| QR Code | 2,610      |
| Bitly   | 2,048      |

| Browser         | Max length                | Notes                                   |
| --------------- | ------------------------- | --------------------------------------- |
| Chrome   | (win) 32,779 (mac) 10,000 | Will not display, but works |
| Firefox         | >64,000                   |                                         |
| IE 11 | 4,043                     | Will not display more than 2,083           |
| Edge  | 2,083                     | Anything above 2083 will fail            |
| Android         | 8,192                     |                                         |
| Safari          | Lots                      |                                         |

## Generate StringToURL links

StringToURL links can also be from your computers command line: 

```bash
# Linux
echo -n 'Hello World' | lzma | base64 -w0 | xargs -0 printf "https://hot-meal.github.io/string-to-url/#%s\n"

# Mac
echo -n 'Hello World' | lzma | base64 | xargs -0 printf "https://hot-meal.github.io/string-to-url/#%s\n"

# Windows Subsystem for Linux
echo -n 'Hello World' | xz --format=lzma | base64 -w0 | printf "https://hot-meal.github.io/string-to-url/#%s\n" "$(cat -)"
```

## Cloning

Feel free to fork or clone this project. Any StringToURL link can be opened on any fork of this project. It is 100% cross-compatible.