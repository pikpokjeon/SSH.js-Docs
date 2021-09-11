# Svg tree
All possible ways of including SVG elements to append built in method.
```javascript
import {Svg, G, createSVG, createMultiple} from 'svg.js'
import {id} from 'html.js'


const circles = createMultiple('circle', 5, [])
                  .attrMap((head,prev, i) => ({cx: (i+1) * 120, cy: 100, r: (i+1) * 10, fill:'red'}))

const rect = createSVG('rect')
                .attr({ width: 100, height: 100, fill: 'red', x: 400, y: 30 })

```
```javascript
const exampleTree =
     Svg({id: 'svg-example', width: 700, height: 800})
          .append([
             G({id: 'svg-group'}).append([
                 ...circles,
                  circles[2].attr({fill:'blue'})  // circle[2] from the list circles will be rendered updated
                  animateSVG(rect).target('y').animate(...)
           ])
```

You can append a list of elements by spreads and animated SVG which returns the element. <br /> 
```javascript
id('svg-area').appendchild(exampleTree)
```
Here I used id function which selects document's element by id then appends the created svg tree to it.
