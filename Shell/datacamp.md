# Introduction to Shell for Data Science

## Summary of commands

| Command  | Description                                                         |
|----------|---------------------------------------------------------------------|
| `pwd`    | Print working directory                                             |
| `ls`     | _Listing_. Show files and directories in working directory          |
| `cd`     | Change directory                                                    |
| `cp`     | Copy                                                                |
| `mv`     | Move or rename                                                      |
| `rm`     | Remove a file                                                       |
| `rmdir`  | Remove an empty directory                                           |
| `cat`    | _Concatenate_. Print content                                        |
| `less`   | Print content piece by piece                                        |
| `head`   | Print 10 first lines of a file                                      |
| `man`    | Help for a command                                                  |
| `cut`    | Select columns of a text file                                       |
| `history`| Print recently run commands                                         |
| `grep`   | Select with regex                                                   |
| `>`      | Store the output of whatever is on the LHS on the RHS file          |
| `|`      | Pipe. Use whatever is on the LHS as input for the RHS command       |
| `wc`     | _Word count_. Print number of characters, words and lines in a file |
| `sort`   | Sorts data in an ascending alphabetical order (default)             |
| `uniq`   | Remove _adjacent_ duplicated lines                                  |
| `set`    | List of __environmental variables__ in the shell                    |


## Flags

| Command | Flag | Description of flag                           |
|---------|------|-----------------------------------------------|
| `head`  | `-n` | Number of lines to print                      |
| `ls`    | `-R` | Print _all_ files (even deeply nested ones)   |
| `ls`    | `-F` | Print `/` after the name of every directory   |
| `cut`   | `-f` | Fields (columns)                              |
| `cut`   | `-d` | Delimiter of text file                        |
| `grep`  | `-c` | Print a count of matching lines               |
| `grep`  | `-i` | Ignore case                                   |
| `grep`  | `-l` | Print the names of files that contain matches |
| `grep`  | `-n` | Print line numbers for matching lines         |
| `grep`  | `-v` | Show lines that _don't_ match                 |
| `sort`  | `-n` | Sort numerically                              |
| `sort`  | `-r` | Reverse the order of the output               |
| `sort`  | `-b` | Ignore leading blanks                         |
| `sort`  | `-f` | _Fold case_, i.e. be case insensitive         |


## Wild cards

| Wild card | Description                                     |
|-----------|-------------------------------------------------|
| `*`       | Match zero or more characters                   |
| `?`       | Match a single character                        |
| `[...]`   | Match any of the `...` characters               |
| `{...}`   | Match any of the `...` comma-separated patterns |


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

Print first 100 lines of a file:

```
head -n 100 hello.txt
```

Print columns 2 to 4 of a text file with a comma delimiter:

```
cut -f 2-4 -d , world.csv
```

Print 25th command in `history`: 
```
!25
```

Print last command starting with `head`:
```
!head
```

Store a command output (LHS) in a file (RHS):

```
echo "Hello world!" > test.txt
```

To print the value of the `USER` variable:

```
echo $USER
```

Define a __shell variable__ and print its value:
```
shellvar=Desktop/test.txt # careful, no spaces around the equal sign
echo $shellvar
```

For-loops:
```

``

