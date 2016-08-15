# Website Optimization
## Project Overview
I will optimize a provided website with a number of optimization- and performance-related issues so that it achieves a target PageSpeed score and runs at 60 frames per second.

## Installation and Running the website optimization
Clone the GitHub repository and open index.html for PageSpeed Score and views/pizza.html for getting rid of Jank
```sh
$ git clone https://github.com/abdullahaalam/frontend-nanodegree-mobile-portfolio.git
```

## How to Start
* View my project! [Website Optimization Project](https://abdullahaalam.github.io/frontend-nanodegree-mobile-portfolio/)
* [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
* To open index.html - PageSpeed score of at least 90 for Mobile and Desktop!
* To open views/pizza.html - it runs at 60 FPS and time to resize is less than 5 ms

## Performance optimizations:
#### Part 1
* Removed google fonts
* Removed the call to style.css so it would not load for the index page
* Inlined all CSS
* Added media="print" for print.css
* Added async attribute for analytics.js
* Compressed all the image
#### Part 2
##### Optimize Frame-rate 60fps

* Declared this variable increases fps
```sh
var scroll = (document.body.scrollTop / 1250);
```

* Decreased number of pizzas created on page from 200 to 30
```sh
for (var i = 0; i < 30; i++) {

}
```
##### Time to resize is less than 5 ms

* Changed 'querySelectorAll' to 'getElementsByClassName' slightly reduces time to resize pizzas
```sh
var getRandomPizzaContainer = document.getElementsByClassName("randomPizzaContainer");
```

* Moved these variable declarations outside 'for' loop drastically reduces time to resize pizzas
```sh
var i = 0;
var dx = determineDx(getRandomPizzaContainer[i], size);
var newwidth = (getRandomPizzaContainer[i].offsetWidth + dx) + 'px';

for (var i = 0; i < getRandomPizzaContainer.length; i++) {
  getRandomPizzaContainer[i].style.width = newwidth;
}
```

* Moved variable outside loop decreases load time
```sh
var pizzasDiv = document.getElementById("randomPizzas");
```

## Resources
* [Website Performance Optimization](https://www.udacity.com/course/website-performance-optimization--ud884)
* [Browser Rendering Optimization](https://www.udacity.com/course/browser-rendering-optimization--ud860)
* [Writing READMEs](https://www.udacity.com/course/writing-readmes--ud777)
* [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
* [Jank Free](http://jankfree.org/)