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

##Main.js - Scrolling pizzas

To improve the FPS of the pizzeria page, changes were made relating to the scrolling pizzas in the background of the page. To do this, the following changes were made to the updatePositions function:

* The document.body.scrollTop call was removed from the for-loop and moved into the global function scope since it only needs to be determined once.
* Changes to the layout and style were separated into two different for-loops.  The first cycles through an array of moving pizza elements and determines the new positions.  The second cycles through the same pizza elements and applies the new position to the element styles.
* The total number of moving pizzas that the page renders was reduced from 200 to 40 in order to decrease the number of elements to be rendered.
