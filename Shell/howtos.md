# How-to's

Get the number of columns of all files in a directory:

```sh
for filename in *.tsv; do awk -F'\t' '{print FILENAME, NF; exit}' $filename; done
```
