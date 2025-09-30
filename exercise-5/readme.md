# Exercise 5 - Transitions, transform and animations

## 5.1 - Transitions

:book: Transitions occur when an element changes from one state to another. It has a set beginning and an end. Transitions are often used when hovering links or clicking buttons.

:book: To use transitions we simply use the transition property:

```css
    a {
        color: #FF4136;
    }

    a:hover {
        transition: 2s; 
        color: #001f3f;
    }
```

:book: The above transition begins on hover, and lasts until the element is not hovered anymore. The element will go back to the non-hovered styling. The ```2s``` refers to the amount of time the transition will take to complete.

:book: You can also specify which properties should be affected by the transition. In the following example, the text will gradually change color, but change font-size immediately.

```css
    a {
        color: #FF4136;
        font-size: 12px;
    }

    a:hover {
        transition: color 2s; 
        color: #001f3f;
        font-size: 22px;
    }
```

:book: If you don't specify which properties to transition, the default is all.

:book: You can set a delay on the transitions by using transition delay:

```css
 a:hover {
        transition: color 2s; 
        transition-delay: 0.5s;
        color: #FF4136;
        font-size: 22px;
    }
```

:book: The speed curve of the transition can also be specified:
![Transition curves](5-1.png)
[Image source](https://developer.tizen.org/community/tip-tech/working-css3-transitions)

:book: To see an example of how this in action, check out [w3schools](https://www.w3schools.com/css/tryit.asp?filename=trycss3_transition_speed).

:book: To specify the curve you need to set the ```transition-timing-function``` property. By default it is set to a linear transition.

## 5.2 - Animations

:book: Animations are more complex than transitions and offers more control. You can animate most HTML elements with CSS animations instead of using JavaScript.

:book: When using animations you can change gradually change from one style to another. To use animations you first need to specify keyframes:

```css
@keyframes name-of-animation {
    from {border-color: #FF4136}
    to{border-color: #001f3f}
}
```

:book: You then use the keyframes on the element you want to animate:

```css
.animated-element {
    animation-name: name-of-animation;
    animation-duration: 2s;
}
```

You can also make keyframes based on percentages:

```css
@keyframes movment-animation {
    0%   {left: 0px}
    25%  {top: -20px;}
    50%  {left: 40px;}
    100% {left: 0px; top: 0px;}
}
```

:book: Animations have a lot of the same properties as transitions. For example `animation-duration` that specifies how long time the animation should use to run. and `animation-delay` to set the time from an element is loaded to the animation in run.

:book: By default the animation will run once when you load the page, but you could also run animation on for example hover:

```css
.animated-element:hover {
    animation-name: name-of-animation;
    animation-duration: 2s;
}
```

:book: If you want to run an animation several times you could use `animation-iteration-count` to specify a set number of times that the animation is run or set it to `infinite` to make it loop.

:book: See more about CSS animations [here](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations).

## 5.3 - :pencil2: Tasks

:exclamation: In this exercise edit the code in this editor:: [Animation example](https://codepen.io/taranger/pen/LaBpGr)

:book: Solution can be found here: [Animation solution](https://codepen.io/taranger/pen/drjYGq) 
Remember to ask if you are stuck on these tasks, also [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS) is a good resource.

### 5.3.1 - Task 1

:pencil2: Make it so that `#item1` element's background-color is changed to blue when you hover it. Make sure it has a transition of 2 seconds.

### 5.3.2 -  Task 2

:pencil2: Make it so that `#item2` element's width is set to 800px when hovered, also change the timing function to ease in and out with a  transition of 2 seconds. :exclamation: Observe the difference in movement between the "ease in and out" and no timing function.

### 5.3.3 - Task 3

:pencil2: Make a new keyframe animation for `#item3` called ``spin`` it should start with a rotate transform of 0 degrees and end with 90 degrees. Give it a duration of 2 seconds and iteration count of infinite. Google "transform rotate css" if you are unsure of the syntax.

### 5.3.4 - Task 4

:pencil2: Make a new keyframe animation called ``circle``. Give `#item4` a `border-radius` of 0% at the beginning of the animation, and end with a border-radius of 100%. Set iteration count to infinite if you want the animation to continously run.

### 5.3.5 - Task 5

:pencil2: See if you can make `#item5` move in a triangle, by first setting `position: relative`, `top: 0px` `left: 0px` and then manipulating the item with keyframes, start the keyframes at 0% with values `top: 0px` `left: 0px`and end it at 100% with the same values so that it returns to the starting point. Remember that if you want the animation to continue forever you need to set `animation-iteration-count` to infinite
