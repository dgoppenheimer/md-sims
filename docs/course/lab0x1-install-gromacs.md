# Installing GROMACS on Colab

These instructions were largely adapted from [Installing Software on Google Colab for IBM3202 tutorials](https://colab.research.google.com/github/pb3lab/ibm3202/blob/master/tutorials/lab00_software.ipynb). I updated the GROMACS version, and to do that I needed to upgrade `cmake`.

<mark>Installation of this software takes about 40 min.</mark> Therefore, we will save the compiled software on Google Drive to save time later.

<mark>**VERY IMPORTANT FIRST STEP:**</mark> Go to the Menu &#8594; *Runtime* &#8594; *Change Runtime Type* and choose GPU!

**Note:** a page reload will be required. This is okay.

First, let's confirm that we are in the correct directory. Remember to run `bash` commands, we need to prepend the command with a `!`.

=== "code input"

    ```py
    !pwd
    ```

=== "output"

    ```py
    /content
    ```

Okay. Great.

## Download GROMACS

Here we will download the software from the GROMACS website.

=== "code input"

    ```py
    #Download GROMACS 2021.5
    !wget https://ftp.gromacs.org/gromacs/gromacs-2021.5.tar.gz
    ```

=== "output"

    ```py
    --2022-04-11 13:03:29--  https://ftp.gromacs.org/gromacs/gromacs-2021.5.tar.gz
    Resolving ftp.gromacs.org (ftp.gromacs.org)... 130.237.11.165, 2001:6b0:1:1191:216:3eff:fec7:6e30
    Connecting to ftp.gromacs.org (ftp.gromacs.org)|130.237.11.165|:443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 38023772 (36M) [application/x-gzip]
    Saving to: ‘gromacs-2021.5.tar.gz’

    gromacs-2021.5.tar. 100%[===================>]  36.26M  17.6MB/s    in 2.1s    

    2022-04-11 13:03:32 (17.6 MB/s) - ‘gromacs-2021.5.tar.gz’ saved [38023772/38023772]
    ```

## Install GROMACS

### Extract the `.tar.gz` File

Use `ipython magic` syntax to run several `bash` commands in the same code cell.

=== "code input"

    ```py
    %%bash
    # extracting the software
    tar xfz gromacs-2021.5.tar.gz
    echo "GROMACS extraction completed"
    ```

=== "output"

    ```py
    GROMACS extraction completed
    ```

### Create and Enter the `build` Directory

=== "code input"

    ```py
    # create and enter the build directory
    %cd gromacs-2021.5
    %mkdir build
    %cd build
    ```

=== "output"

    ```py
    /content/gromacs-2021.5
    /content/gromacs-2021.5/build
    ```

### Upgrade `cmake`

Check the current version of `cmake`.

=== "code input"

    ```py
    !cmake --version
    ```

=== "output"

    ```
    cmake version 3.12.0
    ```

According to the [GROMACS documentation](https://manual.gromacs.org/2021-current/install-guide/index.html):

>Check that you have CMake version 3.13 or later.

Therefore, we need to upgrade `cmake`. First, remove the previous version.

=== "code input"

    ```py
    # remove the old version
    !apt remove cmake
    ```

=== "output"

    ```py
    Reading package lists... Done
    Building dependency tree       
    Reading state information... Done
    The following packages were automatically installed and are no longer required:
      cmake-data libarchive13 liblzo2-2 librhash0 libuv1
    Use 'apt autoremove' to remove them.
    The following packages will be REMOVED:
      cmake
    0 upgraded, 0 newly installed, 1 to remove and 39 not upgraded.
    After this operation, 17.5 MB disk space will be freed.
    (Reading database ... 156210 files and directories currently installed.)
    Removing cmake (3.10.2-1ubuntu2.18.04.2) ...
    Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    ```

Install the current version of `cmake`.

=== "code input"

    ```py
    # Install the new version of `cmake`
    !pip install cmake --upgrade
    ```

=== "output"

    ```py
    Requirement already satisfied: cmake in /usr/local/lib/python3.7/dist-packages (3.12.0)
    Collecting cmake
      Downloading cmake-3.22.3-py2.py3-none-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (22.5 MB)
         |████████████████████████████████| 22.5 MB 45.1 MB/s 
    Installing collected packages: cmake
      Attempting uninstall: cmake
        Found existing installation: cmake 3.12.0
        Uninstalling cmake-3.12.0:
          Successfully uninstalled cmake-3.12.0
    Successfully installed cmake-3.22.3
    ```

Note that `apt` failed to uninstall `cmake`. I may change the command to `!pip uninstall cmake`.  
Check the version (just to be sure).

=== "code input"

    ```py
    !cmake --version
    ```

=== "output"

    ```py
     cmake version 3.22.3
    ```

Okay. That's done.

### Build GROMACS

Run the commands for `cmake`, `make`, `make check`, and `make install`.

=== "cmake"

    ```py
    #@title make
    %%bash
    # had to change -DGMX_GPU=on to -DGMX_GPU=CUDA.
    cmake .. -DGMX_BUILD_OWN_FFTW=ON -DGMX_GPU=CUDA -DCMAKE_INSTALL_PREFIX=/content/gromacs-2021
    ```

=== "make"

    ```py
    # this takes a while
    %%bash
    make
    ```

=== "make check"

    ```py
    %%bash
    make check
    # ~31 min
    ```

=== "make install"

    ```py
    %%bash
    make install
    ```

### Test GROMACS

Let's check that GROMACS was installed correctly.

=== "code input"

    ```py
    ##Checking that GROMACS was successfully installed
    %%bash
    source /content/gromacs-2021/bin/GMXRC
    gmx -h
    ```

=== "output"

    ```py
    /content/drive/MyDrive/IBM3202/gromacs-2021/bin/GMXRC: line 13: /content/gromacs-2021/bin/GMXRC.bash: No such file or directory
    bash: line 2: gmx: command not found
    ```

Okay. We need to change the path in `GMXRC`. On line 13, change

=== "from"

    ```bash
    . /content/gromacs-2021/bin/GMXRC.bash
    ```

=== "to"

    ```bash
    . /content/drive/MyDrive/IBM3202/gromacs-2021/bin/GMXRC.bash
    ```

We also need to fix the path in `GMXRC.bash`. Change line 53

=== "from"

    ```bash
    GMXPREFIX=/content/gromacs-2021/bin/GMXRC.bash
    ```

=== "to"

    ```bash
    GMXPREFIX=/content/drive/MyDrive/IBM3202/gromacs-2021
    ```

Check that GROMACS works, again.

=== "code input"

    ```py
    # Checking that our GROMACS works
    %%bash
    source /content/drive/MyDrive/IBM3202/gromacs-2021/bin/GMXRC
    gmx -h
    ```

=== "output"

    ```py
    bash: line 2: /content/drive/MyDrive/IBM3202/gromacs-2021/bin/gmx: Permission denied
    ```

Ouch! I forgot that you have to give executable permissions to newly installed programs. Run the following code cell.

```py
!chmod 755 -R /content/drive/MyDrive/IBM3202/gromacs-2021
```

Now let's test it again.

=== "code input"

    ```py
    # Checking that our GROMACS works
    %%bash
    source /content/drive/MyDrive/IBM3202/gromacs-2021/bin/GMXRC
    gmx -h
    ```

=== "output"

    ```py
    SYNOPSIS

    gmx [-[no]h] [-[no]quiet] [-[no]version] [-[no]copyright] [-nice <int>]
        [-[no]backup]

    OPTIONS

    Other options:

     -[no]h                     (no)
               Print help and quit
     -[no]quiet                 (no)
               Do not print common startup info or quotes
     -[no]version               (no)
               Print extended version information and quit
     -[no]copyright             (yes)
               Print copyright information on startup
     -nice   <int>              (19)
               Set the nicelevel (default depends on command)
     -[no]backup                (yes)
               Write backups if output files exist

    Additional help is available on the following topics:
        commands    List of available commands
        selections  Selection syntax and usage
    To access the help, use 'gmx help <topic>'.
    For help on a command, use 'gmx help <command>'.
                             :-) GROMACS - gmx, 2021.5 (-:
    ```

Sweet!

Okay. Now we have to remember that whenever we log off of Colab, we will have to remember to change to our working directory and give permissions again to `gmx`. Put the following code cells near the top of your Colab notebook in a section titled *Important Cells to Run*.

=== "change to working directory"

    ```py
    # This gets you into the correct directory
    %cd /content/drive/MyDrive/
    ```

=== "give permissions to `gmx`"

    ```py
    # Give permissions to run gmx
    !chmod 755 -R /content/drive/MyDrive/IBM3202/gromacs-2021
    ```

## Using GROMACS

As an example of setting up and running a molecular dynamics simulation, we will follow the excellent tutorial by Justin Lemkul, [Lysozyme in water](http://www.mdtutorials.com/gmx/lysozyme/index.html), but we will use a different protein. Here we will use the human prion protein (RCSB ID: 1qLz).

Download the protein from the [RCSB database](https://www.rcsb.org/).

=== "code input"

    ```py
    !wget https://www.rcsb.org/structure/1qLz
    ```

=== "output"

    ```py
    --2022-03-24 17:34:39--  https://www.rcsb.org/structure/1qLz
    Resolving www.rcsb.org (www.rcsb.org)... 128.6.159.248
    Connecting to www.rcsb.org (www.rcsb.org)|128.6.159.248|:443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 72560 (71K) [text/html]
    Saving to: ‘1qLz’

    1qLz               100%[===================>]  70.86K  --.-KB/s    in 0.08s   

    2022-03-24 17:34:39 (936 KB/s) - ‘1qLz’ saved [72560/72560]
    ```

!!! important

    It is often difficult to distinguish between an uppercase `O` (Oh) and the number `0` (zero), or a lowercase `l` (el) and the number `1` (one). The RCSB IDs in the database are not case sensitive. Therefore it is always a good idea to write RCSB IDs in all lowercase <mark>except for the lowercase l (el), which you should write as uppercase (L)</mark>. This way you will not mistakenly download the wrong protein for your simulations.

### Preparing Structure Files

The 1QLZ protein structure was solved by NMR, which means that 20 structures were deposited in one `.pdb` file. Here we will use the *stream editor*, `sed`, because `grep` is designed for use on lines of text and we want to collect a block of text<a name="cite_ref-1"></a>[<sup>[1]</sup>](#cite_note-1).

The `.pdb` file has the following format:

```pdb
MODEL        1                                                                  
ATOM      1  N   LEU A 125       4.329 -12.012   2.376  1.00  0.00           N  
ATOM      2  CA  LEU A 125       5.029 -10.769   2.674  1.00  0.00           C  
...
ENDMDL                                                                          
MODEL        2                                                                  
ATOM      1  N   LEU A 125       5.962 -12.281  -0.586  1.00  0.00           N  
ATOM      2  CA  LEU A 125       6.228 -10.948  -0.052  1.00  0.00           C  
...
```

Note that each model is preceded by a line that designates the model number (`MODEL 1`, `MODEL 2`, and so on) and ends with the line `ENDMDL`. We can use these as starting and stopping patterns for each model that we want to extract from this file.

*Regex*, which is short for *Regular Expressions*<a name="cite_ref-2"></a>[<sup>[2]</sup>](#cite_note-2) is used for search and replace of characters in certain text files (but cannot be used for `html` files--see [Stackoverflow](https://stackoverflow.com/questions/1732348/regex-match-open-tags-except-xhtml-self-contained-tags/1732454#1732454)). In our case we want to extract the text between the patterns `MODEL 1` and `ENDMDL` (including the patterns) into a new file. I got the code, below, from [Stackoverflow](https://stackoverflow.com/questions/4857424/extract-lines-between-2-tokens-in-a-text-file-using-bash), but had to modify it for using `sed` on Mac OSX (you need the `-E` option). The `-E` option may or may not be necessary for Colab.

```bash
# Here is the sed command
sed -E -n '/^MODEL +1 /,/^ENDMDL/w 1qLz-model1.pdb' 1qlz.pdb
```

#### Explanation of the `sed` Command

- `sed -E` use extended regular expressions  
- `-n` do not echo every line to output  
- `'/START/,/STOP/'` pattern to search for; we start at lines that begin with `MODEL 1` and end with lines that begin with `ENDMDL`  
- `^` is Regex for the beginning of a line  
- `<space> +` search for 1 or more spaces  
- `1 <space>`, search for the number 1 followed by a space (or else you get model 19)  
- `w 1qLz-model1.pdb` write the output to the file `1qLz-model1.pdb`  
- `1qlz.pdb` is the input file

---
<a name="cite_note-1"></a>1. It is possible to extract blocks of text using `grep` but it is not as easy as using `sed`.[&#8617;](#cite_ref-1)

<a name="cite_note-2"></a>2. The [Python Regex Cheat Sheet](https://www.geeksforgeeks.org/python-regex-cheat-sheet/) has a list of many common regular expressions and is a useful reference.[&#8617;](#cite_ref-2)


