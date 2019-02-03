Takeaways from rstudio::conf2019
================

*From the webinars, because I did not attend* :sob:

## R Markdown

### Advanced R Markdown Workshop, Yihui Xie and Alison Hill

[Website](https://arm.rbind.io/) [Video](https://youtu.be/6JX4UNxEOLU)

#### Part I: Customizing R Markdown

#### Part II: R Markdown extensions

## Tidy eval

### Tidy eval in context, Jenny Brian

[Repo](https://github.com/jennybc/tidy-eval-context#readme),
[Video](https://resources.rstudio.com/rstudio-conf-2019/lazy-evaluation)

You may **not** need tidy eval. Most people don’t need to make direct
use of
[rlang](https://rlang.r-lib.org/).

| You want to …                                      | You need to know this much tidy eval |
| -------------------------------------------------- | ------------------------------------ |
| Write simple functions to reduce duplication       | Pass the dots, `enquo()`, `!!`       |
| Write functions that make names from user input    | `:=`                                 |
| Compute on expressions and manipulate environments | Know the theory + rlang              |

### Working with names and expressions in your tidy eval code, Lionel Henry

[Slides](https://speakerdeck.com/lionelhenry/selecting-and-doing-with-tidy-eval),
[Video](https://resources.rstudio.com/rstudio-conf-2019/working-with-names-and-expressions-in-your-tidy-eval-code)

#### Context

There are two dplyr flavours:

  - Action verbs: `mutate()`, `transmute()`, `summarise()`, `group_by()`
  - Selection verbs: `select()`

Use scoped dplyr verbs (e.g. `group_by_at()`) to pass selections to
action verbs.

#### “Passing the dots” strategies

1.  Selections with dplyr
    
    ``` r
    summary_functions <- list(
      ~ mean(., na.rm = TRUE),
      ~ sd(., na.rm = TRUE)
    )
    
    # Pass the dots!
    summarise_sels <- function(.data, ...) {
      summarise_at(.data, vars(...), summary_functions)
    }
    
    
    starwars %>% 
      summarise_sels(height:mass)
    ```
    
        ## # A tibble: 1 x 4
        ##   height_mean mass_mean height_sd mass_sd
        ##         <dbl>     <dbl>     <dbl>   <dbl>
        ## 1        174.      97.3      34.8    169.

2.  Actions with dplyr
    
    ``` r
    # Pass the dots! 
    summarise_act <- function(.data, ...) {
      .data %>% 
        transmute(...) %>% 
        summarise_all(summary_functions)
    }
    
    starwars %>% 
      summarise_act(
        heightm = height / 100,
        bmi = mass / heightm^2 
      )
    ```
    
        ## # A tibble: 1 x 4
        ##   heightm_mean bmi_mean heightm_sd bmi_sd
        ##          <dbl>    <dbl>      <dbl>  <dbl>
        ## 1         1.74     32.0      0.348   54.9

3.  Gather with tidyr
    
    ``` r
    gather_summarise_act <- function(.data, ...) {
      .data %>% 
        transmute(...) %>% 
        gather("Variable", "Value", -one_of(group_vars(.))) %>% 
        summarise_at(vars(Value), summary_functions)
    }
    
    starwars %>% 
      group_by(gender) %>% 
      gather_summarise_act(
        heightm = height / 100,
        bmi = mass / heightm^2 
      )
    ```
    
        ## # A tibble: 5 x 3
        ##   gender          mean     sd
        ##   <chr>          <dbl>  <dbl>
        ## 1 female          8.01   8.73
        ## 2 hermaphrodite 223.   312.  
        ## 3 male           12.0   12.6 
        ## 4 none           18.5   23.3 
        ## 5 <NA>           16.5   17.0

#### Takeaways

  - “Passing the dots” strategies with dplyr (selection *and* actions)
    work easily with gouped data.

  - For other functions, like `tidyr::gather()`, we need to deal with
    the grouping variables inside the function.

  - New discovery:
    [`dplyr::group_vars()`](https://dplyr.tidyverse.org/reference/groups.html)
