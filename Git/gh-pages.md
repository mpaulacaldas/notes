# Github pages

You can host HTML files in Github via Github Pages. The steps to follow are:

1. Create an [orphan branch](https://stackoverflow.com/q/19980631) named gh-pages

    ```bash
    git checkout --orphan gh-pages
    ```

1. Remove everything but the HTML file of interest. For `bookdown` books, this will be `index.html`.
    - If you are hosting a `bookdown` book, keep all of the images, CSS and JavaScript files.
    - If you are hosting self-contained slides generated with RMarkdown, you should **remove** all other files.

    ```bash
    ls | grep -v slides.html | xargs rm
    ```

1. If this is not already the case, rename the HTML `index.html`.

    ```shell
    mv slides.html index.html
    ```

1. Add a hidden file that tells Github not to build the site via Jekyll.

    ```bash
    touch .nojekyll
    ```

1. Stage, commit and push.

    ```bash
    git add .
    git commit -m "Add webpage"
    git push origin gh-pages
    ```


Sources:

- https://bookdown.org/yihui/bookdown/github.html
- https://unix.stackexchange.com/a/154067
