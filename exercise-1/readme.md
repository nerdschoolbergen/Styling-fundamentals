# Exercise 1 - The cascade, selectors, and specificity
This exercise will focus on tackling one of the most common challenges of CSS: selector specificity and the cascade. Since CSS by nature has a global scope, understanding specificity is fundamental in order to contol it.

### The Cascade
The "cascade" part of the name cascading style sheet is in itself pretty simple: the order in which CSS rules are declared matter. The rules defined last in a stylesheet take precedence over the ones defined earlier.
```css
selector1 {
  color: red;
}

selector2 {
  color: green;
}

selector3 {
  color: blue;
}
```
If all these selectors would target the same element, it's text color would be blue since the declarations in `selector3` take precedence over the others due to it being applied last.

:exclamation: However, the type of selector you use can override the order in which rules are specified.

In order to talk about selector specificity we should first talk about the main groups of selectors:

- Element
- Class
- Pseudo class
- Attribute
- ID
- Style attribute

### Element
An element selctor is the most basic form of selector. Use the name of the corresponding HTML-element type you want to target, like `<div>`, `<p>`, `<span>`, `<body>` etc.
```css
p {
  /* I target all paragraphs. But remember, I can be overwritten by declarations later in the style sheet */
}
```
### Class
A class selector is something that is applied to an HTML-element using the `class` attribute: `<div class="fancy-class">I have a class</div>`. We use the "dot"(`.`) notation to target them in CSS. Multiple elements can have the same class slector, this is useful so that we do not need to write the same rules for different elements.
```css
.fancy-class {
  // I'm a class rule!
}
```
### Pseudo class
Pseudo classes are most often used to trigger specific styles on element states like when you hover over a link or focus on an element using tab on your keyboard. But a pseudo class can also target more abstract element properties like the first or last child within a parent element, or if the element is an "only-child", or even if the element does NOT contain another selector. Pseudo classes can be used by themselves, but are usually used in conjunction with another selector in order to not be too general. We use "colon"(`:`) notation to specify pseudo classes.
```css
:hover {
  /* This is not a good, idea since this rule will apply to every element that you hover, 
     including the html document itself */
}

a:hover {
  /* This will apply to all links that are hovered */
}

.class:last-child {
  /* This will apply to the last element within a parent element with the class ".class" */
}

.class:nth-child(odd) {
  /* This will apply to all odd child elements of a parent, useful for example to make zebra stripes on list items */
}

.class:not(.another-class) {
  /* This rule will only apply to an element with the class ".class" if it does NOT also 
     have the class ".another-class" */
}
```
[Handy reference of all available pseudo classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
### Attribute
Attribute selectors can be targeted towards all other HTML-element attributes than `class` (explained above) and `id` (explained later). Some common attributes to style would be the `disabled` attribute on a button element
```html
<button disabled>Disabled button</button>
```
or a link based on the content of it's `href` attribute. Since we in HTML5 are allowed to create our own attributes on any element using the `data-` prefix
```html
<div data-my-magic-attribute="I also have a value!">I have a custom attribute</div>
```
, we could essentially use attributes like we would use classes(but please don't). We target attributes in CSS using "bracket"(`[]`) notation.
:exclamation: [In attribute selectors we can even use pseudo-regular expressions to target attribute values](https://css-tricks.com/attribute-selectors/)
```css
button[disabled] {
  /* Targets all button elements that have a disabled attribute */
}

a[href*="https://"] {
  /* Targets all external links that use the HTTPS protocol
     (* sybolises that "string starts with") */
}

[data-my-magic-attribute$="!"] {
  /* Targets all elements that have the custom attribute "data-my-magic-attribute"
     that has a value that ends with an exclamation point
     ($ sybolises that "string ends with") */
}
```
### Id
The id selector are meant to target all HTML-elements that are unique. For the id tag to be considered valid by the browser the id must be unique to the specific element. An example of an element with a id tag: `<div id="unique-item">This item is unique</div>`

Elements that tends to have ids are main sections of webpages such as the header, main content or the footer. Other specific elements such as input fields may have unique id's so that javascript functions can target them.

```css
button#submit {
  /* Targets a button element that have a id="submit" -> <button id="submit">Submit</button> */
}

#menu li {
  /* Targets all li elements that are children to an element with the id="menu" */
}
```
The Id tag is more specific than targeting a class or and element, and will overwrite previous styles applied to those elements.
In the example below the second css rule that points towars p elements with the id "red-text" will overrule the previous one and turn that specific element red, while all other p elements will be blue.

```css
p {
  color: blue;
}

p#red-text {
  color: red;
}
```

### Style attribute
When styling HTML-elements you do not necessarily need to have a stylesheet, you can write (inline) styles inside a "style" attribute directly on the element itself, such as this: `<p style="color: red">This text is red</p>` This type of styling is regarded as bad practice, because the markup and content of the site should be separated from the styling.

```html
  <div id="main-content">
    <h1 style="font-size: 64px; text-decoration: underline">Underlined title element with font size of 64px</h1>
    <p style="color: red; font-weight: bold">A paragraph that is colored red and have font weight bold.</p>
  </div>
```

The example above contains a div with two elements, separating the styles form the html would make the markup more readable:

```html
  <div id="main-content">
    <h1>Underlined title element with font size of 64px</h1>
    <p>A paragraph that is colored red and have font weight bold.</p>
  </div>
```

```css
  h1 {
    font-size: 64px;
    text-decoration: underline;
  }
  
  p {
    color: red; 
    font-weight: bold;
  }
```
## :pencil2: Tasks
Remember to ask if you are stuck on these tasks, also [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS) is a good resource.
In this exercise use the example code in this code pen: [Codepen example](https://codepen.io/taranger/pen/NJaOzM)

#### Task 1
Change the color of the h1 element to red. (The h1 element can be found on line 29 with `display: inline-block` property already present)

```css
  h1 {
    display: inline-block;
    /* insert color properties here */
  }
```

#### Task 2
Make another identical selector for h1 and set the color to blue. See that it overrides the existing css rule above it. You should have two h1 selector at this point.
:exclamation: this is not best practise but only for illustrating how the cascade works.

#### Task 3
Notice that all images in the HTML have a class "image", create a new css rule for "image" at the bottom of the css window. Make the width and height 100px;

```css 
  .image {
    /* Create a rule like this and type your properties */
  }
```

#### Task 4
Make it so when you hover the checkboxes `<input>`, the cursor changes to a pointer, if you are unsure read the section on pseudo classes above.
You can either target them by targeting all "input" elements or more specifically targeting elements with the attribute `type="checkbox"`. 

#### Task 5
Target the `#content` id selector of the page and give it a background color using the value "#c3e4d6", and a padding of of 20px;

#### Task 6
Add a inline style attribute to the h1 header and add a property that puts the font-size at 50px;
