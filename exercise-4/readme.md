# Exercise 4 - Making it responsive with media queries

Media query is a CSS technique introduced in CSS3.
It uses the @media rule to include a block of CSS properties only if a certain condition is true.
To use a mediaquery simply make a new css rule with the @media tag followed by only screen and a breakpoint. It is common to use the screen width as breakpoints either through min-width or max-width, but you can also trigger it through the property (orientation: landscape) for example if you are on mobile and turn the device over.

In this example code the background color of the body will change to red when the min-width of the window is 600px. This means that resizing the browser window will give the webpage a different look depending on how much space is available.

```css
    @media only screen and (min-width: 600px) {
        body {
            background-color: red;
        }
    }
```

We can use @media to our advantage when desiging webpages for mobile. We type whatever css rules we want in the media query that we want to override previous rules.
In the example below you can see that we set the body width to 100% when the screen width is at max 600px or less, this will make the body fill the entire width of the browser window. When the screen width is 601px minimum we set it to 800px and margin: 0px auto, making it so that it will be a set size of 800px and be centered in the window due to the margin rule.


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

There are a number of different breakpoint configurations that is possible, it all depends on what your target devices are. But it common to set mobile sie around 400-800px, tablet from 800-1000px and desktop from around 1000 and up. Some websites have breakpoints at larger sizes than that, in order to support 4k screens for example.

## :pencil2: Media queries Tasks
Open the starting point for this assignment on codepen [Mediaqueries exercise](https://codepen.io/taranger/pen/dreBay).
Solution can be found here [Mediaqueries exercise solution](https://codepen.io/taranger/pen/vPjqbN)

Open the mediaqueries exercise starting point code pen. Move the divider centered on the screen to stretch the boxes on the right. Observe how the boxes stretch and shrink. They still keep their position relative to eachother. For example the sidebar will still be placed on the same row as the main-content even if the window shrinks below 600px. So if this were to be viewet on a mobile or tablet, these two container would be crammed too much together.
#### Task 1
We want to make it so that on mobile, the containers take up the full width of the window. Write a mediaquery that is set to max width of 600px and sets the display property of .content to block instead of flex. 

#### Task 2
Change the width of .main-content and .sidebar to 100% inside the mediaquery.

#### Task 3
Now the .main-content and .sidebar will fill 100% of the .container's width when the user is on a mobile phone or the screen is resized to 600px and below.

#### Task 4
Lets make some rules that apply for 900px and up. Set up another media query that affect this requirement. Now we want the font size of the article element to be 24px and the header element to be 40px.

#### Task 5 
Now the page will be more suited to different screen sizes, making text larger when the screensize is larger. Lets assume that the footer is not needed when we are on mobile. Try to hide the footer when the screen is set to the first query you made; max width of 600px. See the section on display properties in [Exercise 2](exercise-2/readme.md) if you are usure what propery to use.

#### Task 6
Try to make sidebar and main-content switch places by changeing the flex-direction on the .container element, and also make it so the sidebar is aligned at the bottom of the .container instead of the top. 

#### Bonus task - some html
We want to make it so that if you are on a screensize of 400px and below the whole article element is not displayed, and also make a p element with an id "error" that is shown in place of the article that says "Your device is not suited to view this page". Make it so that it is not displayed by default and is only shown when the breakpoint of 400px is reached.
