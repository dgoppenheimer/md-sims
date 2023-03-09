---
date: 2023-03-08
---

# Images and Videos

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

### Image Tests

See the Material for MkDocs documentation for [images](https://squidfunk.github.io/mkdocs-material/reference/images/) for these examples.

#### Image Alignment and size with `attr_list`

```md
![Image title](https://dummyimage.com/600x400/eee/aaa){  width="300" align=left }
```

![Image title](https://dummyimage.com/600x400/eee/aaa){  width="300" align=left }
Donec congue pretium sollicitudin. Proin malesuada consectetur lectus, ac commodo lorem posuere ut. In sem nisi, malesuada quis nibh ut, sagittis gravida velit. Mauris sed posuere ligula. Cras suscipit mauris eu dictum porta. Pellentesque maximus tortor ultrices, blandit risus ut, facilisis massa. Aliquam et dolor eu dolor pretium porta. Nulla fermentum erat ante, nec hendrerit metus sodales et. Donec eget risus at odio pulvinar aliquam. Aenean sit amet mattis erat.

!!! note
    
    The image alignment does not work if both `attr_list` and `markdown_captions` are enabled in `mkdocs.yml`. The `markdown_captions` extension uses the image title as the image caption. Since it doesn't work with `attr_list`, I will disable it for now.


!!! success

    This works fine.

#### Image Captions using `md_in_html`

```md
<figure markdown>
  ![Image title](https://dummyimage.com/600x400/eee/aaa){ width="300" align=left }
  <figcaption>Image caption</figcaption>
</figure>
```

<figure markdown>
  ![Image title](https://dummyimage.com/600x400/eee/aaa){ width="300" align=left }
  <figcaption>Image caption</figcaption>
</figure>
Nunc fringilla consectetur augue sit amet commodo. Curabitur turpis augue, euismod ac mauris ut, porta accumsan dui. Curabitur in elementum urna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed egestas odio nulla, non blandit metus mattis sed. Nunc pellentesque lobortis dolor non bibendum. Cras eu elit leo. Morbi in imperdiet sapien, quis accumsan nunc.

!!! failure
    The re-sizing works, but the alignment does not.

This is not a big problem. I usually center images anyway, and most of the time I will be using the images in Jupyter notebooks on Colab. Jupyter's markdown parser is fairly basic so I will likely be using `html` to display images.

UPDATE: See the answer to [Is it possible to caption an aligned image?](https://github.com/squidfunk/mkdocs-material/discussions/4082) in the Material for MkDocs discussion forum. The key is to use the `inline` (left alignment) and `inline end` (right alignment) modifiers set up for admonitions.

```md
<figure class="inline end" markdown>
  ![Image title](https://dummyimage.com/600x400/eee/aaa){ width="300" }
  <figcaption>Image caption</figcaption>
</figure>
```

<figure class="inline end" markdown>
  ![Image title](https://dummyimage.com/600x400/eee/aaa){ width="300" }
  <figcaption>Image caption</figcaption>
</figure>
Nunc fringilla consectetur augue sit amet commodo. Curabitur turpis augue, euismod ac mauris ut, porta accumsan dui. Curabitur in elementum urna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed egestas odio nulla, non blandit metus mattis sed. Nunc pellentesque lobortis dolor non bibendum. Cras eu elit leo. Morbi in imperdiet sapien, quis accumsan nunc.

!!! Success
    Sweet! I'm lovin' it!

### Images on Google Colab

There are a few requirements that I have for using images in Jupyter notebooks on Google Colab:

1. I do not want to have to store the images in Colab or on my Google drive. This will take up valuable space as well as needing to transfer the images each time I use the notebook. This means being able to access the images over the web.
2. I want to be able to change the size of the images as I embed them.
3. I would like to be able to add image captions when I need them.
4. I would like the option of specifying the image alignment.

Here we will try the following:

```html
<figure markdown>
  [<img src="https://dummyimage.com/600x400/eee/aaa" alt="dummy image" width="250" align="left"/>](https://dummyimage.com/600x400/eee/aaa)
  <figcaption>Caption: this image should be small and on the left</figcaption>
</figure>
```

<figure markdown>
  [<img src="https://dummyimage.com/600x400/eee/aaa" alt="dummy image" width="250" align="left"/>](https://dummyimage.com/600x400/eee/aaa)
  <figcaption >Caption: this image should be small and on the left</figcaption>
</figure>

Nunc fringilla consectetur augue sit amet commodo. Curabitur turpis augue, euismod ac mauris ut, porta accumsan dui. Curabitur in elementum urna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed egestas odio nulla, non blandit metus mattis sed. Nunc pellentesque lobortis dolor non bibendum. Cras eu elit leo. Morbi in imperdiet sapien, quis accumsan nunc.

!!! note

    When we use the `<figcaption>` tag, the alignment applies to the caption and image as opposed to the image+caption relative to the surrounding text. But we still get image resizing, which is good. To make it a bit simpler, we could remove the markdown link notation \[...\](...), which links the image to the full-sized image. So far this solves 1 and 2, sometimes 3, but not 4.

    Another interesting thing is that if you put quotes around the `left`, then the caption is on the right side of the image.

Next we will try using `html` in `markdown` to achieve image resizing and alignment (but no caption)

```markdown
[<img src="https://github.com/dgoppenheimer/notebook-images/blob/main/connect.png?raw=true" alt="connect to a runtime" width="350" align="right"/>](https://github.com/dgoppenheimer/notebook-images/blob/main/connect.png?raw=true)
```

[<img src="https://github.com/dgoppenheimer/notebook-images/blob/main/connect.png?raw=true" alt="connect to a runtime" width="350" align="right"/>](https://github.com/dgoppenheimer/notebook-images/blob/main/connect.png?raw=true)

Nunc fringilla consectetur augue sit amet commodo. Curabitur turpis augue, euismod ac mauris ut, porta accumsan dui. Curabitur in elementum urna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed egestas odio nulla, non blandit metus mattis sed. Nunc pellentesque lobortis dolor non bibendum. Cras eu elit leo. Morbi in imperdiet sapien, quis accumsan nunc.

!!! note

    This solves 1, 2, and 4, but not 3.

The `markdown_captions` extension does not help very much. You only get centered images using the image title as the caption.

To get more sophisticated image captions, I'll have to use `CSS`. This will be fine for the MkDocs site, but will likely be too complicated to use for routine Jupyter notebooks.

## Videos

Install the [MkDocs plugin for video](https://github.com/soulless-viewer/mkdocs-video):

```zsh
pip install mkdocs-video
```

Enable the plugin in `mkdocs.yml`:

```yaml
plugins:
    - mkdocs-video
```

Add the installation to `ci.yml`:

```yml
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - run: pip install mkdocs-video
```

### Usage

```markdown
![type:video](https://www.youtube.com/embed/LXb3EKWsInQ)
```
