Shiny
================

-   [Leaflet](#leaflet)
-   [Modules](#modules)

Leaflet
-------

-   I cannot reuse the same output binding (e.g. from a leaflet plot) in different tab panels. There are two possible solutions: use modules, or do a double assignment. For more info see [this issue](https://github.com/rstudio/shiny/issues/867).
-   I need to store clicks from a leaflet map. The [documentation](https://rstudio.github.io/leaflet/shiny.html) and [this answer form SO](https://stackoverflow.com/questions/41106547/how-to-save-click-events-in-leaflet-shiny-map) were useful.
-   This [answer](https://stackoverflow.com/questions/41104576/changing-styles-when-selecting-and-deselecting-multiple-polygons-with-leaflet-sh/41147206#41147206) explains how to use clicks and double clicks to update a Leaflet map.

Modules
-------

[Link to article.](https://shiny.rstudio.com/articles/modules.html)

#### Context

-   Input and output IDs must be unique across the entire app. Modules only require input and output IDs to be unique *within the function*.
-   When to use Shiny modules? When you want functions to generate UI, inputs and outputs.
-   A module = piece of UI + fragment of server logic that uses that UI

#### How to use them

Module UI functions need to: - have names suffixed with `Input`, `Ouput` or `UI` - have `id` as **first** argument - create a namespace function at the beginning of the statement like so: `ns <- NS(id)` - wrap any input or output ID in `ns()` - wrap results in `tagList()`

They look more or less like this:

``` r
fooInput <- function(id, label = "Label") {
  # Create namespace
  ns <- NS(id)

  # Wrap result in tagList()
  tagList(

    # Creating inputs
    # Make sure they are wraped by ns()

    )

}
```

Module server functions need to:

-   be named like their corresponding module UI function but *without* the `Input`, `Ouput` or `UI` suffix
-   have `input`, `output` and `session` as its first parameters

They look more or less like this:

``` r
foo <- function(input, output, session, ...) {
  # Stuff calling on the IDs created in fooInput()
}
```

Bring it all together:

-   `global.R`: source the script where you have saved your module functions
-   `ui.R`: call the module UI function pretty much like you would with any other input function

``` r
fooInput("id_foo", "This is a label")
```

-   `server.R`: call the server function, making sure you have the same ID

``` r
callModule(foo, "id_foo", ...)
```

#### More

Refer back to [article](https://shiny.rstudio.com/articles/modules.html) for more on nesting modules, using renderUI within modules, and packaging.
