# Tidyeval

## Tidyevaluation in 5 minutes

[Link to video](https://www.youtube.com/watch?v=nERXS3ssntw&feature=youtu.be)

Summary of the 5 big ideas presented by Hadley:

1. R code is a tree.
    - Every expression in R has a hierarchical form.
    - Every expression can be written in prefix form.
2. Capture the tree by __quoting__.
    - `expr()` quotes developer's expression.
    - `enexpr()` quotes user's expression.
3. __Unquoting__ makes it easy to build trees.
    - `!!` is called unquote, pronounced "bang-bang" :boom: :boom:. It can be used inside `expr()`
4. __Quote + unquote__
    - Inside a wrapper function: First, __quote__ the variables with `enexpr()` and then __unquote__ them with `!!` to pass them along.
    - Be careful with the environment! The variables defined _inside_ the function call will have precedence over the ones from the global environment. [See example in 4:41](https://youtu.be/nERXS3ssntw?t=4m21s)
5. __Quosures__ capture expression & environment
    - `enquo()` captures the user's expression and its environment.
    - Therefore, one should use `enquo()` instead of `enexpr()` in a wrapper function.

My questions:

- Is there any situation where we would want to use `enexpr()` instead of `enquo()`?

## My examples

`enquo()` + `!!`

```r
model_by_grp <- function(df, grp_var) {

  grp_var_q <- enquo(grp_var)

  df %>%
    group_by(!! grp_var_q) %>%
    nest() %>%
    mutate(
      model  = map(data, my_lm_fun),
      tidy   = map(model, broom::tidy),
      glance = map(model, broom::glance)
    )
}
```

`rlang::sym()` or `as.name()` + `!!`

```r
# Function
model_by_grp <- function(df, grp_vars) {

  grp_vars_q <- rlang::sym(grp_vars)

  df %>%
    group_by(!! grp_vars_q) %>%
    nest() %>%
    mutate(
      model = map(data, my_lm_fun),
      tidy  = map(model, broom::tidy)
    )
}

# Usage
models <- c("var1", "var2", "var3") %>%
  set_names() %>%
  map(~ model_by_grp(my_df, .x))
```

`quos()` + `!!!`

```r
model_by_grps <- function(df, ...) {

  grp_vars_q <- quos(...)

  df %>%
    group_by(!!! grp_vars_q) %>%
    nest() %>%
    mutate(
      model  = map(data, my_lm_fun),
      tidy   = map(model, broom::tidy),
      glance = map(model, broom::glance)
    )
}
```
