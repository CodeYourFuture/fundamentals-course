# Using p5.js after Khan Academy's processing.js courses

If you enjoyed using javascript to make drawings and animations, I recommend further study and play with the very, very similar p5.js library.  It's better.

Instead of writing programs on the khan academy site, I suggest using the site [openprocessing](https://openprocessing.org) (or codepen).

## Where to start coding with p5.js

* I recommend the site called ["openprocessing"](https://www.openprocessing.org/) - it makes it easy to click ["new sketch"](https://www.openprocessing.org/sketch/create) and start immediately.  
 * Alternatively, [here's a starting sketch](https://www.openprocessing.org/sketch/812085) that defines functions the way you have learned so far
* If you want to use codepen, here's a [p5.js starting "pen" in codepen](https://codepen.io/enz0/pen/vYEXyZr?editors=1010)
* If you want to see the whole picture of html and javascript together, [here's a website project on glitch](https://glitch.com/~cyf-p5js-start) with html, css, and javascript files. 
* [Here's a tutorial for a random words poster](https://www.openprocessing.org/sketch/812093) which works through a project using p5.js

## Why change?

* Khan Academy platform is not stable for complicated programs
* Khan Academy doesn't "feel professional" or "polished"
* processing.js library has been retired
* p5.js is much more widely used than processing.js
* p5.js has more and better documentation and tutorials
* p5.js is more advanced and more powerful than processing.js.  You can make sketches that: 
    * process video from the webcam
    * [process audio from your microphone](https://www.openprocessing.org/sketch/812282) - ([simplest example](https://www.openprocessing.org/sketch/812284/)).
    * load and show 3d models
    * interact with all sorts of other interesting javascript libraries
        * random example: [p5.js pose-detection with using PoseNet](https://codepen.io/enz0/full/wvBzoMN)
* You can use *modern* javascript language features, which make things nicer.

However, some of my favourite differences are very, very small.  Here's one:

#### pick one element at random from an array

If you have an array, you can pick one element of it at random, simply by passing the array as a parameter to the `random()` function.

Example:

```
//(inside your draw() function...)

var colorNames = ["maroon", "skyblue", "whitesmoke"];
var chosenColor = random(colorNames);
fill(chosenColor);

var words = ["code", "your", "future"];
var chosenWord = random(words);
text(chosenWord, 100, 100);
```

## Best place to learn p5.js: Daniel Shiffman: "Code! Programming with p5.js"

I recommend Daniel Shiffman's youtube course: ["Code! Programming with p5.js"](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA).  "p5.js" is another drawing library nearly identical to the "processing.js" library that you've been using in the Khan Academy course (except p5.js is more powerful and now much more widely used than processing.js).

### what's openprocessing.org ?
The above course introduces a website called "p5.js web editor" which allows you to quickly write your projects and test them out.  It's ok, but I happen to prefer a different website which does the same thing: https://www.openprocessing.org/

One reason I like this site instead for p5.js work is that it has [a huge gallery of work by other artists](https://www.openprocessing.org/browse/), and you can see all of their code to learn from*!

### when you read others' code and it makes no sense...

(* **Don't Panic!** Do not be worried when you find a project that looks amazing but then you look at the code and can't understand it - this is normal.  These projects can become VERY complex and the artists often aren't very concerned about how easy their code is to read.  And code reading is a skill you have to work on.  Take it slow.  Study simpler projects to start with.)

## Other courses

In addition to ["Code! Programming with p5.js"](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA)...

* The creators of processing have [a p5.js course on kadenze.com - "Introduction to Programming for the Visual Arts with p5.js"](https://www.kadenze.com/courses/introduction-to-programming-for-the-visual-arts-with-p5-js-vi/info)
* Joshua Davis has some courses on processing on skillshare, which is free for 2 months.
[Programming Graphics I: Introduction to Generative Art](https://www.skillshare.com/classes/Programming-Graphics-I-Introduction-to-Generative-Art/782118657).  This does *not* teach in javascript but in Processing, which uses the Java language instead.  However, if you LOVE the topic, you could skim these videos and still learn a lot.  Normally I would recommend getting strong in ONE language (JavaScript) for the first year or two of your programming journey.
* Mostly aimed at teachers: [Introduction to Computational Media with p5.js](https://nycdoe-cs4all.github.io/) has material for teachers to run a course.  Students can find some interesting project ideas.

* If you want to stick with processing.js and Khan Academy longer, there is [Advanced JS: Games and Visualizations](https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations).  I haven't worked through this course, yet.

# Other migration guides

* If you want to stick with processing.js, Khan Academy have [this guide to using processingjs outside khan academy](https://www.khanacademy.org/computing/computer-programming/programming-games-visualizations/advanced-development-tools/a/using-processingjs-outside-khan-academy)


## List of important differences between (khan academy) processing.js and p5.js

### You must always define the `draw()` function.
* The draw() function is not optional.
* All drawing operations (fill, ellipse, rect, etc) should go inside the draw() function.

### You can provide a `setup()` function for set-up

It will be called before the first call to your `draw()` function.


### If you *don't* want animation, you must call noLoop()

Unlike khan academy's processing.js, you must always define a draw() function, even if you don't want animation.  
`noLoop()` and `loop()` can be used to prevent or enable animation by repeated calls to the `draw()` function.  The default is to animate.

[Live Demo](https://www.openprocessing.org/sketch/812071)
```
var setup = function(){
    noLoop();
}
var draw = function(){
    fill(random(255), random(255), random(255));
    rect(50, 50, 400, 400);
}
```

### You can't call processing.js functions at the top level

You can't call functions like `random()`, `fill()`, `color()`, `rect()` at the top-level (i.e.) outside of the p5.js functions such `setup()`, `draw()`, `mousePressed()`, etc.  

If you try to do this, you'll get an error such as `Uncaught ReferenceError: random is not defined`

The editor at openprocessing.org is kind enough to add the following good advice - read your error messages!:  `Did you just try to use p5.js's random() function? If so, you may want to move it into your sketch's setup() function.`


### Global variables must be initialised in `setup()`, if they need p5.js functions
* If you want a *global* variable to be initialised at random, using p5.js's `random()` function, you must do it in two parts:
    1. Declare the variable `var xPos;`
    1. Initialise the variable in `setup()`.  Example: `xPos = random(0, 400);`

**GOOD CODE example** - do this if you need to initialise a global variable using `random()` or `color()` or `width` or `height`...

```
var xPos;

var setup = function(){
    xPos = random(0, 400);
};
```

**BAD CODE example** - this won't work

```
//start of program
var xPos = random(0, 400);  // can't call random() outside of setup() or draw(), etc.
var draw = function(){
    rect(xPos, 100, 50, 50);
};
```

### The default canvas is only 100, 100...

however, you can make it bigger calling `createCanvas()` in `setup()`

```
var setup = function(){
    createCanvas(windowWidth, windowHeight);
}
```
[Live Demo of specifying canvas size](https://www.openprocessing.org/sketch/create)

p5.js provides global variables `windowWidth` and `windowHeight`, AND `width` and `height` which will hold the size of the canvas.

### Where's the documentation?

* The documentation is at https://p5js.org/reference/
* Each function has multiple examples of how it can be used.
