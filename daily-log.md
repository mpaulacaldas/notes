# :spiral_calendar: Daily log

2018-03-09

- I cannot reuse the same output binding (e.g. from a leaflet plot) in different tab panels. There are two possible solutions: use modules, or do a double assignment. For more info see [this issue](https://github.com/rstudio/shiny/issues/867).
- I need to store clicks from a leaflet map. The [documentation](https://rstudio.github.io/leaflet/shiny.html) and [this answer form SO](https://stackoverflow.com/questions/41106547/how-to-save-click-events-in-leaflet-shiny-map) were useful.

2018-03-12

- I _should_ be able to run Stata commands in .Rmd files by changing the chuck option from `{r}` to `{stata}`. This doesn't work for me, I am not really sure why. The method described in this [blog post](https://www.ssc.wisc.edu/~hemken/SASworkshops/Markdown/SASmarkdown.html) (for SAS) did work. I should explore further.
- This [answer](https://stackoverflow.com/questions/41104576/changing-styles-when-selecting-and-deselecting-multiple-polygons-with-leaflet-sh/41147206#41147206) explains how to use clicks and double clicks to update a Leaflet map.

2018-03-13

- `eventReactive()` is used to create an object with reactive values, while `observeEvent()` is used for side effects ([see this SO answer](https://stackoverflow.com/questions/33519816/shiny-what-is-the-difference-between-observeevent-and-eventreactive)).
- However, is an object created by `eventReactive()` a reactive object? __Hell, no.__ The values _inside_ the objects are reactive, but the object itself is not. Always read the [documentation](https://www.rdocumentation.org/packages/shiny/versions/1.0.5/topics/reactiveValues).

2018-03-14
- Started watching Joe Cheng's tutorial on "Effective reactive programming". Resources can be found [here](https://github.com/jcheng5/user2016-tutorial-shiny).
  - :bulb: Also, for this year's interns intro to R, do the thing with the 5 slides with yes/no questions and then answers.

## TODO

- [ ] Explore [`fuzzyjoin`](https://github.com/dgrtwo/fuzzyjoin).

- [ ] Read [this](https://sandhya-k.gitbooks.io/on-boarding-off-boarding-in-newsrooms/content/links.html) for links on documentation/onboarding.

- [ ] For more on the differences between `observe()`, `reactive()` and `eventReactive()`, read [this](https://stackoverflow.com/questions/39436713/r-shiny-reactivevalues-vs-reactive) and watch [this](https://www.rstudio.com/resources/webinars/shiny-developer-conference/).
