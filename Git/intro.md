## Git resources

### How to use Git with R

First, check out Jenny Brian's tutorial from rstudioconf::2017, [Happy Git and Github for the useR](https://www.rstudio.com/resources/videos/happy-git-and-gihub-for-the-user-tutorial/). The tutorial was aimed at people with little to no exposure of Git, so it focuses on how to use Git via the RStudio GUI instead of the command line. There is a book with installation instructions and exercices at <http://happygitwithr.com/>. I recommend watching the full tutorial + reading the entire book.

Second, have a look at Hadley Wickham's chapter in [R Packages](http://r-pkgs.had.co.nz) about [Git and Github](http://r-pkgs.had.co.nz/git.html).

Here are some other links that I regularly used when learning Git:

- [RStudio's Version Control with Git and SVN](https://support.rstudio.com/hc/en-us/articles/200532077-Version-Control-with-Git-and-SVN)
- [DataCamp's Introduction to Git for Data Science](https://www.datacamp.com/courses/introduction-to-git-for-data-science)

### Basic Git commands

*Use these in the* ***Terminal***.

![](https://support.rstudio.com/hc/article_attachments/115019249667/2017-08-07-1_1_term-simple.png)

Stage files for commit:
```bash
# Two files
git add one.R two.R
# All files
git add .
```

Commit:
```bash
git commit -m "My short but descriptive message"
```

See what changed between two commits:
```bash
# Where ID1 and ID2 are the identifiers (or hashs) of the commits
git diff ID1..ID2
```

Get the status of the working tree:

```bash
git status
```

Info on last commits:

```bash
git log
# Press Enter to keep going
# Type "q" to quit
```

See the state of all files at a given point in time (as determined by a commit):

```bash
# Reference the commit relative to the current state
git checkout HEAD~1
# Or reference it with respect to the hash of the target commit
git checkout 8e68cb
# Return back to the most recent commit in master
git checkout master
```

Create a new branch and move to it:

```bash
git branch branch-name
git checkout branch-name
```

Merge a branch into master:

```bash
# Make sure you're at the branch
git checkout branch-name
# Merge master into branch to make sure that branch is up to date
git merge master
# Move to master
git checkout master
# Merge branch into master
git merge branch-name
```
