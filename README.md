# Polymer Happy Fun Time | Step One: Starting from Scratch

This is an experiment. It is a git-based tutorial for building a web application using Polymer. Instead of commits being just a way to track your progress, each commit is going to be a step in the tutorial. That way, you can jump to a commit and see the code, and follow along with comments.

The project I'll be walking you through is a simple web page that uses many of the web components featured in Google's [Polymer Element Catlog](https://elements.polymer-project.org/). At this stage in the process, the only thing I've done is created the application, added a gitignore file, and added a few comments to help you get situated. Finish reading through this Readme then feel free to peek around on your own!

## Creating a Polymer Application
If you want to create your own blank Polymer application, type the following in to your command line:

```
$ mkdir <your-application-name>
$ cd <your-application-name>
$ polymer init
```

You'll be guiding you through a series of prompts, asking you what you want to call your application, as well as the main element name. You can use the default values for now (just press enter; that's what I usually do), or you can add your own names. This tutorial is just going to cover using pre-built components, so we won't dive too deep into the world of custom elements (the "main element" the command line prompt asks for).

## Anatomy of a Polymer Project
Initializing an application generates a bunch of files and folders. I'll cover them briefly here.

### src
This is where your code lives. If you have any custom elements, they'll be here. It's not required to have a custom element and you *could* build an entire web page using just ready-made elements from Google/other developers, but where's the fun in that? So every Polymer project is initialized with a custom element (explained briefly in the bower_components section above) to get you started.

### bower_components 
This is a folder full of Polymer elements you can import into your project. The unit of Polymer is elements: think of them like souped up HTML tags. 

HTML is awesome, but it's vocabulary is pretty limited. Sure, you have `div`, `span`, `img`, etc, but those are the only "words" HTML understands. Polymer lets you expand that vocabulary. For example, what if instead of an endless series of `div` tags, the code body for a website looked like this:

```
<blog-header>Welcome to my blog!</blog-header>
<blog-post-container\>Welcome to my site!</blog-post-container>
<blog-footer>Welcome to my blog!</blog-footer>
```

You could have a robust, interactive website with only these three elements. In this case, blog-header, blog-post-container, and blog-footer are *custom elements*, meaning you write the code for them yourself, but Google (Polymer's benevolent overlord) has also provided a host of pre-built, robust elements in their [Polymer Element Catlog](https://elements.polymer-project.org/) that you can download to your project. These elements are stored in the bower_components folder, and downloaded via command line using [Bower](https://bower.io/) (go install that if you haven't already). If you want to add an element to your project, Google's catalog makes it as easy as copying and pasting the bower command. Just go to the element you like in the catalog, copy the command (in the left sidebar), paste it into your command line (make sure you're in the root of your project directory), and import it into the file where you want to use it. It's pretty neat.

### bower.json 
This is a json file that keeps track of all the components you've downloaded and what version they are. This can be really helpful for making sure you have the most recent versions of your components downloaded, but you can pretty much just ignore it.

### manifest.json 
Another file you can pretty much ignore for now. This is where you tell your application about itself, so if you ever want to know the name of your application, it's stored there. You can also add on to the file (file paths to app icons, for example) but again, don't sweat this one--we probably won't be going into it.

### test
If you want to write tests for your app, this is the folder to do it in. We won't get down that rabbit hole in this tutorial, but it's a really good idea--especially if you have custom element(s).

### README.md
That's this file! It's just a prettified text document written in markdown (hence the .md) to tell you what you need to know. Polymer includes a bunch of boilerplate in it (such as tellig you how to build/view your app), which I've included in the next section.

### index.html
This is the page that your computer looks for when a website is opened, and it's the file we're gonna be working with in this tutorial. You can import and use web components in a normal html file, which will be where we start. Polymer assumes you want to use your custom element, so it puts it in the html file for you.

### .gitignore
Tells git what files to ignore. Mine ignores build files and changes to the Mac OS file system (.DS_Store).

## Polymer Boilerplate
### Install the Polymer-CLI

First, make sure you have the [Polymer CLI](https://www.npmjs.com/package/polymer-cli) installed. Then run `polymer serve` to serve your application locally.

### Viewing Your Application

```
$ polymer serve
```

### Building Your Application

```
$ polymer build
```

This will create a `build/` folder with `bundled/` and `unbundled/` sub-folders
containing a bundled (Vulcanized) and unbundled builds, both run through HTML,
CSS, and JS optimizers.

You can serve the built versions by giving `polymer serve` a folder to serve
from:

```
$ polymer serve build/bundled
```

### Running Tests

```
$ polymer test
```

Your application is already set up to be tested via [web-component-tester](https://github.com/Polymer/web-component-tester). Run `polymer test` to run your application's test suite locally.