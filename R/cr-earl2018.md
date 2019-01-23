# *Compte-rendu* of EARL 2019
*by Maria Paula Caldas*

*Extract from e-mail I sent to my coworkers*

Last month I attended the 2019 London edition of the EARL (**E**nterprise **A**pplications of the **R L**anguage) conference, organised by [Mango Solutions](https://www.mango-solutions.com/). The conference takes place every year and is composed of two days of presentations and one day of workshop sessions. It is a great way to stay up to date with what is happening in the R community and to get a glimpse of the type of data products being developed with R in different types of industries.

Shiny was a popular topic -- to the point that someone suggested renaming next year's event to "Shiny conference". Here is are some of the presentations that I found particularly interesting (or fun!):

- Shiny for hospital operations: [Christian Moroy](https://twitter.com/@ChristianMoroy) presented a Shiny app that helps administrators allocate operating theatres to patients depending on different constraints (e.g. length of procedures, staff availability, risk to the patients of prolonging waiting times, etc.). The app also gives suggestions to the administrators, which are based on ML algorithms that predict critical care demand. The presentation was interesting because it detailed both the technical and non technical challenges that can arise in these kind of projects.
- Apps for economic analysis in pharma: [Ian Jacob](https://twitter.com/@ianjacobs)'s presentation dealt with the process of bringing drugs to market in the UK, the role health economists play in the process, and how difficult it is to convince regulators to ditch Excel.
- Finding out what Parliament thinks: Sam Tazzyman presented an app that helps users browse the different debates that took place in Parliament. Funny enough, the tool was developed by the Ministry of Justice to assess which Parliamentarians are more influential and what they care about so that the MoJ can get them to agree on suggested changes to legislation.
- Putting the R in bar: [Jasmine Pengelly](https://twitter.com/@stackjaz) helps her boyfriend, a bar owner, make informed decisions about his drink menu, prices and marketing investments by looking into his data. Very funny talk!

Another popular topic was *reproducibility*. For example:

- [Leanne Fitzpatrick](https://twitter.com/@LK_Fitzpatrick), head of data at HelloSoda, gave a great talk on the different challenges faced by data science teams. Her talk revolved around the different tools and processes that her company has tried to adopt to address these challenges. In particular, she spoke about the difficulties of ensuring proper documentation in a growing team composed of data scientists and engineers. I have attached her slides to this e-mail.
-  [Omayma Said](https://github.com/OmaymaS)'s talk on [R and Docker](https://speakerdeck.com/omaymas/beyond-prototypes-a-journey-to-the-production-land-earl2018) addressed the challenges of bringing Shiny apps into production while minimising the risks brought on by new versions of R or its packages.
- [Garrett Grolemund](https://github.com/garrettgman)'s keynote lecture addressed the reproducibility crisis in academia and presented R Markdown as a possible tool to address the issue. Moreover, he announced the release of the book [**R Markdown: The Definitive Guide**](https://bookdown.org/yihui/rmarkdown/) (*which we should start reading*). And good news, the latest version of `rmarkdown` now supports PowerPoint presentations.
- [Mike K Smith](https://twitter.com/MikeKSmith), a senior director at Pfiezer, talked about the challenges of ensuring reproducibility in pharma, a heavily regulated industry where they must make sure that their data analyses are fully reproducible decades (yes, decades) after they have been run. He compared his job to "herding chickens".

Last but not least, four workshop sessions proposed on the first day:

- [Shiny, beyond the basics](https://github.com/MangoTheCat/shiny_beyond_the_basics)
- [Python for R Users](https://github.com/MangoTheCat/python-for-r-users-workshop)
- [Deep Learning in Keras with R](https://github.com/MangoTheCat/keras-workshop)
- [Introduction to Functional Programming with purrr](https://github.com/MangoTheCat/Introduction-to-Functional-Programming-with-Purrr)

Since the workshops were organised in parallel sessions, we could only choose two of the above. I chose **Shiny, beyond the basics** and **Python for R Users**. Both workshops were well-taught, and most importantly, provided excellent supporting materials. You can access the original materials by following the links in the list items above, or take a look at my personal notes [here](https://github.com/mpaulacaldas/python-for-r-users-workshop) and [here](https://github.com/mpaulacaldas/shiny_beyond_the_basics).

Please feel free to ask me questions if you want to speak about the presentations or the workshops.
