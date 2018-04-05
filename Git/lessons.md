# Lessons

## How to recover from `git reset --hard`?

How did this happen?

1. Googled "how to remove the last commit from git"
2. Google answered "run `git reset --hard HEAD^`"
3. I obeyed. Lost all of my uncommited changes.

How did I fix it?

1. Ran `git fsck --lost-found`
2. Went looking for the blobs in `.git/lost-found/other`

References:

- [How to recover from `git reset --hard`?](https://stackoverflow.com/a/5788069/4862374)
- [Recover dangling blobs in git](https://stackoverflow.com/a/9928789/4862374)
