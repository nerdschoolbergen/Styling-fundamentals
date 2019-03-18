# Exercise 3 – Layout using floats

:pencil2: [Open the starting point for this assignment on codepen](https://codepen.io/taranger/pen/JzvqEy)
Solution can be found here [Float layout exercise solution](https://codepen.io/taranger/pen/WmJBRV)

:book: Up until very recently, the main way of creating grid layouts (content separated into rows and columns) was done using floats. Today we have better ways of creating grids, but a lot of websites and applications (unfortunately) still rely on floats. This is usually in order to support legacy browsers, or because rewriting existing codebase is to expensive and/or time consuming. We will therefore spend a little time exploring some of the quirks of using floats for layout.

:exclamation: The following image illustrates the wanted layout for this assignment.

![](1-1.png)

:book: If we compare the image with the starting point on Codepen we see that there are a few things that are off.
1. The height of the parent container is much smaller than its content
2. The child containers are misaligned and overflow the parent container
3. The main content and sidebar do not align on a row

:book: The reasons for this is the following:
1. When we float elements they are taken out of content flow. This essentially means that to the parent container they do not exists and their height is therefore 0. This is probably the biggest drawback of using floats for layout purposes [More on information on content flow for the curious](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flow_Layout/In_Flow_and_Out_of_Flow).
2. This is related to the CSS box model. There are two ways in which width and height of elements can be specified in CSS. Either an element's width and height is only calculated based on its content, or its a combination of content + padding + borders. [Reference on box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model).
3. This point is also related to the CSS box model. At this point the width of the main content (75%) and the sidebar (25%) is 100%. But because of how the box-sizing property is set (per default), this is in fact wider than the width of the element's container.

:pencil2: In order to fix problem 1 we need to create a new [block formating context(BFC)](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) for our container. Try googling "CSS clearfix" in order to find to find a solution and implement it in CodePen.

:pencil2: In order to fix problems 2 and 3 we need to adjust the `box-sizing` property of our elements ([reference](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)). Adjust box-sizing for elements in order to create the layout illustrated in the image above.
