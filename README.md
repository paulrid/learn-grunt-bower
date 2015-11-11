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

Respond Yes to everything except the final confirmation where you can say you don't need to make changes.

The "Y" is in capital when it's the default answer, you can also just press [enter] to choose it.

You should now have both a Gruntfile.js and a package.json file we'll get into in a moment.

Commit all your code changes.

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

Here's some alternative templates you may be interested in:

- https://github.com/gruntjs/grunt-init-jquery
- https://github.com/gruntjs/grunt-init-node

Once you're done, commit your new branch.

```
git add .
git commit -m "Alternative Gruntfile installed from another template."
```

If you want to go further with Grunt templates and learn how to write your own templates, take a look at http://gruntjs.com/project-scaffolding

You can now switch back to your master branch.

```
git checkout master
```

## Install npm dependencies

npm manages some of your dependencies. Most of the time, they will be the kind of dependencies you use in your development environment, but they could also be server side dependencies or even client side dependencies that will get processed by a library like Babel (ES6 -> ES5) and webpack (alternative or in combination with Grunt).

The basic gruntfile template should have also installed a basic package.json file that lists some dependencies, however these dependencies aren't installed yet.

Take a moment to look at them in package.json then install them all with:

```
npm install
```

## npm dependency versions

There are 3 different ways to manage your library versions in package.json.

If you want to strict install a specific version of your npm dependency, use a version without any prefix (^ carret or ~ tilde).

If you can trust the middle number of the version, which is meant for backward compatible versions of the library, use a ~ tilde.

If you are certain it's ok to always install the absolute latest, which may include breaking changes at each install, use a ^ carret.

The prefix you choose depends on the policy you have setup in your team.

You can read more about the major.minor.patch semantic versioning system there: http://semver.org/

Please note that not every library programmer strictly follows semantic versioning.

## Exercise

Edit your package.json with different combinations of ^ carret, ~ tilde and version numbers to see if you fully understand how npm install will resolve the library versions. 

If you get unexpected results, try to figure them out by looking at the npm repository of that library, especially the release history at the bottom.

- https://www.npmjs.com/package/grunt-contrib-jshint
- https://www.npmjs.com/package/grunt-contrib-watch
- https://www.npmjs.com/package/grunt-contrib-qunit
- https://www.npmjs.com/package/grunt-contrib-concat
- https://www.npmjs.com/package/grunt-contrib-uglify




































