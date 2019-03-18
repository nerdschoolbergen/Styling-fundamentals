# Exercise 5 - Transitions, transform and animations

## Transitions
Transitions occurs when an element changes from one state to another. It has a set beginning and an end. Transitions are often used when hovering links or clicking buttons. 

To use transitions we simply use the transition property:

```css
    a{
        color: #FF4136;
    }

    a:hover{
        transition: 2s; 
        color: #001f3f;
    }
```

The above transition begins on hover, and lasts until the element is not hovered anymore. The element will go back to the non-hovered styling. The ```2s``` refers to the amount of time the transition will take to complete. 

You can also specify which properties should be affected by the transition. In the following example, the text will gradually change color, but change font-size immediately.

```css
    a{
        color: #FF4136;
        font-size: 12px;
    }

    a:hover{
        transition: color 2s; 
        color: #001f3f;
        font-size: 22px;
    }
```

If you don't specify which properties to transition, the default is all. 

You can set a delay on the transitions by using transition delay: 

```
 a:hover{
        transition: color 2s; 
        transition-delay: 0.5s;
        color: #FF4136;
        font-size: 22px;
    }
```

The speed curve of the transition can also be specified:
![Transition curves](5-1.png)
[Image source](https://developer.tizen.org/community/tip-tech/working-css3-transitions)

To see an example of how this in action, check out [w3schools](https://www.w3schools.com/css/tryit.asp?filename=trycss3_transition_speed). 

To specify the curve you need to set the ```transition-timing-function``` property. By default it is set to a linear transitions. 

## Animations
Animations are more complex than transitions and offers more control. You can animate most HTML elements with CSS animations instead of using JavaScript.

When using animations you can change gradually change from one style to another. To use animations you first need to specify keyframes:

```css
@keyframes name-of-animation{
    from {border-color: #FF4136}
    to{border-color: #001f3f}
}
```

You then use the keyframes on the element you want to animate: 

```css
.animated-element{
    animation-name: name-of-animation;
    animation-duration: 2s;
}
```

Animations have a lot of the same properties as transitions. For example ```animation-duration``` that specifies how long time the animation should use to run. and ``animation-delay``` to set the time from an element is loaded to the animation in run. 

By default the animation will run once when you load the page, but you could also run animation on for example hover: 

```css
.animated-element:hover{
    animation-name: name-of-animation;
    animation-duration: 2s;
}
```

If you want to run an animation several times you could use ```animation-iteration-count``` to specify a set number of times that the animation is run or set it to ```infinite``` to make it loop. 

See more about CSS animations [here](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations).

