# R templates

## R Markdown templates

R Markdown templates can be included in packages:

- I learned about this possibility from watching [Daniel Hadley](https://twitter.com/danielphadley)'s talk at rstudio::conf2018 on _Branding and automating your work with R Markdown_.
  - [Slides](https://github.com/Sorenson-Impact/rmarkdown-branding-talk)
  - [Video](https://youtu.be/ogy7rHWlsQ8?t=5h55m27s)
  - [Package](https://github.com/Sorenson-Impact/sorensonimpact)
- It seems like [Chester Ismay](https://twitter.com/old_man_chester) had already written a pretty nice [blog post](http://ismayc.github.io/ecots2k16/template_pkg/)about _Creating a basic template package in R_.

## R Project templates

- [ ] Read [this thread](https://discuss.ropensci.org/t/resources-on-project-directory-organization/340) from [Noam Ross](https://twitter.com/noamross) for links about data analysis project organisation.

## An idea for a package

I would like to create a package for work that will do/have three things:

- RMarkdown templates
  - One for internal memos (HTML)
  - One for external memos and reports (PDF, Word)
  - One for presentations, maybe powered by [xaringan](https://github.com/yihui/xaringan).
- Helper functions for plotting
  - Like our `ggplot2` template.
  - Vigenette with how-to-use examples.
- An R project template:
  -  Implemented via a function like `usethis::create_project()`, or an [extension to the RStudio GUI](https://rstudio.github.io/rstudio-extensions/rstudio_project_templates.html).

The structure I have in mind so far is:
  - `README.rmd`: with some basic prompts.
  - `.gitignore`: that ignores all data and figures.
  - `data/`: With `.RDS`, `.RData` or `.dta` files.
  - `data-raw/`: With the raw data.
  - `out/`: Output
    - `figures/`
    - `tables/`
  - `memos/`:
    - `internal/`: Dynamic.
    - `external/`: Static.
  - `helpers/`: Optional directory, _only_ for helper functions. We will need to define this concept.
  - `AppName/`: Optional directory, for the Shiny app. If this directory exists, then it __must__ have git.
