# Introduction to Shell for Data Science

## Summary of commands

| Command | Description                                                |
|---------|------------------------------------------------------------|
| `pwd`   | Print working directory                                    |
| `ls`    | _Listing_. Show files and directories in working directory |
| `cd`    | Change directory                                           |
| `cp`    | Copy                                                       |
| `mv`    | Move or rename                                             |
| `rm`    | Remove a file                                              |
| `rmdir` | Remove an empty directory                                  |
| `cat`   | _Concatenate_. Print content                               |
| `less`  | Print content piece by piece                               |
| `head`  | Print 10 first lines of a file                             |
| `man`   | Help for a command                                         |
| `cut`   | Select columns of a text file                              |


## Flags

| Command | Flag | Description of flag                         |
|---------|------|---------------------------------------------|
| `head`  | `-n` | Number of lines to print                    |
| `ls`    | `-R` | Print _all_ files (even deeply nested ones) |
| `ls`    | `-F` | Print `/` after the name of every directory |
| `cut`   | `-f` | Fields                                      |
| `cut`   | `-d` | Delimiter of text file                      |



## Usage examples

Move up a directory:

```
cd ..
```

Copy a file:

```
cp original.txt duplicate.txt
```

Move up files:

```
mv hello.txt world.txt ..
```

Rename a file:

```
mv old-name.txt new-name.txt
```

Print first _x_ (e.g. 100) lines of a file:

```
head -n 100 hello.txt
```

