# Setting up your enviornment

1. Nikola requires python 2.7.9 or higher to work properly

  * Install python version managers [pyenv](https://github.com/yyuu/pyenv)
  * Install pyevn add-on [pyenv-virtualenv](https://github.com/yyuu/pyenv-virtualenv)
2. Start a python virtualenv using pyenv-virtualenv

  * Activate your new virtualenv
  * Use pip to install nikola

    `$ pip install nikola`

  * Install nikola ipython and zen-ipython themes

    `$ nikola install_theme ipython`

    `$ nikola install_theme zen-ipython`

# Activating your virtualenv using pyenv

This is the command you want if you already have the python 2.7.9 virtualenv setup:
```
$ pyenv activate nikola279
```

You can read more about how to make more virtualenvs using pyenv an the pyenv-virtualenv projects [pyenv-virtualenv](https://github.com/yyuu/pyenv-virtualenv)


# Deleting posts

Do this:
```
$ rm blog/posts/foo.rst
$ nikola build
$ nikola check -f
```

If everything on the list can be deleted (make sure there are no extra orphans):
```
$ nikola check -f --clean-files
$ nikola build
```
# Creating a new page
Do this
```
$ nikola new_page
```

and just add what you need to the markdown. Connect it up from conf.py. These are the lines of interest:
```python
NAVIGATION_LINKS = {
    DEFAULT_LANG: (
        ("/stories/charts.html", "About"),
        ("/archive.html", "Archive"),
        ("/categories/index.html", "Tags"),
    ),
}
```

# Creating new posts

Tell Nikola to make a new post:
```
$ nikola new_post -f ipynb
```

Inside your posts directory. Do this:
```
$ ipython notebook
```

# Publishing your posts!
Build first
```
$ nikola build
```

Then see if it works locally
```
$ nikola serve --browser
```

Then deploy to GitHub Pages
```
$ nikola github_deploy
```

You should push master and the source code as well.
```
$ git add .
$ git commit -m "message here"
$ git push
```
