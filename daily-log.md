# Daily log

2018-03-09

- I cannot reuse the same output binding (e.g. from a leaflet plot) in different tab panels. There are two possible solutions: use modules, or do a double assignment. For more info see [this issue](https://github.com/rstudio/shiny/issues/867).
- I need to store clicks from a leaflet map. The [documentation](https://rstudio.github.io/leaflet/shiny.html) and [this answer form SO](https://stackoverflow.com/questions/41106547/how-to-save-click-events-in-leaflet-shiny-map) were useful.

2018-03-12

- I _should_ be able to run Stata commands in .Rmd files by changing the chuck option from `{r}` to `{stata}`. This doesn't work for me, I am not really sure why. The method described in this [blog post](https://www.ssc.wisc.edu/~hemken/SASworkshops/Markdown/SASmarkdown.html) (for SAS) did work. I should explore further.
- This [answer](https://stackoverflow.com/questions/41104576/changing-styles-when-selecting-and-deselecting-multiple-polygons-with-leaflet-sh/41147206#41147206) explains how to use clicks and double clicks to update a Leaflet map.
