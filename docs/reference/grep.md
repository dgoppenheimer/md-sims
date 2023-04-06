---
title: Using grep
date: 2023-03-29
---

The word `grep` is derived from a contraction of the command `g/re/p`, which is short for "Global search for Regular Expression and Print matching lines". Currently `grep` is a command line Unix/Linux utility for searching text files for particular strings of characters. It uses [regular expressions](https://en.wikipedia.org/wiki/Regular_expression), also known as `regex`, to specify the pattern to match when searching.

[grep command in Unix/Linux](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

In terminal, type `man grep` to get the help page for the `grep` command. To exit the `man` page, just type `q`.

Usage:

```zsh
grep [options] pattern [files]
```

Options: (list some of the common options here)

## Basic Syntax

### Delete lines that match a pattern

To delete lines that match a pattern, use the `-v` option. This option does an inverted match and keeps the lines that do not match the pattern.

```zsh
grep -v "words to delete" myfile.txt > tmpfile && mv tmpfile myfile.txt
# the words that do not match the pattern are written to tmpfile
# the && is used to join multiple commands
# the contents of tmpfile are then used to overwrite the original file, myfile.txt
```







---

## Other Resources

Here are two of many `grep` tutorials on the web:

- [How To Use grep Command In Linux / UNIX With Practical Examples](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)
- [Grep Command in Linux/UNIX](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix)

## Notes

Create a general `grep` tutorial with an example file (constructed from a random word generator). The file should be long enough that none of the example queries can be accomplished using a text editor.

Also create a tutorial using a several files from the RCSB PDB. Use relatively large, multi-chain containing files.

These will be relatively easy to grade. The sample `grep` commands will always produce the same output, and any created files can be compared using `diff`
.

The goal is to get the students comfortable using `grep` (and `sed`) to examine the RCSB `.pdb` files and not completely reliant on programs like ChimeraX to prepare proteins for docking and MD simulations.
