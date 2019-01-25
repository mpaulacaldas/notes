# Installations and set-ups

## R on Windows

- I had problems downloading packages in Windows before updating to R 3.5.0. [This was the workaround.](https://stackoverflow.com/a/46037327/4862374)
- [How to download RTools](http://jtleek.com/modules/01_DataScientistToolbox/02_10_rtools/#1).

## Anaconda

Two things to keep in mind during installation.

- Install for all users.
- Add Anaconda to the System Path. If you didn't, follow [these instructions](https://medium.com/@GalarnykMichael/install-python-on-windows-anaconda-c63c7c3d1444).

## Stata kernel

The instructions [from the official documentation](https://kylebarron.github.io/stata_kernel/getting_started/) didn't quite work. Here is what did:

```bash
pip install --user stata_kernel
python -m stata_kernel.install
```

Note that this did not work with the internet from work, but worked alright at home.
