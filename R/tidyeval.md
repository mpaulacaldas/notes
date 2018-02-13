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
  - `!!` is called unquote, pronounced "bang-bang". It can be used inside `expr()`
4. __Quote + unquote__
  - Inside a wrapper function: First, __quote__ the variables with `enexpr()` and then __unquote__ them with `!!` to pass them along.
  - Be careful with the environment! The variables defined _inside_ the function call will have precedence over the ones from the global environment. [See example in 4:41](https://youtu.be/nERXS3ssntw?t=4m21s)
5. __Quosures__ capture expression & environment
  - `enquo()` captures the user's expression and its environment. 
  - Therefore, one should use `enquo()` instead of `enexpr()` in a wrapper function.

My questions:

- Is there any situation where we would want to use `enexpr()` instead of `enquo()`?

## TODO

Check out these resources and take some notes: 

- [Advanced R, section IV](https://adv-r.hadley.nz/meta.html)
- [Programming with dplyr](http://dplyr.tidyverse.org/articles/programming.html)
- [This blog post](https://edwinth.github.io/blog/dplyr-recipes/)