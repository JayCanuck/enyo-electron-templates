# enyo-templates-electron
A collection of [electron](https://github.com/electron/electron)-based app templates for [enyo-dev](http://github.com/enyojs/enyo-dev). It allows for powerful webapps developed in Enyo to be packaged within a self-contained environment and binary executable for Windows, Mac, and Linux.

--------------------

##Installation
Start by cloning this repository (or downloading and extracting the repository zip) to a desired location. From there, you can add the templates to enyo-dev via:

```
enyo templates add electron
enyo templates add electron-onyx
enyo templates add electron-moonstone
```
As the names would imply, `electron` is the basic Enyo core with electron support, `electron-onyx` is the same with with a basic onyx UI, and `electron-moonstone` is mostly the same with a basic moonstone UI. The main difference with `electron-moonstone` is that the window frame is hidden in builds, the `moonstone/Panels` close button actually closes the window, and you can move the window around by dragging on the top of the window.

##Usage

To create a new project with a given template, create a new directory and then within it, initialize with with enyo-dev. For example:

```
enyo init --template=electron
```

##Gulpfile
Included in each template is a gulpfile for your projects. Be sure to run `npm install` on your project and have gulp-cli installed on your system (`npm install -g gulp-cli`). The following gulp tasks are available:

* `init` - Fetches the enyo libraries via enyo-dev
* `enyo` - Builds the app with enyo-dev
* `electron` - Packages built app with electron for the current platform
* `electron-all` - Packages built app with electron for all available platforms
* `run` - Runs the built app directly with electron without packaging
* `build` - Combination of the 'enyo' task then the 'electron' task
* `build-all` - Combination of the 'enyo' task then the 'electron-all' task

For `enyo` (and by extension `build` and `build-all`), all extra arguments/options will be forwarded to the `enyo pack` command.

For `run`, using -P/--production will disable the navigation/developer toolbar with electron-moonstone template.

The default task is `build`
