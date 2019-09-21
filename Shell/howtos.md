# How-to's

Get the number of columns of all files in a directory:

```sh
for filename in *.tsv; do awk -F'\t' '{print FILENAME, NF; exit}' $filename; done
```

[Work with RStudio:](https://community.rstudio.com/t/terminal-command-to-open-rstudio/2476)

```sh
# Open RStudio
open -na Rstudio
# Open a project
open myproject.Rproj
```
