# Installing GROMACS on Colab

These instructions were largely adapted from [Installing Software on Google Colab for IBM3202 tutorials](https://colab.research.google.com/github/pb3lab/ibm3202/blob/master/tutorials/lab00_software.ipynb). I updated the GROMACS version, and to do that I needed to upgrade `cmake`.

<mark>Installation of this software takes about 40 min.</mark> Therefore, we will save the compiled software on Google Drive to save time later.

<mark>**VERY IMPORTANT FIRST STEP:**</mark> Go to the Menu &#8594; *Runtime* &#8594; *Change Runtime Type* and choose GPU!

**Note:** a page reload will be required. This is okay.

First, let's confirm that we are in the correct directory. Remember to run `bash` commands, we need to prepend the command with a `!`.

```py
!pwd
/content
```

Okay. Great.

## Download GROMACS

Here we will download the software from the GROMACS website.

```py
#Download GROMACS 2021.5
!wget https://ftp.gromacs.org/gromacs/gromacs-2021.5.tar.gz
```
