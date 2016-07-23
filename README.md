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

##Size Switching

In order to optimize the pizza size-switching function, 

##Pizzeria - main.js optimization

In order to improve the FPS on the page, 