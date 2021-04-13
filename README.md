# Record variety Algorithms.

* [Honeycomb](https://www.acmicpc.net/problem/2292)

The problem of finding the location of the honeycomb according to the rules of formation of honeycombs

```java
var pos = -1	// note. For current position in layer(Not setted yet).
var max = 0		// note. For maximum value of current layer.
var layer = 0	// note. For get current layer in honeycomb.
var diff = 6	// note. Increasing value rule which when layer increased.

fun main() {
    var end = 70    // note. This is just input value (You could input any number here you want).
    
    if(end > 1) {	            // note. Input value must greater than 1.
        for (i in 1..end) {		// note. Will retrieve by the number value you entered.
            if (layer == 0) {	// note. Set first layer.
                setNewLayer()
                continue
            }

            if (pos >= max) {	// note. Set other layers.
                setNewLayer()
                continue
            }
            pos++				// note. Set current position in current layer.
        }
    }
    println("layer:${layer + 1}")	// note. Finally print result.
}

fun setNewLayer() {
    layer++				// note. Increase layer value.
    max = layer * diff	// note. Set maximum position value of current layer.
    pos = 1				// note. Initialize position value.
}
```