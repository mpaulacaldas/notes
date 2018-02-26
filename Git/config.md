# Git configurations

How to keep CRLF endings in Windows checkouts and LF endings on Mac and Linux systems and in the repository (see this [answer](https://stackoverflow.com/questions/5834014/lf-will-be-replaced-by-crlf-in-git-what-is-that-and-is-it-important)): 

```
$ git config --global core.autocrlf input
```