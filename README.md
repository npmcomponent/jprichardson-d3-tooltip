*This repository is a mirror of the [component](http://component.io) module [jprichardson/d3-tooltip](http://github.com/jprichardson/d3-tooltip). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/jprichardson-d3-tooltip`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
JavaScript - d3-tooltip
=======================

This is a JavaScript [d3](http://d3js.org/) tooltip component.


Browserify
----------

    npm install --save d3-tooltip


Component
---------

    component install jprichardson/d3-tooltip



Example
------


```javascript
var d3 = require('d3')
  , d3tooltip = require('d3-tooltip')

var yourDataArray = [.....]

var svg = d3.select('#graph').append('svg')

var tooltip = d3tooltip(d3) //create new tooltip

//the id attribute, automatically incremented on the creation of each tooltip
console.log(tooltip.id) //d3-tooltip-0

svg.selectAll("circle")
    .data(yourDataArray)
    .enter()
    .append("circle")
      .attr("r", 3)
      .attr("cx", function(d, i) {
        //return x position, typically you use a scale here
      })
      .attr("cy", function(d) {
        //return y position, could use a scale here as well
      })
      .on("mouseover", function(d) {
        var html = d.toString()

        tooltip.html(html)
        tooltip.show()    
      })
      .on("mouseout", function(){
        tooltip.hide()
      })
```

Styling
-------

As read from the article below, this gives a nice styling:

```css
.d3-tooltip {            
  text-align: center;           
  width: 60px;                  
  height: 28px;                 
  padding: 2px;             
  font: 12px sans-serif;        
  background: lightsteelblue;   
  border: 0px;      
  border-radius: 8px;                
}
```
You could also add style for different tooltips using the value of the `id` property from your tooltip object.



Credits
-------

This code is almost exclusively based upon this article: http://www.d3noob.org/2013/01/adding-tooltips-to-d3js-graph.html


License
-------

(MIT License)

Copyright 2013, JP Richardson  <jprichardson@gmail.com>


