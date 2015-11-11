# Learn Grunt and Bower

Workshop to learn Grunt and Bower with hands-on exercises.


## Install tools

On Windows you need Git Bash: https://git-scm.com/downloads

You also need Node.js and npm which are both installed from: https://nodejs.org/

## Open Git Bash

We are going to run all our commands in Git Bash.

## Install Grunt

If you haven't already installed Grunt, run

```
npm install -g grunt-cli
```

## Fork this repository on Github

If you don't have a Github account, you can make one at: https://github.com/join

With your account, you can then browse to https://github.com/ebabel-eu/learn-grunt-bower and fork the repository (top right button).

Your code will be checked in to your own repository for later reference.

## Clone your repository on your computer

In Git Bash, or any other tool where you normally manage Git, clone your own repository locally:

```
git clone https://github.com/[your username]/learn-grunt-bower.git
```

You can then switch to that directory to run your commands:

```
cd learn-grunt-bower
```

## Grunt scaffolding

It's possibly to copy paste your Grunt from an existing project, but we're going to look into grunt-init scaffolding.

```
npm install -g grunt-init
```

On Windows, your grunt init scaffolding templates are to be installed in %USERPROFILE%\.grunt-init\

There are several templates you can use. The one I recommend is a very simple Gruntfile template.

Got to the correct director and clone this repository:

```
git clone https://github.com/gruntjs/grunt-init-gruntfile.git
```

Once that repository is checked out, let's switch back to your own learn-grunt-bower repository directory to create a new Gruntfile from that template.

## Install a Gruntfile from a template

```
grunt-init gruntfile
```

You are presented with a series of questions that will make it possible for the template to create the correct Gruntfile.

Commit your code.

```
git add .
git commit -m "Basic Gruntfile installed from template."
```

## Exercise

For your first exercise, we will checkout a new branch in your repository and create a Gruntfile with another scaffolding template.

```
git checkout -b second-template
```

Install a second scaffolding template, delete your Gruntfile and run grunt-init to install the alternative template.

Once you're done, commit your new branch.

```
git add .
git commit -m "Alternative Gruntfile installed from another template."
```

You can then switch back to your master branch.

```
git checkout master
```

























