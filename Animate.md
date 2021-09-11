# Animate an element
```javascript
import {Rect} from 'svg.js'

const rect = Rect({ width: 100, height: 100, fill: 'red', x: 400, y: 30, })
```
```javascript
const dropDownRect = animateSVG(rect)  // element
                      .target('y')     // attributeName (to animate)
```
You can hold the target (attributeName) and animate dynamically.

```javascript
dropDownRect.animate(({y}) => ({dur:"5s",from:10,to:y+100,repeatCount: "indefinite"}))
```
In animate method the element's attributes are passed as parameter. <br />
animateSVG function returns it's element so that It can be listed to built in append method.

#### Dynamically change animate attributes
```javascript
dropDownRect.animate(({y}) => ({from: 100,to: y+200}))
```
