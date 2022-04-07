# Building This Site

```bash

```

On GitHub I forked the `mkdocs-material` project.
Go to Settings on GitHub and rename the repository to `md-sims`.
Clone it locally.

```bash
cd ~/Sites
git clone https://github.com/dgoppenheimer/md-sims.git
cd md-sims
git remote -v
    origin	https://github.com/dgoppenheimer/md-sims.git (fetch)
    origin	https://github.com/dgoppenheimer/md-sims.git (push)
git status
    On branch master
git branch -m master main
git status
    On branch main
git push -u origin main
```

Go to GitHub and set default branch as main.

Settings  Branches 

Then delete the master branch from the remote repository

```bash
git push origin --delete master

```


```bash
cd md-sims
mkdocs serve
INFO     -  Building documentation...
ERROR    -  Config value: 'plugins'. Error: The "redirects" plugin is not
            installed
Aborted with 1 Configuration Errors!
```

Open `mkdocs.yml` and delete the `redirects` and `minify` plugins.

```yml
plugins:
  - redirects:
      redirect_maps:
        changelog/insiders.md: insiders/changelog.md
        reference/meta-tags.md: reference/index.md
        reference/variables.md: https://mkdocs-macros-plugin.readthedocs.io/
        sponsorship.md: insiders/index.md
        upgrading.md: upgrade.md
  - minify:
      minify_html: true
```

Make changes to `mkdocs.yml`

See copy of file in repository.


!!! Success

        The site builds locally.


Commit local changes and push to origin.

Go to GitHub Settings Pages Source and change source to `gh-pages` (already done)

make a change and push again.


Change the workflow file to `ci.yml`

!!! Success

    The site builds on GitHub pages.


Start modifying the landing page.

Modify `material/overrides/home.html`:  
Remove the text `Set up in 5 minutes.`  
Change the Title text to `Practical Molecular Dynamics`  
Delete the `Get Insiders` button.  
Add `favicon.png` to `material/assets/images/` and to `docs/assets/`  
Add the other favicon sizes to `docs/assets/`  
Add landing page image to `docs/assets/images/` and name it `illustration.png`.  
Delete announcement block from `material/overrides/main.html`


