# Exercise 4 - Making it responsive with media queries

## Making it responsive with media queries
Open the starting point for this assignment on codepen [Mediaqueries exercise](https://codepen.io/taranger/pen/dreBay)
Solution can be found here [Mediaqueries exercise solution](https://codepen.io/taranger/pen/vPjqbN)

Media query is a CSS technique introduced in CSS3.
It uses the @media rule to include a block of CSS properties only if a certain condition is true.
To use a mediaquery simply make a new css rule with the @media tag followed by only screen and a breakpoint. It is common to use a window width as breakpoints either through min-width or max-width, but you can also trigger it through the property (orientation: landscape) for example if you are on mobile and turn the device over.

In this example code the background color of the body will change to red when the min-width og the window is 600px. This means that resizing the browser window will give the webpage a different look depending on how much space is available.

```css
    @media only screen and (min-width: 600px) {
        body {
            background-color: red;
        }
    }
```

We can use this rule to our advantage when desiging webpages for mobile. We type whatever css rules we want in the media query that we want to override previous rules.
In the example below you can see that we set the body width to 100% when the screen is 600px and below, this will make the body fill the entire width of the browserwindow. When the screen width is 601px minimum we set it to 800px and margin: 0px auto, making it so that it will be a set size of 800px and be centered in the window due to the margin rule.


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



## :pencil2: Media queries Tasks

Open the starting point for this assignment on codepen [Mediaqueries exercise](https://codepen.io/taranger/pen/dreBay)
Solution can be found here [Mediaqueries exercise solution](https://codepen.io/taranger/pen/vPjqbN)