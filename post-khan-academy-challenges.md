# Challenge: Make it rain... objects!

Make a spin-off of your "make it rain" project, and change it to store one array of **objects** instead of many arrays.

So instead of `xPositions`, `yPositions`, `speeds`, etc, you'll simply have `raindrops`, and each raindrop will have:
* an `x` property
* a `y` property
...

More ideas:

to each object add more properties:

* a `speed` property
* a `size` property to each object and randomise it at the start.
* a `color` property to each object - you can make a random colour like this: `color(random(255), random(255), random(255))`

* try with squares or rectangles
* try with images.


# Challenge: Fishtank v2 - using objects

Go back to your [https://www.khanacademy.org/computing/computer-programming/programming/functions/pp/project-fish-tank](fishtank project), and make a spin-off.

In the spin-off, change your code so that each fish is represented by an object

fish objects have these properties
* `x`, 
* `y`, 
* `speed`, 
* `colour`, and perhaps 
* `size`.

*Add bubbles* (if you have not, already):

Make these bubbles objects, too, with these properties:
* `x`, 
* `y`, 
* `size`
* `speed` (if you want some to move at different speeds)

Add a pebble sea-bed

Add *seaweed*:
* random x pos, fixed y pos
* random height
* random color *variation*

### Advanced - clickable bubbles

Make each bubble clickable - when you click it it changes in colour.  To track which bubbles have been clicked, you should add a `clicked` property to each bubble object.

Use the function `dist(x1, x2, x2, y2)` to find the distance between two points.

### Advanced - have fish swimming the other way.

# Challenge: many snowmen, with objects!

Go back to the ["simple snowman" challenge](https://www.khanacademy.org/computing/computer-programming/programming/drawing-basics/pc/challenge-simple-snowman) and make a spin-off.

You don't need to animate this one, so you don't need a `draw()` function.

* In the spin-off change the code so that you draw 100 snowmen in random places.  
* Use an object to keep track of the position of each snowman.
* optional: try to have each snowman be a different size
* optional: (very advanced) - can you have each snowman choose from 3 different faces?  One way to do this would be to have three functions: `drawFace1(x, y, size)`, `drawFace2(x, y, size)`, `drawFace3(x, y, size)` and somehow choose between them for each snowman/snow-woman.
* optional: It would be nice to give the snow-people a colourful hat and scarf.


# Challenge: shooting stars, with objects

Go back to the ["shooting stars" project](https://www.khanacademy.org/computing/computer-programming/programming/animation-basics/pp/project-shooting-star) and make a spin-off.

* In the spin-off, change your code so that shooting stars are represented by objects.  Each star would have an `x` and `y`, and a `xSpeed` and `ySpeed`.  (To move the star increment `x` by `xSpeed`, and `y` by `ySpeed`.)
* If you didn't already add some buildings for a skyline, do so now.
* Each building should be an object with x, y, and height.
* You don't need to draw the windows if you haven't already done that.


# p5.js Challenge - font outline

(If you've seen p5.js and openprocessing before)

* Fork (spin-off) [this "font as dots" challenge project](https://www.openprocessing.org/sketch/812356)
* Read the code comments for details
* Essentially, you are provided with an array of points on the outline of some text, and you must draw a circle at each point.
