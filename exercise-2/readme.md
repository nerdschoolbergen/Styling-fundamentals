# Exercise 2 - Sizing and the box model
This exercise will focus on the sizing and box model of CSS, which will be important knowledge to have before devling into layouts.

You will learn about:
- Display properties
- Normal flow vs out of flow (float, abolute/fixed positioning)
- Understanding how the box model affects sizing of elements

## Display properties
The display property plays an important role in CSS, it decides how an HTML-element will behave in relation to other elements.
In this exercise we will take a look at inline, inline-block, block, flex and grid.
For full details of display properties check out: [Display properties](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

### inline
`display: inline` will make an element behave as an inline element (like <span>). Any height and width properties will have no effect to it. Text and icons are common uses for display: inline.

### inline-block
`display: inline-block` will make an element display as an inline-level block container. The element itself is formatted as an inline element, but you can apply height and width values. Uses for inline-block can be pretty much anything that you want to not take up all available space and control the size of.

### block
`display: block` The block element will take up all horizontal space in the parent container, it will allways start on a new line from previous elements and stretch to the end of what confines it

### flex
Flexbox is a bit more complicated than the previous displays, putting `display: flex` on a container makes the width and/or height of children elements flex dynamically when the parent container is resized, essentially the elements are stretching and moving either in a row or in a column configuration, imagine a musician playing an accordion. The flex container can have 6 different properties:

### flex-direction
Flex-direction decides which direction the children elements are flexing. `row` makes the elements flex horizontally `row-reverse` reverses the order of the items in horizontal view, `column` makes the elements spread out vertically, and `column-reverse` will do the same just backwards.

Default flex-direction is set to "row", so if you want a collection of items to spread out vertically you type it like this:
```css
 .main-content {
  display: flex;
  flex-direction: column;
 }
```
### flex-wrap
### flex-flow
### justify-content
### align-items
### align-content


### grid

### None

## Flow

## The Box model



