# My AI Hugo Website
So basically I made this website to be able to see what I can do with AI. I also use a modified [`hugo.386`](https://themes.gohugo.io/themes/hugo.386/) theme that I will fork to make a make a TempleOS themed site.(You know, as a meme.)

## Requirements
Here I show what packages need to be installed, turns out there is not much to install.

### `Hugo`
First of all you will need to install hugo, you can do this by following the instructions for you platform found here: 
https://gohugo.io/installation

### `Git`
You will then need git. You should know how to do this if you are a programmer, but if not here is a link:
https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

## Running a local server
To run a local server just go in the terminal in the root of this folder(it should be called `rayvert64.github.io` unless you changed the name of this repo) and run:
``` bash
$ hugo server
```
As easy as that.

## Developement
This is where things get a little more tricky. I use a git submodule for the `hugo.386` theme. Therefore you want to make sure that that git submodule is up to date before starting to code.

First of make sure that the repo is up to date with a fetch and a pull.
``` bash 
$ git fetch --all
$ git pull # I usually like to write `git poule` because "poule" means "chicken" in french and that makes me happy. :) `git config --global alias.poule "pull"`
$ git checkout develop # If you are just playing this is fine
$ git branch <NAME-OF-YOUR-BRANCH> # Do this if you actually want to merge in develop in the future.
```

**RUN THIS EVERY TIME YOU START WORK AND BEFORE PUSHING**
``` bash
$ git submodule update --init --recursive
```

All the work should be done on branches based on the current `develop` branch. So if you think you will be working on the submodule please make sure that you are on the right branch:
``` bash 
$ git submodule foreach git checkout develop # or <NAME-OF-YOUR-BRANCH> if you are doing your own thing # I assume that if I add other submodules I will be working on them at the same time.
```

Sadly git has no way of adding/commiting changes for a submodule unless you do apply one command to all of the submodules simultaniously... so if you ever want to commit/push you will have to go in the `./themes/hugo.386` folder and perform your git commands there. :(

