# Recipes

-  Convert a character string to numeric, when `,` is used as a decimal mark.

  ```r
  parse_number(x, locale = locale(decimal_mark = ","))
  ```

- Remove all columns with only NAs:

  ```r
  select_if(df, ~ ! all(is.na(.)))
  ```

- `lengths(x)` is base R's equivalent to `map_int(x, length)`


# Other useful functions

- [`pryr::object_size()`](http://adv-r.had.co.nz/memory.html)
- [`knitr::knit_exit()`](https://www.rdocumentation.org/packages/knitr/versions/1.19/topics/knit_exit) to stop knitting at a given line of an `.Rmd` document. Originally found  [here](https://community.rstudio.com/t/from-rstudio-is-it-possible-to-knit-only-part-of-an-r-markdown-document/6475/14) and [here](https://stackoverflow.com/questions/33705662/how-to-request-an-early-exit-when-knitting-an-rmd-document).
