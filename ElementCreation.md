# Create an element
There are two ways of creating an SVG element.
```javascript
import {createSVG, Circle} from svg.js

const rect = createSVG('rect') // type
```
It creates a single element without attributes
```javascript
Circle({cx: 100, cy: 50, r: 10, fill: 'green'})//attributes
```
It creates a single element with attributes.
### Built in methods
It is built in method for the element you've created with above element create functions.
#### Set Attributes dynamically
```javascript
rect.attr({ width: 100, height: 400, fill: 'blue', x: 250, y: 100, })
```
attr method, only works with a single element.
#### Append multiple elements
```javascript
rect2.append([...elements])
```
#### Set text
```javascript
textElement.text('some text')
```
text method, only works with text-related elements

# Create multiple elements
```javascript
import {createMultiple} from svg.js

const texts = createMultiple('text', 7, [])// type, count, initArray
```
It creates the same type of elements in a list
### Built in methods
#### Set Attributes
```javascript
texts.attrMap ((head,prev, i) =>
({   width: 50,
     height: 70,
     fill: i === 0 ? 'black' : i > 1 && i < 5 ? 'red' : head.fill,
     x: i === 0 ? 0 : prev.x + 150,
     y: i === 0? 250 : prev.y + ((i*10)),
})).map( t => t.text('text-{i}'))
```
In attrMap method, first element' attributes (head),
previous element' attibutes (prev) and the current index of the element are passed as parameter
```javascript
texts[4] .attr({ fill:'green' })
```
attr method is also possible to use for a single element from the list.
