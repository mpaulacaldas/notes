# Recipes

Convert a character string to numeric, when `,` is used as a decimal mark.

```r
parse_number(x, locale = locale(decimal_mark = ","))
```

Remove all columns with only NAs:

```r
select_if(df, ~ ! all(is.na(.)))
```

# Other useful functions

- [`pryr::object_size()`](http://adv-r.had.co.nz/memory.html)
- [`dplyr::pull()`](http://dplyr.tidyverse.org/reference/pull.html) to pull out a variable from a tibble as a vector. Same the thing as `... %>% .$varname`, but perhaps more stylish.
- [`knitr::knit_exit()`](https://www.rdocumentation.org/packages/knitr/versions/1.19/topics/knit_exit) to stop knitting at a given line of an `.Rmd` document. Originally found  [here](https://community.rstudio.com/t/from-rstudio-is-it-possible-to-knit-only-part-of-an-r-markdown-document/6475/14) and [here](https://stackoverflow.com/questions/33705662/how-to-request-an-early-exit-when-knitting-an-rmd-document).
