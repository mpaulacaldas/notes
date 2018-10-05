# Highlights eRum2018

*Extract from e-mail I sent to my coworkers*

Last week I attendended the 2018 European R Users Meeting (eRum2018) in Budapest. The conference is held every two years in Europe and gathers hundreds of R Users from industry and academia.

This year's conference lasted three days, with one day dedicated to workshops, and the other two to presentations (which included keynotes, shiny demos, lightning talks and poster sessions).

I attended two workshops (one in text mining, and another on building packages), all of the Shiny presentations (demos and package presentations), and tried to make it most of the talks on using R in industry.

Below you will find my main takeaways from a selection of the presentations. Feel free to come see me if you have questions, or if you would like to talk about any of the other presentations that I do not cover here.

## Workshops

### Building an interpretable NLP model to classify tweets

The aim of this workshop was to give an introduction to Natural Language Processing and the LIME (Local Interpretable Model-agnostic Explanations) Framework for interpreting Machine Learning Models. This workshop was fairly popular among R users in industry that use Machine Learning models everyday but find them difficult to explain to clients and/or other stakeholders.

During the workshop, we created a simple predictive model calssifying tweets made by Clinton or Trump during their presidential campaign. This was done using the [quanteda](https://github.com/quanteda/quanteda) package. We then used used the [LIME](https://github.com/marcotcr/lime) package to create visualisations to help interpret and understand the reliability of our NLP model. Both base R and tidytext approaches were presented.

The materials are available at [this Github repo.](https://github.com/KKulma/2018_eRum_TextClassification_workshop)

The tutorial was led by Grace Meyer and Kasia Kulma, the organisers of R-Ladies London.

### Building a package that lasts

This workshop presented best practices for creating packages (e.g. documentation, testing, continuous integration) and tools for automating the package-creating process. We mainly worked with the `devtools`, `usethis` and `testthat` packages.

I thought this was an excellent training because it gave a nice overview of a lot of topics that are generally covered in very specialised (and sometimes outdated) blogs. Although no previous package-building experience was required to attend the workshop, I think tutorial could have been very difficult to follow for someone with zero experience.

The (excellent) slides presented in the tutorial are available at [this Github repo](https://github.com/ColinFay/erum2018).

The tutorial was led by Colin Fay, from [ThinkR](https://thinkr.fr/), a small French company specialising R consulting and trainings. They are very active in the Parisian R User community (organisers of R-Addicts, R-Ladies) and have an [excellent blog](https://thinkr.fr/le-blog/) (in French).

## Shiny presentations

### Not all that _Shiny_ by default

Mikolaj Olszewski and Mateusz Otmianowski presented a Shiny app that they created for Pearson, one of the world's largest learning companies. Their app served as a platform where different stakeholders could monitor and interact with the content and KPIs comming from hundreds of MOOCs and books.

In my opinion, this was one of the best Shiny presentations because it managed to explain the business logic of the app, the technical and design challanges that they faced and the lessons they learned along the way.

This app took __over 6 months__ to develop. This is a good benchmark to keep in mind for apps that are important in _scale_ and that will need _maintainance_ in the future.

You can watch their presentation [here on YouTube](https://www.youtube.com/watch?v=3u2r0lUdr7E).

### Taking inspirations from proven frontend frameworks to add to Shiny with 6 new packages

[Olga Mierzwa-Sulima](https://twitter.com/olga_mie?lang=en) from [Appsilon](https://appsilondatascience.com/) presented 6 Shiny packages developed by their company for creating Shiny apps. Four of these packages are available in open source, and the latter two are available exclusively to Appsilon's clients.

1. `shiny.semantic`: Alternative to Shiny default's Bootstrap theme.
2. `semantic.dashboard`: Alternative to `shinydashboard`
3. `shiny.router`: Allows for urls with parameters.
4. `shiny.i18n`: Translate Shiny elements into a different language. This works by setting a global variable, so it may adding a button to change languages will require having to reload the app.
5. `shiny.users`: Creates user logins. __Not open source__.
6. `shiny.admin`: To monitor the perfomance and usage of app. __Not open source__.

Slides can be found [here](https://github.com/Appsilon/erum2018).

### Drilldown data discovery with Shiny

Barbara Borges Ribeiro from RStudio presented three ways of _drilling_ in Shiny apps:

- __Drilling down:__ This happens when you want to delve deeper into the data with respect to the click (e.g. click on a row and then a pop-up with more detailed information shows up). This can be done with `appendTab()` and `removeTab()`.

- __Drill trough:__ All boxes and plots get updated after change in `selectInput()`. This is done with  `showModal()` or `removeModal()`

- __Drilling up:__ Starting from all your data and choosing _how_ to aggregate it. Selections in options create new boxes in the UI. All done with `insertUI()` and `removeUI()`.

All the triggers for these type of actions are defined inside `observeEvent()` calls. Note that you can have nested `observeEvent()`'s.

Materials can be found [here](https://github.com/bborgesr/erum2018).

## Shiny demos

Seven Shiny demos were presented during the conference:

- Shiny Dashboard on streaming data, András Tajti

- [What is the best place to be? Location optimization with R and Google Maps](https://www.youtube.com/watch?v=TEv5uX3X0os&list=PLUBl0DoLa5SAo_XRnkQA5GtEORg9K7kMh&index=4), Bartosz Czernecki, Jakub Nowosad

- [Visualizing vehicle usage with the leaflet package](https://www.youtube.com/watch?v=zbTE9I1pvVI&index=5&list=PLUBl0DoLa5SAo_XRnkQA5GtEORg9K7kMh), Peter Szabolcs

- [Going async with Shiny](https://www.youtube.com/watch?v=He7Z3Fkyw7w&list=PLUBl0DoLa5SAo_XRnkQA5GtEORg9K7kMh&index=6), Dávid Gyurkó

- [SmaRP: Smart Retirement Planning A Shiny App to evaluate retirement benefits and optimization thereof, in the context of the Swiss system](https://www.youtube.com/watch?v=B1EbbF_B7Ts), Francesca Vitalini

- [Towards Native Declarative Data Collection with Question and Survey Instant Feedback in R & Shiny](https://www.youtube.com/watch?v=G5tr2cHmbTk&list=PLUBl0DoLa5SAo_XRnkQA5GtEORg9K7kMh&index=2), Kamil Wais

- [The Zurich Real Estate App - An R-Shiny application for the Zurich real estate market](https://www.youtube.com/watch?v=IhLVxnqjtto&index=3&list=PLUBl0DoLa5SAo_XRnkQA5GtEORg9K7kMh), Max Grütter

The most interesting of these talks were the those of Kamil Wais (presenting the [ODGAR Framework](https://kalimu.github.io/project/odgar/)), Max Grütter (only Shiny app with [Github repo](https://github.com/mxgrttr/zhreapp) available) and Francesca Vitalini (who wan "Best Shiny Demo").

Note that most of the presentations/demos are __not__ available on-line since they were made on behalf of private clients. The apps presented used fake or anonymised data.

## More info

There were a lot of other very interesting presentations. The full list is available at <http://2018.erum.io/>, and videos can be found at the [Budapest R Users YouTube channel](https://www.youtube.com/watch?v=4XxOUPgs9tc&list=PLUBl0DoLa5SAo_XRnkQA5GtEORg9K7kMh).
