# Using `grep`

*Global regular expression print* know by its moniker, `grep` is a unix tool used for searching plain-text files for lines that contain a pattern and printing the result.

```bash

```


`grep -v` 

prints only the lines that don't match the search pattern.

`egrep` or `grep -E` for enhanced `grep`.

`grep -e` (e for expression)

prints lines that contain any of the search patterns.

```bash
grep -e "pattern1" -e "pattern2" input-file
```

This is also useful when your search pattern begins with a `-`.

```bash
# this does not work
grep ---foo

# this works
grep -e ---foo
```




