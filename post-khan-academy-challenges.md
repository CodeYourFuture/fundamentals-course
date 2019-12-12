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

In the spin-off, change your code so that each fish is represented by an object, with `x`, `y`, `speed`, `colour`, and perhaps `size` variables.

Add bubbles to your fishtank (if you have not, already), and make these objects, too. (`x`, `y`, and perhaps `size`).

# Challenge: many snowmen, with objects!

Go back to the ["simple snowman" challenge](https://www.khanacademy.org/computing/computer-programming/programming/drawing-basics/pc/challenge-simple-snowman) and make a spin-off.

You don't need to animate this one, so you don't need a `draw()` function.

* In the spin-off change the code so that you draw 100 snowmen in random places.  
* Use an object to keep track of the position of each snowman.
* optional: try to have each snowman be a different size
* optional: (very advanced) - can you have each snowman choose from 3 different faces?  One way to do this would be to have three functions: `drawFace1(x, y, size)`, `drawFace2(x, y, size)`, `drawFace3(x, y, size)` and somehow choose between them for each snowman/snow-woman.
* optional: It would be nice to give the snow-people a colourful hat and scarf.
