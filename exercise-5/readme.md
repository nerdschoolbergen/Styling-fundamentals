# Exercise 5 - Transitions, transform and animations

## Transitions
Transitions occur when an element changes from one state to another. It has a set beginning and an end. Transitions are often used when hovering links or clicking buttons. 

To use transitions we simply use the transition property:

```css
    a {
        color: #FF4136;
    }

    a:hover {
        transition: 2s; 
        color: #001f3f;
    }
```

The above transition begins on hover, and lasts until the element is not hovered anymore. The element will go back to the non-hovered styling. The ```2s``` refers to the amount of time the transition will take to complete. 

You can also specify which properties should be affected by the transition. In the following example, the text will gradually change color, but change font-size immediately.

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

If you don't specify which properties to transition, the default is all. 

You can set a delay on the transitions by using transition delay: 

```
 a:hover {
        transition: color 2s; 
        transition-delay: 0.5s;
        color: #FF4136;
        font-size: 22px;
    }
```

The speed curve of the transition can also be specified:
![Transition curves](images/5-1.png)
[Image source](https://developer.tizen.org/community/tip-tech/working-css3-transitions)

To see an example of how this in action, check out [w3schools](https://www.w3schools.com/css/tryit.asp?filename=trycss3_transition_speed). 

To specify the curve you need to set the ```transition-timing-function``` property. By default it is set to a linear transition. 

## Animations
Animations are more complex than transitions and offers more control. You can animate most HTML elements with CSS animations instead of using JavaScript.

When using animations you can change gradually from one style to another. To use animations you first need to specify keyframes:

```css
@keyframes name-of-animation {
    from {border-color: #FF4136}
    to{border-color: #001f3f}
}
```

You then use the keyframes on the element you want to animate: 

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

Animations have a lot of the same properties as transitions. For example ```animation-duration``` that specifies how long time the animation should use to run. and ``animation-delay``` to set the time from an element is loaded to the animation in run. 

By default the animation will run once when you load the page, but you could also run animation on for example hover: 

```css
.animated-element:hover {
    animation-name: name-of-animation;
    animation-duration: 2s;
}
```

If you want to run an animation several times you could use ```animation-iteration-count``` to specify a set number of times that the animation is run or set it to ```infinite``` to make it loop. 

See more about CSS animations [here](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations).

## :pencil2: Tasks
Remember to ask if you are stuck on these tasks, also [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS) is a good resource.
In this exercise use the example code in this code pen: [Animation example](https://codepen.io/taranger/pen/LaBpGr)
Solution can be found here: [Animation solution](https://codepen.io/taranger/pen/drjYGq)

#### Task 1
Make it so that `#item1` element's background-color is changed to blue when you hover it.

#### Task 2
Make it so that `#item2` element's width is set to 800px when hovered, also change the timing function to ease in and out.

#### Task 3
Make a new keyframe animation for `#item3` called ``spin`` it should start with a rotate transform of 0 degrees and end with 90 degrees. Give it a duration of 2 seconds and iteration count of infinite. Google "transform rotate css" if you are unsure of the syntax.

#### Task 4
Make a new keyframe animation called ``circle``. Give `#item4` a `border-radius` of 0% at the beginning of the animation, and end with a border-radius of 100%. Set iteration count to infinite if you want the animation to continously run.

#### Task 5
See if you can make `#item5` move in a triangle, by first setting `position: relative`, `top: 0px` `left: 0px` and then manipulating the item with keyframes, start the keyframes at 0% with values `top: 0px` `left: 0px`and end it at 100% with the same values so that it returns to the starting point. Remember that if you want the animation to continue forever you need to set `animation-iteration-count` to infinite

### [Go to exercise 6 :arrow_right:](../exercise-6/readme.md)
