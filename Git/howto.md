# How to ...

### Get the print the time of my commits

- https://www.atlassian.com/git/tutorials/git-log
- https://stackoverflow.com/questions/4259996/how-can-i-view-a-git-log-of-just-one-users-commits

```bash
git log --author="Maria Paula Caldas" --pretty=format:"%cn committed %h on %cd"
```

### Keep CRLF endings in Windows and LF endings on Mac/Linux and in the repository

- https://stackoverflow.com/questions/5834014/lf-will-be-replaced-by-crlf-in-git-what-is-that-and-is-it-important

```bash
$ git config --global core.autocrlf input
```

### SSH keys

- [What](https://serverfault.com/a/430069), [how](http://happygitwithr.com/ssh-keys.html).
