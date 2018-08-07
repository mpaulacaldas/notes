# CSS

## From Datacamp's "Communicating with data in the Tidyverse"

CSS stands for _Cascading Style Sheets_.

__CSS specifies rules for HTML tags.__ For example, to set the colour of the level 1 heading, we would write something like:

```css
h1 {
  color: red;
}
```

We can add __class selectors__ that give us exceptions to predefined rules:

```css
/* In the .css file */
strong {
  color: black;
}

strong.pink {
  color: pink;
}
```

```HTML
<!-- In the .html -->
I <strong> love </strong> <strong class = "pink"> pink </strong>
```

__CSS combinators__ can be used to customise the elements of an HTML with respect to the nested structure of the tags.

```css
/* Sets the colour to black for any strong tag inside a div tag, no matter how deeply nested it is*/
div strong {
  color: black
}
/* Sets the colour to back of any strong tag directly under a div tag */
div > strong {
  color: purple
}
```

For more info, check out the [Mozilla developer reference](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals).

Other things to keep in mind:

- Do not wrap the name or hex value of colours in quotation marks.
- R code elements in RMarkdown are wrapped in `pre` tags.
- Hyperlinks are wrapped in an `a` selector. `a:hover` defines the style of the link when you hover your mouse over it (see [this example](https://www.w3schools.com/cssref/sel_hover.asp)).

## Examples

See [here](R/rmarkdown.md)
