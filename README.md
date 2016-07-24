# Website Performance Optimization portfolio project

In this challenge, the goal was to optimize the provided online portfolio for spree.  In order to do this, the critical rendering path had to be optimized to make the page render as quickly as possible.  

In the main index.html, the goal was to attain a PageSpeed score of at least 90

##Downloading Project Files

The files for this project can be cloned or downloaded from the following GitHub repository [here](https://github.com/acampos645/acampos645.github.io).

##Optimization of index.html for PageSpeed Score

In order to improve the PageSpeed score for the index file, the following optimizations were made:

* async tag added to js script calls as they were not render blocking
* removed Google Font tag
* inlined and minified contents of style.css
* losslessly compressed jpg files using compressor.io

##Main.js - Pizza Size Switching

In order to optimize the pizza size-switching function, the changePizzaSizes function was simplified.  Instead of having to calculate the change in and new size, three scenarios are provided (25%, 33.3% or 50%).  Then, a for-loop cycles through the pizza containers and applies the change in size to each.

Additionally, the querySelectorAll method was replaced with getElementsByClassName which has a better performance.

##Main.js - Scrolling pizzas

To improve the FPS of the pizzeria page, changes were made relating to the scrolling pizzas in the background of the page. To do this, the following changes were made to the updatePositions function:

* In style.css, will-change, transform and backface-visibility properties were added to the .movers class.
* The document.body.scrollTop call was removed from the for-loop and moved into the global function scope since it only needs to be determined once.
* For each scroll, there are only 5 possible phase changes, so these were calculated using a separate for loop before changes are applied to the moving pizzas.  The next for loop cycles through the list of .mover pizza elements and applies one of the five previously calculated phases.
* The total number of moving pizzas that the page renders was changed from 200 to a dynamic value.  The number generated will be calculated according to the size of the user's screen.