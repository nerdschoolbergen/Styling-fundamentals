# Exercise 2 – Media queries and layouts

:exclamation:
:question:
:pencil2:
:book:

You will learn about
- Different techniques for creating page layouts
- Ensuring that the box model properties are set correctly with regards to the layout we are trying to achieve
- Using media queries to alter layout configurations
- Creating flexible layouts that mitigate some of the need for media queries

:pencil2: [Open the starting point for this assignment on codepen](https://codepen.io/eivindmjelde/pen/PyBZwx?editors=1100)

:book: Up until very recently, the main way of creating grid layouts (content separated into rows and columns) was done using floats. Today we have better ways of creating grids, but a lot of websites and applications (unfortunately) still rely on floats. Either in order to support legacy browsers, or because rewriting existing codebase is to expensive and/or time consuming. We will therefore spend a little time exploring some of the quirks of using floats for layout.

:exclamation: The following image illustrates the wanted layout for this example.

IMG HERE

:book: If we compare the image with the starting point on Codepen we see that there are a few things that are off.
- The child containers are misaligned and overflow the parent container
- The height of the parent container is much smaller than its content
- The main content and sidebar do not align on a row
