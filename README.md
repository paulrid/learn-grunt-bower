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
grunt-init grunt-init-gruntfile
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

## Running Grunt

You can organise your Grunt tasks in sets. 

With the basic template you used to create your Gruntfile, you are getting a default set of tasks you can run with:

```
grunt
```

Don't worry if the tasks are not execting successfully, that's because you haven't written any qunit tests.

When you run `grunt`, it runs just once. 

This could be used as a final build before deployment, to run absolutely all the tasks needed for the project, however there is not hard and fast rule, so you could organise your default Grunt tasks for another purpose than preparing a deployment, like just running some of your development tasks just once instead of continuously.

### Running Grunt continuously

If you do want to run your tasks continuously and re-run them when you change certain files, use watch:

```
grunt watch
```

### Running a single Grunt task

It's also possible to run a specific grunt task on its own.

```
grunt jshint
```

### Fix the package.json file

The package.json file create by default isn't very complete. You can install a better package.json with

```
npm init
```

## Exercise

Aim to run the default set of grunt tasks without failing the build. 

Try to fix any build error by looking carefully at the error message, working out what it means and how to solve it.

You should be able to get a dist directory created by grunt tasks with js and min.js files.

To make this exercise easier, you could simplify your Gruntfile.js further by removing some of the tasks.

Commit your code.

## Banner

Look at the banner at the top of your Gruntfile.js and compare it with the .js and .min.js that have been created by running your tasks.

The banner is placed at the top of your js file and allows the usage of variables read from package.json

You could however read from any file. For example, you could have a config.json file with a few settings you keep separate from Gruntfile.js, to keep it tidier or possibly have different config.json files depending on your deployment environment.

## Exercise

Modify the values in package.json and check the banner does indeed reflect this when running grunt.

Commit your code.

## Exercise

Refactor the jshint configuration in your a config.json file and read this from Gruntfile.js.

Commit your code.

## Create a separate set of tasks

You may want to create your own custom set of tasks. 

For example, you could have a set of tasks that concats your third party libraries. Since they are unlikely to change every time you modify your own Javascript code, it might be a good idea not to concat them as part of your watch.

## Exercise

Copy the default set of Grunt tasks, pick a different name than 'default' and run it with grunt [name of your set of tasks].

Commit your code.

## Any questions about Grunt?

Feel free to ask anything and we'll discuss it here.

## Comparison with Gulp

If time allows and someone is willing to talk about Gulp, we can recreate what we have built in Grunt with Gulp and compare the result.


## Bower

Bower is a front-end dependencies management tool. It makes it easy to install these dependencies and keep track of their versions.

If you haven't installed it already, run

```
npm install -g bower
```

## Initial bower.json

When starting a new project, you could copy/paste your bower.json configuration from a different project but it might be better to start with a fresh one:

```
bower init
```

## Exercise

Compare the usual bower.json you normally have and the bower.json created by bower init. Is there any difference?

## Install a third party library

You can install a library by running bower install followed by the name of that library.

```
bower install jquery
```

However, if you do this, your bower.json won't know what you just installed. Add --save or --save-dev to your installation.

```
bower install jquery --save
```

The difference between --save and --save-dev is that --save is a library you mean to be used in production and --save-dev is for libraries you won't publish as part of your deployed code, but are used nonetheless during your development. 

For example, the sass library of Twitter Bootstrap is  used during development to generate your CSS code, but it won't be published in deployment as such.

The distinction betweem --save and --save-dev is more to help keep your dependencies purpose clearer, but it's not a very big nor important difference.

## Install all libraries

Should you start a project with just a bower.json configuration and no bower_components installed, you can install all your dependencies with:

```
bower install
```

## Exercise

Install the usual libraries you work with and make sure they become part of your bower.json configuration.

## Versions

Check the version of jquery that was installed and documented in bower.json with --save.

It's the latest version, which isn't always what you need.

## Exercise

Pick an earlier version of jquery or some other library and re-run bower install. Check what happens in the bower_components directory.

## Install more than one version of the same library

Although it's not ideal, sometimes you need to install more than one version of the same library. This could be the case for jQuery for example.

Bower can specify the source of the library to install:

```
  "dependencies": {
    "jquery": "~2.1.4",
    "jquery-1.7.1": "http://code.jquery.com/jquery-1.7.1.js"
  }
```

## Exercise

Install two versions of the same library for a dependency other than jQuery.

## Dependencies of libraries

Sometimes, a library you install has its own dependency. For example, the bootstrap-sass library has a dependency on jQuery.

## Exercise

Clear dependencies from bower.json and bower_components then install bootstrap-sass. 

Note what has been installed in bower_components and what is written in bower.json as well as the command line log in Git Bash.

## Resolving dependency version conflicts

If you already have jQuery installed as a dependency of your project and you also want to install bootstrap-sass later, you may have a conflict depending on the minium jQuery version bootstrap-sass needs.

Bower will highlight this conflict and can help resolve it.

## Exercise

Clear your bower.json dependencies and bower_components. Write the following in bower.json

```
  "devDependencies": {
    "bootstrap-sass": "~3.3.5"
  },
  "dependencies": {
    "jquery": "1.7.1"
  }
```

Run bower install. 

```
bower install
```

Resolve the conflict with Bower's help. 

Check which version of jQuery is installed and how it's documented in bower.json

## Create your own Bower library

It's possible to make a private Bower library and place it on Stash, so that it can only be accessed within the company.

You can then organise your dependencies and give each of them its own repository.

On Stash, go to your profile page and create your own repository there.

You can then write any code you want to turn into a library and add a bower.json to that repository, so that your dependency has its own dependencies too.

## Exercise

Create a simple hello-world.js library on Stash and include it in your forked learn-grunt-bower repository.
























































