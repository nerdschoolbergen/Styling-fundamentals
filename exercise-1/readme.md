# Exercise 1 - The cascade, selectors, and specificity
This assignment will focus on tackling one of the most common challenges of CSS: selector specificity. Since CSS by nature has a global scope, understanding specificity is fundemnental in order to contol it.

You will learn about:
- What the cascading part of CSS (Cascading Style Sheets) means
- Inheritance
- The basic groups of selectors and their corresponding specificity values
- Pseudo classes and elements
- Selector combinators
- User agent style sheets?

## 1.1 Subtitle
:book: The "cascade" part of the name cascading style sheet is in itself pretty simple: the order in which CSS rules are declared matter. The rules defined last in a stylesheet take precedence over the ones defined earlier.
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
If all these selectors would target the same element, it's text color would be blue since the declarations in `selector3` take precedence over the others.

:exclamation:However, the type of selector you use can override the order in wich rules are specified.

In order to talk about selector specificity we should first talk about the main groups of selectors:

- Element
- Class
- Pseudo class
- Attribute
- ID
- Style attribute

### Element
An element selctor is the most basic form of selector. Its specified using the name of the corresponding HTML-element type you want to target, like `div`, `p`, `span`, `body` etc.
```css
p {
  // I target all paragraphs. But remember, I can be overwritten by declarations later in the style sheet
}
```
### Class
A class selector is something that is applied to an HTML-element using the `style` attribute: `<div style="fancy-class">I have a class</div>`. We use the "dot"(`.`) notation to target them in CSS.
```css
.fancy-class {
  // I'm a class rule!
}
```
### Pseudo class
Pseudo classes are most often used to trigger specific styles on element states like when you hover over a link or focus on an element using tab on your keyboard. But a pseudo class can also target more abstract element properties like the first or last child within a parent element, or if the element is an "only-child", or even if the element does NOT contain another selector. Pseudo classes can be used by themselves, but are usually used in conjuntion with another selector in order to not be to general. We use "colon"(`:`) notation to specify pseudo classes.
```css
:hover {
  // This is not a good idea since this rule will apply to every element that you hover, including the html document itself
}

a:hover {
  // This will apply to all links that are hovered
}

.class:last-child {
  // This will apply to the last element within a parent element with the class ".class"
}

.class:not(.another-class) {
  // This rule will only apply to an element with the class ".class" if it does NOT also have the class ".another-class"
}
```
[Handy reference of all available pseudo classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
### Attribute
Attribute selectors can be targeted towards all other HTML-element attributes than `class` (explained above) and `id` (explained later). Some common attributes to style would be the `disabled` attribute on a button element(`<button disabled>Disabled button</button>`) or a link based on the content of it's `href` attribute. Since we in HTML5 are allowed to create our own attributes on any element using the `data-` prefix (`<div data-my-magic-attribute="I also have a value!">I have a custom attribute</div>`), we could essentially use attributes like we would use classes(but please don't). We target attributes in CSS using "bracket"(`[]`) notation.
:exclamation: [In attribute selectors we can even use pseudo-regular expressions to target attribute values](https://css-tricks.com/attribute-selectors/)
```css
button[disabled] {
  // Targets all button elements that have a disabled attribute
}

a[href*="https://"] {
  // Targets all external links that use the HTTPS protocol
}

[data-my-magic-attribute$="!"] {
  // Targets all elements that have the custom attribute "data-my-magic-attribute" that has a value that ends with an exclamation point
}
```

