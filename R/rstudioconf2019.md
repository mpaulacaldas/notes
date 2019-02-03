-   [R Markdown](#r-markdown)
    -   [Advanced R Markdown Workshop, Yihui Xie and Alison
        Hill](#advanced-r-markdown-workshop-yihui-xie-and-alison-hill)
        -   [xaringan](#xaringan)
        -   [bookdown](#bookdown)
        -   [blogdown](#blogdown)
        -   [Customization and
            extensions](#customization-and-extensions)
-   [Tidy eval](#tidy-eval)
    -   [Tidy eval in context, Jenny
        Brian](#tidy-eval-in-context-jenny-brian)
    -   [Working with names and expressions in your tidy eval code,
        Lionel
        Henry](#working-with-names-and-expressions-in-your-tidy-eval-code-lionel-henry)
        -   [Context](#context)
        -   [“Passing the dots”
            strategies](#passing-the-dots-strategies)
        -   [Takeaways](#takeaways)
-   [Other](#other)
    -   [vctrs, Hadley Wickham](#vctrs-hadley-wickham)

*From the webinars, because I did not attend* :sob:

R Markdown
==========

Advanced R Markdown Workshop, Yihui Xie and Alison Hill
-------------------------------------------------------

[Website](https://arm.rbind.io/)

Topics I don’t cover in this summary:

-   [officer](https://rpodcast.github.io/officer-advrmarkdown)
-   [flexdashboard](https://arm.rbind.io/slides/flexdashboard.html)
-   [learnr](https://arm.rbind.io/slides/learnr.pdf)

### xaringan

*[Slides](https://arm.rbind.io/slides/xaringan.html)*

In the code for slides:

| Term or command                      | What does it do?                                   |
|--------------------------------------|----------------------------------------------------|
| `name: mynameis`                     | Name of slide, useful for cross-referencing.       |
| `class: center, right`               | Sets alignment of the entire slide.                |
| `background-image: url(url/or/path)` | Add background image.                              |
| `layout: true`                       | Will apply layout to all slides. Useful for logos. |
| `???`                                | Presenter notes.                                   |
| `.left[]` `.right[]`                 | Align some text only.                              |
| `.pull-left[]` `.pull-right[]`       | Two-columns.                                       |

Inside the code chucks:

| Term or command                 | What does it do?                |
|---------------------------------|---------------------------------|
| `#<<`                           | Highlight a line of code input. |
| `knitr::kable(format = "html")` | Print a table.                  |

In the chunk options:

| Term or command              | What does it do?                            |
|------------------------------|---------------------------------------------|
| `highlight.output = c(1, 3)` | Highlight lines 1 and 3.                    |
| `highlight.output = 1:3`     | Highlight lines 1 to 3.                     |
| `highlight.output = TRUE`    | Highlight all lines of the output.          |
|                              | Prints and evaluates a previous code chunk. |

YAML options for `output:xaringan::moon_reader:`:

| Example                                 | What does it do?                                               |
|-----------------------------------------|----------------------------------------------------------------|
| `nature:highlightStyle:github`          | Define highlight style option.                                 |
| `nature:highlightLines:true`            | Enable/disable line highlighting.                              |
| `seal:false`                            | First slide will not use the information from the YAML header. |
| `css:[default, rladies, rladies-fonts]` | Use R-Ladies theme.                                            |

Global options:

| Term or command                         | What does it do?         |
|-----------------------------------------|--------------------------|
| `options(knitr.table.format = "html")`  | Knit all tables to HTML. |
| `knitr::opts_chunk$set(fig.retina = 3)` | Makes images clearer.    |

### bookdown

[*Slides*](https://arm.rbind.io/slides/bookdown.html)

In the console:

``` r
# Start a bookdown from a template
bookdown::bookdown_skeleton(getwd())

# Render book
bookdown::render_book('index.Rmd')

# Serve book (powers "Preview book" add-in)
bookdown::serve_book()
```

Other tips:

-   Cross-reference figures with `\@ref{fig:fig-chunk-name}` and tables
    with `\@ref{tab:tab-chunk-name}`
-   It is easy to configure the appearence of the TOC Sidebar by adding
    options to the headers (see [slides
    46-50](https://arm.rbind.io/slides/bookdown.html#46)) or configuring
    the `_output.yml` file ([slide
    51](https://arm.rbind.io/slides/bookdown.html#51)).

In the YAML of the `index.Rmd`:

-   For Github sharing, add `github-repo:mpaulacaldas/repo-name`.
-   Use the `url`, `cover-image` and `description` options to customise
    your [card
    metadata](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/summary).

The `_bookdown.yml`:

-   Gets fed to `bookdown::render_book()`.
-   Output dir is set to `"docs"` to make publishing in Github pages
    easier.

The `_output.yml`:

-   Most arguments get passed to `rmarkdown::html_document()`.
-   Don’t forget to adapt the link in the
    `bookdown::gitbook:config:edit:link:` option so that it points to
    the correnct branch of your book’s repo.

### blogdown

[*Slides*](https://arm.rbind.io/slides/blogdown.html)

Global configurations:

``` r
library(usethis)

edit_r_profile()
options(
  blogdown.new_bundle = TRUE, # allows hugo page bundles
  blogdown.author = "Ada Lovelace",
  blogdown.ext = ".Rmd",
  blogdown.subdir = "blog",
  blogdown.yaml.empty = TRUE,
  blogdown.new_bundle = TRUE,
  blogdown.title_case = TRUE
  )
```

New site:

``` r
library(blogdown)

new_site(
  theme = "jpescador/hugo-future-imperfect", 
  sample = TRUE, 
  theme_example = TRUE, 
  empty_dirs = TRUE,
  to_yaml = TRUE
  )
```

Keep in mind:

-   Don’t touch the `index.Rmd` or the `themes/` directory.
-   Don’t knit, serve site with `blogdown::serve_site()`.
-   Ignore `public/`. Once you serve your site, you can drag this folder
    to Netlify.

Edit `config.toml`:

-   `ignoreFiles`: Copy and paste from R console upon first serve of
    site.
-   `relativeURLS = true` for cloud setup.
-   `enableEmoji = true` obviously.
-   `[params]` for more.

Workflow:

1.  Open project
2.  “Serve site”
3.  “New post”
4.  Write, save.
5.  Commit, push.
6.  On Netlify, *New site from Git &gt; Pick site repo*

### Customization and extensions

[*Slides*](https://slides.yihui.name/2019-rstudio-conf-rmarkdown-workshop.html#1)

WIP

Tidy eval
=========

Tidy eval in context, Jenny Brian
---------------------------------

[Repo](https://github.com/jennybc/tidy-eval-context#readme),
[Video](https://resources.rstudio.com/rstudio-conf-2019/lazy-evaluation)

You may **not** need tidy eval. Most people don’t need to make direct
use of [rlang](https://rlang.r-lib.org/).

<table>
<colgroup>
<col style="width: 30%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th>You want to …</th>
<th>You need to know this much tidy eval</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Write simple functions to reduce duplication</td>
<td>Pass the dots, <code>enquo()</code>, <code>!!</code></td>
</tr>
<tr class="even">
<td>Write functions that make names from user input</td>
<td><code>:=</code></td>
</tr>
<tr class="odd">
<td>Compute on expressions and manipulate environments</td>
<td>Know the theory + rlang</td>
</tr>
</tbody>
</table>

Working with names and expressions in your tidy eval code, Lionel Henry
-----------------------------------------------------------------------

[Slides](https://speakerdeck.com/lionelhenry/selecting-and-doing-with-tidy-eval),
[Video](https://resources.rstudio.com/rstudio-conf-2019/working-with-names-and-expressions-in-your-tidy-eval-code)

#### Context

There are two dplyr flavours:

-   Action verbs: `mutate()`, `transmute()`, `summarise()`, `group_by()`
-   Selection verbs: `select()`

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

-   “Passing the dots” strategies with dplyr (selection *and* actions)
    work easily with grouped data.

-   For other functions, like `tidyr::gather()`, we need to deal with
    the grouping variables inside the function.

-   New discovery:
    [`dplyr::group_vars()`](https://dplyr.tidyverse.org/reference/groups.html)

Other
=====

vctrs, Hadley Wickham
---------------------

[Video](https://resources.rstudio.com/rstudio-conf-2019/vctrs-tools-for-making-size-and-type-consistent-functions)

-   Package aimed at package developers.
-   Base R leads to some **WAT** moments.

    ``` r
    # Dates and date-times give unexpected output and are not consistent.

    today <- as.Date("2018-09-18")
    lunch <- as.POSIXct("2018-09-18 12:00", tz = "Europe/London")

    c(today, lunch)
    ```

        ## [1] "2018-09-18"    "4210867-12-04"

    ``` r
    c(lunch, today)
    ```

        ## [1] "2018-09-18 13:00:00 CEST" "1970-01-01 05:56:32 CET"

    ``` r
    c(lunch)
    ```

        ## [1] "2018-09-18 13:00:00 CEST"

    ``` r
    c(NULL, lunch)
    ```

        ## [1] 1537268400

-   The `vctr` package tries to get rid of them.

    ``` r
    library(vctrs)

    # Forces you to be explicit about the type of output you want
    vec_c(1.5, "x")
    ```

        ## Error: No common type for <double> and <character>

    ``` r
    vec_c(1.5, "x", .ptype = "character")
    ```

        ## [1] "1.5" "x"

    ``` r
    # Nonetheless, pragmatics > philosophy
    fa <- factor("a")
    fb <- factor("b")

    vec_c(fa, fb)
    ```

        ## [1] a b
        ## Levels: a b

    ``` r
    vec_c(fb, fa)
    ```

        ## [1] b a
        ## Levels: b a

    ``` r
    # No unexpected output, like in base R
    c(today, fa)
    ```

        ## [1] "2018-09-18" "1970-01-02"

    ``` r
    vec_c(today, fa)
    ```

        ## Error: No common type for <date> and <factor<127a2>>

-   And makes it easier to create new vector classes.

The **main principles** of the package:

1.  The output type only depends on the types of the arguments.

    ``` r
    # It's hard to guess the type of output returned by base::ifelse()
    typeof(ifelse(NA, 1, "a"))
    typeof(ifelse(TRUE, 1, "a"))
    typeof(ifelse(FALSE, 1, "a"))
    ```

        ## [1] "logical"
        ## [1] "double"
        ## [1] "character"

    ``` r
    # dplyr is equally annoying
    typeof(if_else(NA, 1, "a"))
    ```

        ## Error: `false` must be type double, not character

2.  The order of inputs in `...` does not affect the output type.

3.  It uses consistent rules.

    ``` r
    # Needlessly exposes data scientist to R's internals
    c(factor("a"), factor("b"))
    ```

        ## [1] 1 1

    ``` r
    # But doesn't follow an underlying principle
    unlist(list(factor("a"), factor("b")))
    ```

        ## [1] a b
        ## Levels: a b
