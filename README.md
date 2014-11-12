Css2Sass
========

Sublime text plugin to convert CSS in the clipboard to SASS on your screen. Also supports converting javascript to coffeescript in the same manner.

![demo](images/Css2Sass.gif)

### Installation

To install, well, come talk to me and I'll sort it out for you. Soon it'll be in package control. Read on for more options, and see the sections below and the 'Setup Issues' section for more information.

###### Installing through package control

Coming soon...

###### Installing the hard way

1. Clone repository to your Sublime Text Packages directory.
2. Follow all other instructions.

### Usage

Insert CSS from your clipboard into a .css.sass file using `"super+k+v"`. The CSS will be inserted into your file as SASS. Perfect for copying straight from Stack Overflow.

This plugin is intended to be very much a background worker. To that end, I recommend mapping `"super+v"` to the `"css_to_sass"` command in your user key bindings. 

```json
# Preferences/Key Bindings - User

[
    {
        "keys": ["super+v"], "command": "css_to_sass"
    }
]
```

From there, you can start pasting raw CSS into your .css.sass files and be amazed as pure sass goodness is pasted into your file, and all text pasted into other files will be pasted in as usual (so no worries there!)

### Setup Issues

###### Sass Gem

You must have the sass gem installed to use the CSS to SASS feature of this plugin. Internally, we use the `sass-convert` command, which requires the sass gem. To install the sass gem visit http://sass-lang.com/install.

###### Converting JS to CoffeeScript

To use the JS to Coffeescript automagical conversion you need to have the `js2coffee` Node Package Module installed (https://www.npmjs.org/package/js2coffee). If you don't have js2coffee installed, you can easily install it with the following command:

```bash
$ npm install -g js2coffee
```

If you don't have npm installed then you can follow the instructions here http://blog.npmjs.org/post/85484771375/how-to-install-npm. 

###### Ruby Version Managers

If you are using RVM or rbenv etc, then you will need to set the path in settings, as RVM/rbenv modify the environment path, which messes with sublimes use of the path.

To find your path you can run `echo $PATH` on the command line. Copy the result then paste it into the Css2Sass user settings file, as shown below.

```json
# Preferences/Package Settings/Css2Sass/Settings - User

{
    "path": "your/copied/path/here"
}
```

### Known Issues

There is an issue with the paths and RVM/rbenv. Sublime Text will not load with the correct paths to find Sass if it is not loaded from the command line. At the moment I am not sure what to do about it, and am happy to hear ideas. The same issue is occuring here https://github.com/badsyntax/SassBeautify/issues/53. You can get around this by opening Sublime Text from the command line, or, if you're hardcore and want to solve the issue permanently, you can follow these instructions: http://unix.stackexchange.com/questions/89076/how-to-set-the-path-osx-applications-use/89077#89077.

If you find more, create an issue or let me know on twitter ([@nmdowse](http://www.twitter.com/nmdowse "Nick Dowse twitter")). Most of the hard work was done by the creators and maintainers of SassBeautify, another great Sublime Text Plugin. So, thanks to them!
