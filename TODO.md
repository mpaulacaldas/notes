# TODO

- [ ] Explore [`fuzzyjoin`](https://github.com/dgrtwo/fuzzyjoin).

- [ ] Read [this](https://sandhya-k.gitbooks.io/on-boarding-off-boarding-in-newsrooms/content/links.html) for links on documentation/onboarding.

- [ ] For more on the differences between `observe()`, `reactive()` and `eventReactive()`, read [this](https://stackoverflow.com/questions/39436713/r-shiny-reactivevalues-vs-reactive) and watch [this](https://www.rstudio.com/resources/webinars/shiny-developer-conference/).

- [ ] Read [this thread](https://discuss.ropensci.org/t/resources-on-project-directory-organization/340) from [Noam Ross](https://twitter.com/noamross) for links about data analysis project organisation.

- [ ] Create a package for work that includes:
  - RMarkdown template for internal and external memos (HTML, Word, PDF).
  - RMarkdown presentation template, powered by [xaringan](https://github.com/yihui/xaringan).
  - Our `ggplot2` template, with a vignette.
  - A function similar to `usethis::create_project()` that will create all the necessary directories for a data analysis project and set up a git repository. The structure I have in mind so far is:
    - `README.rmd`: with some basic prompts.
    - `.gitignore`: that ignores __all__ data and figures.
    - `data/`: With `.RDS`, `.RData` or `.dta` files.
    - `data-raw/`: With the raw data.
    - `figures/`: Produced from the scripts.
    - `tables/`: Produced from the scripts.
    - `memos/`: Optional directory, for `.rmd` or `.html` files. This configuration may be problematic.
    - `R/`: Optional directory, _only_ for helper functions. I may have to rethink the name of the directory, it may lead to confusion with Stata users.
    - `AppName/`: Optional directory, for the Shiny app.
