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
$ nikola Build
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
