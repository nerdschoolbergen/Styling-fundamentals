# Exercise 4 - Making it responsive with media queries

Media query is a CSS technique introduced in CSS3.
It uses the @media rule to apply CSS properties only if a certain condition is true.
To use a mediaquery simply make a new css rule with the @media tag followed by only screen and a breakpoint. It is common to use the screen width as breakpoints either through min-width or max-width, but you can also trigger it through other properties such as (orientation: landscape) if you are on mobile and flip the device over.

In the example code below, the background color of the body will change to red when the min-width of the window is 600px. This means that resizing the browser window will give the webpage a different look depending on the size of the window.

```css
@media only screen and (min-width: 600px) {
  body {
    background-color: red;
  }
}
```

We can use @media to our advantage when desiging webpages for mobile. We type whatever css rules we want in the media query that we want to override previous rules.
In the example below you can see that we set the body width to 100% when the screen width is at max 600px, this will make the body fill the entire width of the browser window. When the screen width is 601px minimum we set the width to 800px and margin: 0px auto, making it so that it will be a set size of 800px and be centered in the window due to the margin rule.

```css
@media only screen and (max-width: 600px) {
  body {
    width: 100%;
  }
}

@media only screen and (min-width: 601px) {
  body {
    width: 800px;
    margin: 0px auto;
  }
}
```

There are a number of different breakpoint configurations that is possible, it all depends on what your target devices are. But it is common to set mobile size from around 400-800px, tablet from 800-1000px and desktop from around 1000 and up. Some websites have breakpoints at larger sizes than that, in order to support 4k screens for example.

## :pencil2: Media queries Tasks

:exclamation: In this exercise edit the code in this editor: [Mediaqueries exercise](https://codepen.io/taranger/pen/dreBay).  
Solution can be found here [Mediaqueries exercise solution](https://codepen.io/taranger/pen/vPjqbN)

Open the mediaqueries exercise starting point code pen. Move the divider centered on the screen to stretch the webpage. Observe how the elements stretch and shrink. They still keep their position relative to eachother. For example the sidebar will still be placed on the same row as the main-content even if the window shrinks below 600px. So if this were to be viewed on a mobile or tablet, these two containers would be too crammed with content.

#### Task 1

We want to make it so that on mobile, the main-content and sidebar is stacked ontop of eachother instead of side by side. Write a mediaquery that is set to max width of 600px and inside of it set the display property of .content to block instead of flex.

#### Task 2

Lets make the main-content and sidebar fill the whole width on mobile. Change the width of .main-content and .sidebar so that they take up full width in this mediaquery.

#### Task 3

Lets make some rules that apply for a minimum of 900px width and up. Set up another media query that affect this requirement. Now we want the font size of the article element to be 24px and the header element to be 40px.

#### Task 4

Now the page will be more suited to different screen sizes, making text larger when the screensize is larger. Lets assume that the footer is not needed when we are on mobile. Try to hide the footer when the screen is set to the first query you made. See the section on display properties in [Exercise 2](exercise-2/readme.md) if you are usure what propery to use.

#### Task 5

When the screensize is 601px and up, make sidebar and main-content switch places by reversing the flex-direction on the .container element, and also make it so the sidebar is aligned at the bottom of the .container instead of the top.

#### :star: Bonus task

We want to make it so that if you are on a screensize of 400px and below the whole article element is not displayed, and also make a p element with an id "error" that is shown in place of the article that says "Your device is not suited to view this page". Make it so that it is not displayed by default and is only shown when the breakpoint of 400px is reached.

#### :star: Bonus task - Update the grid to use media query

Use the solution from the grid task: [Grid task 2 solution](https://codepen.io/grynag/pen/BaaPyxO) to move the sidebar on mobile devices. If the device is smaller than 600px, the sidebar should be underneath the content instead of on the side.

### [Go to exercise 5 :arrow_right:](../exercise-5/readme.md)
