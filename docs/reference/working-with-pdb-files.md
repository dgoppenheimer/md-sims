---
tags:
  - insiders
  - brand new
---

# More `.pdb` file manipulation

Some `pdb` files from the RCSB database contain more than one model. Structures solved by NMR often have multiple structure models--20 is common. To extract a single model for docking or MD simulations, you can always open the file in PyMOL or VMD and save a single model as a new file. But we can also do this easily using `grep`, `awk`, or `sed`. Here we will use the **s**tream **ed**itor, `sed`, because `grep` is designed for use on lines of text and we want to collect a block of text.

!!! info

    It is possible to extract blocks of text using `grep` but it is not as easy as using `sed`.

Below we will extract a single model from a multi-model structure file.

`1qLz` is a typical multi-model structure file that has 20 structures in the same file. Multi-model files have the following format.

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

!!! note

    Each model is preceded by a line that designates the model number (`MODEL 1`, `MODEL 2`, and so on) and ends with the line `ENDMDL`. We can use these as starting and stopping patterns for each model that we want to extract from this file.

*Regex*, which is short for *Regular Expressions*[^1] is used for search and replace of characters in certain text files (but generally should not be used for `html` files--see [Stackoverflow](https://stackoverflow.com/questions/1732348/regex-match-open-tags-except-xhtml-self-contained-tags/1732454#1732454)). In our case we want to extract the text between the patterns `MODEL 1` and `ENDMDL` (including the patterns) into a new file. I got the code, below, from [Stackoverflow](https://stackoverflow.com/questions/4857424/extract-lines-between-2-tokens-in-a-text-file-using-bash), but had to modify it for using `sed` on Mac OSX (you need the `-E` option).

```bash
# Here is the sed command
sed -E -n '/^MODEL +1 /,/^ENDMDL/w 1qLz-model1.pdb' 1qlz.pdb
```

!!! info Explanation

    `sed -E` use extended regular expressions
    `-n` do not echo every line to output
    `'/START/,/STOP/'` pattern to search for; we start at lines that begin with `MODEL 1` and end with lines that begin with `ENDMDL`
    `^` is Regex for the beginning of a line
    `<space> +` search for 1 or more spaces
    `1 <space>`, search for the number 1 followed by a space (or else you get model 19)
    `w 1qLz-model1.pdb` write the output to the file `1qLz-model1.pdb`
    `1qlz.pdb` is the input file


Check that your protein is indeed the human prion protein. It is easy to mistake `1qlz` for `1q1z`. That is why it is best to use lowercase letters for the structure file names (except for the letter, L, where we use upper case), because then the letter, `o`, will not be mistaken for the number `0`.




[^1]: The [Python Regex Cheat Sheet](https://www.geeksforgeeks.org/python-regex-cheat-sheet/) has a list of many common regular expressions and is a useful reference.



