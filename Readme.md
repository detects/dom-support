
# dom-support

  Test for browser rendering/styling quirks. Extracted from jQuery.

## Installation

    $ component install timoxley/dom-support

## Usage

```js
var support = require('dom-support');
console.log(support.opacity) // true in Chrome, false in IE
```

## API

All properties of the `dom-support` object are `Boolean`.

### leadingWhitespace
IE strips leading whitespace when .innerHTML is used

### tbody
Make sure that tbody elements aren't automatically inserted.  IE will insert them into empty tables

### htmlSerialize
Make sure that link elements get serialized correctly by innerHTML. This requires a wrapper element in IE

### style
Get the style information from getAttribute (IE uses .cssText instead)

### hrefNormalized
Make sure that URLs aren't manipulated. (IE normalizes it by default)

### opacity
Make sure that element opacity exists (IE uses filter instead) Use a regex to work around a WebKit issue.

### cssFloat
Verify style float existence (IE uses styleFloat instead of cssFloat

### checkOn
Make sure that if no value is specified for a checkbox that it defaults to "on". (WebKit defaults to "" instead)

### optSelected
Make sure that a selected-by-default option has a working selected property. (WebKit defaults to false instead of true, IE too, if it's in an optgroup)

### getSetAttribute
Test setAttribute on camelCase class. If it works, we need attrFixes when doing get/setAttribute (ie6/7)

### enctype
Tests for enctype support on a form

### html5Clone
Makes sure cloning an html5 element does not cause problems

### submitBubbles, changeBubbles, focusinBubbles
Detect support for bubbling the corresponding event in non-standard event systems (namely IE). 

### deleteExpando
Test to see if it's possible to delete an expando from an element (Fails
in IE)

### noCloneEvent
Cloning a node shouldn't copy over any bound event handlers (IE does this)

### noCloneChecked
Make sure checked status is properly cloned

### optDisabled
Make sure that the options inside disabled selects aren't marked as disabled (WebKit marks them as disabled)

### radioValue
Check if a radio maintains its value after being appended to the DOM

### checkClone
WebKit doesn't clone checked state correctly in fragments

### appendChecked
Check if a disconnected checkbox will retain its checked value of true after appended to the DOM (IE6/7)

### reliableHiddenOffsets
Check if table cells still have offsetWidth/Height when they are set
to display:none and there are still other visible table cells in a
table row; if so, offsetWidth/Height are not reliable for use when
determining if an element has been hidden directly using
display:none (it is still safe to use offsets if a parent element is
hidden; don safety goggles and see bug [#4512](http://bugs.jquery.com/ticket/4512) for more information).
(only IE 8 fails this test)

### boxSizing, boxSizingReliable, doesNotIncludeMarginInBodyOffset, pixelPosition
Checks box-sizing & margin behavior

### reliableMarginRight
Check if div with explicit width and no margin-right incorrectly
gets computed margin-right based on width of container. For more
info see bug [#3333](http://bugs.jquery.com/ticket/3333)
Fails in WebKit before Feb 2011 nightlies
WebKit Bug 13343 - getComputedStyle returns wrong value for margin-right

### inlineBlockNeedsLayout
Check if natively block-level elements act like inline-block
elements when setting their display to 'inline' and giving
them layout. (IE < 8 does this)

### shrinkWrapBlocks
Check if elements with layout shrink-wrap their children (IE 6 does this)

## License

  MIT
