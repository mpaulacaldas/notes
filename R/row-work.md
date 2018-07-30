# Row-oriented workflows with R

[Video](https://www.rstudio.com/resources/webinars/thinking-inside-the-box-you-can-do-that-inside-a-data-frame/), [repo](https://github.com/jennybc/row-oriented-workflows) and [slides](https://speakerdeck.com/jennybc/row-oriented-workflows-in-r-with-the-tidyverse?slide=1).

## Pro-tip #1: Use vectorized functions.

- It is easy to forget that a lot of functions in R are already vectorized.
- Try to vectorize your own functions over the primary argument.
  - *e.g. I did this today to fetch travel distances from the Google Distance Matrix API.*
- See [here](https://dcl-2018-01.github.io/curriculum/vector-functions.html) for more examples on vector and scalar functions.
  - *Sneak-peek: `str_detect()` is vectorised over both `string` and `pattern`!*

## Pro-tip #2: Use `purrr::map()` and friends.

- `pmap(.l, .f, ...)`: for every tuple in `.l` apply `.f`.
- A tuple is a list of lists that have the same length
  - *You know, like data frames!*
- What if you need to map your function over more than 2 but not all of the columns in your data? Use `...` :sparkles: Metioned [here](https://community.rstudio.com/t/dplyr-alternatives-to-rowwise/8071/8) and [here](https://github.com/jennybc/row-oriented-workflows/blob/master/ex06_runif-via-pmap.md#extra-variables-in-the-data-frame).

## Pro-tip #3: Use `dplyr::group_by()` + `dplyr::summarize()`

- To return summaries that **are not** a single number, create a list-column! (You can later get rid of it with `map(.x, enframe)` + `unnest()`).

```r
# From ex07_group-by-summarise.R
iris %>%
  group_by(Species) %>%
  summarise( pl_qtile = list(quantile(Petal.Length, c(0.25, 0.5, 0.75))) )
```

- Although it may feel akward, also try to use `dplyr::group_by()` + `tidyr::nest()`.


## Extras

- [Row-wise summaries](https://github.com/jennybc/row-oriented-workflows/blob/master/ex09_row-summaries.md). The entire example is just :fire: Also, I had no idea about `purrr::lift_vd()`, and I don't think I would have understood *why* I might need it if I had stumbled upon it on my own.