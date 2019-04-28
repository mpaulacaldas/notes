# Useful functions that I often forget exist

*In alphabetical order*

- [`knitr::knit_exit()`](https://www.rdocumentation.org/packages/knitr/versions/1.19/topics/knit_exit) to stop knitting at a given line of an `.Rmd` document. Originally found  [here](https://community.rstudio.com/t/from-rstudio-is-it-possible-to-knit-only-part-of-an-r-markdown-document/6475/14) and [here](https://stackoverflow.com/questions/33705662/how-to-request-an-early-exit-when-knitting-an-rmd-document).

- `base::lengths(x)` is equivalent to `purrr::map_int(x, length)`

- [`pryr::object_size()`](http://adv-r.had.co.nz/memory.html)

- Convert a character string to numeric, when `,` is used as a decimal mark:

    ```r
    readr::parse_number(x, locale = locale(decimal_mark = ","))
    ```

- Remove all columns with only NAs:

    ```r
    dplyr::select_if(df, ~ ! all(is.na(.)))
    ```

