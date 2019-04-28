How to...
================

-   [Slightly modified examples](#slightly-modified-examples)
    -   [Host HTML files via Github Pages](#host-html-files-via-github-pages)
    -   [Recover from `git reset --hard`?](#recover-from-git-reset---hard)
    -   [Get the print the time of my commits](#get-the-print-the-time-of-my-commits)
    -   [Keep CRLF endings in Windows and LF endings on Mac/Linux and in the repository](#keep-crlf-endings-in-windows-and-lf-endings-on-maclinux-and-in-the-repository)
    -   [SSH keys](#ssh-keys)
    -   [Remove merged local branches](#remove-merged-local-branches)
-   [SO answers](#so-answers)
-   [Blog posts and other](#blog-posts-and-other)

Slightly modified examples
--------------------------

### Host HTML files via Github Pages

You can host HTML files in Github via Github Pages. The steps to follow are:

1.  Create an [orphan branch](https://stackoverflow.com/q/19980631) named gh-pages

    ``` bash
    git checkout --orphan gh-pages
    ```

2.  Remove everything but the HTML file of interest. For `bookdown` books, this will be `index.html`.
    -   If you are hosting a `bookdown` book, keep all of the images, CSS and JavaScript files.
    -   If you are hosting self-contained slides generated with RMarkdown, you should **remove** all other files.

    ``` bash
    ls | grep -v slides.html | xargs rm
    ```

3.  If this is not already the case, rename the HTML `index.html`.

    ``` shell
    mv slides.html index.html
    ```

4.  Add a hidden file that tells Github not to build the site via Jekyll.

    ``` bash
    touch .nojekyll
    ```

5.  Stage, commit and push.

    ``` bash
    git add .
    git commit -m "Add webpage"
    git push origin gh-pages
    ```

Sources:

-   <https://bookdown.org/yihui/bookdown/github.html>
-   <https://unix.stackexchange.com/a/154067>

### Recover from `git reset --hard`?

How did this happen?

1.  Googled "how to remove the last commit from git"
2.  Google answered "run `git reset --hard HEAD^`"
3.  I obeyed. Lost all of my uncommited changes.

How did I fix it?

1.  Ran `git fsck --lost-found`
2.  Went looking for the blobs in `.git/lost-found/other`

References:

-   [How to recover from `git reset --hard`?](https://stackoverflow.com/a/5788069/4862374)
-   [Recover dangling blobs in git](https://stackoverflow.com/a/9928789/4862374)

### Get the print the time of my commits

-   <https://www.atlassian.com/git/tutorials/git-log>
-   <https://stackoverflow.com/questions/4259996/how-can-i-view-a-git-log-of-just-one-users-commits>

``` bash
git log --author="Maria Paula Caldas" --pretty=format:"%cn committed %h on %cd"
```

### Keep CRLF endings in Windows and LF endings on Mac/Linux and in the repository

-   <https://stackoverflow.com/questions/5834014/lf-will-be-replaced-by-crlf-in-git-what-is-that-and-is-it-important>

``` bash
$ git config --global core.autocrlf input
```

### SSH keys

-   [What](https://serverfault.com/a/430069), [how](http://happygitwithr.com/ssh-keys.html).

### Remove merged local branches

Modified version of this [SO answer](https://stackoverflow.com/a/6127884).

``` bash
git branch --merged | egrep -v "(master)" | xargs git branch -d
```

SO answers
----------

-   [Move the most recent commit(s) to a new branch with Git](https://stackoverflow.com/questions/1628563/move-the-most-recent-commits-to-a-new-branch-with-git)

Blog posts and other
--------------------

-   [Guide to connect RStudio and Gitlab](https://gitlab.com/HeidiSeibold/setup-git-rstudio-gitlab)
