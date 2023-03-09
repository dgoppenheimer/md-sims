---
date: 2023-03-08
---

# Videos and Images

## Videos

## Images

The [Material for MkDocs documentation](vhttps://squidfunk.github.io/mkdocs-material/reference/images/) is the place to start for information on how to add images to pages.  

In addition to `attr_list` and `md_in_html`, I also added `markdown_captions` to my `mkdocs.yml` file:

```yaml
markdown_extensions:
  - attr_list
  - md_in_html
  - markdown_captions
```

However, when I built the site I got the following error:

```zsh
ERROR    -  Config value 'markdown_extensions': Failed to load extension
        'markdown_captions'.
        ModuleNotFoundError: No module named 'markdown_captions'
```

Doh! I forgot to install the extension!

```zsh
pip install markdown_captions
```

And add it to `ci.yml`:

```yaml
name: ci 
on:
  push:
    branches:
      - main
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-python@v2
        with:
          python-version: 3.x
      - run: pip install mkdocs-material 
      - run: pip install mkdocs-video
      - run: pip install markdown_captions
      - run: mkdocs gh-deploy --force
```

 - run: pip install markdown_captions`


