# R Markdown

## CSS tricks

*Add in the body of `.Rmd`*

To change the style of blockquotes:
```
<style>
blockquote p {
  font-size: 14px;
  color: #86BC25;
}
</style>
```

To justify text:
```
<style>
body {text-align: justify}
</style>
```

Add some vertical space:
```
<br/>
```

## Other

Use [`knit_exit()`](https://stackoverflow.com/a/33711413) to stop knitting of a large document at a given place.

## Links

- [Add task lists in R Markdown](https://github.com/jgm/pandoc/wiki/Pandoc-Tricks#via-lua-filter).
- [How to include a logo in RMarkdown HTML](https://stackoverflow.com/a/43010632).
