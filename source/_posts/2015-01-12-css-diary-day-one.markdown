---
layout: post
title: "CSS Diary Day One - Overview of basic CSS layout"
date: 2015-01-12 19:14:35 -0500
comments: true
categories: 
---
## `position` Property 
As the name of this property, `position` specify the behavior of how to locate the element on the document. There are six different values you can assign to position:
```
position: static|absolute|fixed|relative|initial|inherit;
```

### Static
`static` is the default value of position. Any element has a position value of `static` is considered as *unpositioned*. In this situation property like `top`or `float` will be automatically ignored.

Any element has a position value other than `static` will be considered as *positioned*

### Absolute
An absolutely positioned element is placed relative to it's closest positioned ancestor, which is the closest parent element whose position value is not `staic`. If there is no such an element found. Then it will be relative to `<body>`.

### Relative
The element is positioned relative to its *normal* position. For example, a relatively positioned element with `left: 20px;` will be added 20 pixels to its left.

If you do not specify any of `top`, `bottom`, `left`, `right` or `float` property, `relative` behaves like `static` but the element is still considered as `positioned`.

It is a common trick to use relatively positioned container element with absolutely positioned child elements to layout a page.

## `display` Property - `block` and `inline`
The difference between these two is `block` will take as much horizontal space as possible and have a new line before and after it, while `inline` will only take the space it need and not have new lines.

## Other tips

Remove underline of a hyperlink:
```css
a:link, a:visited {
    text-decoration: none;
}
```

```css
/* Applys to all descent li's */
li li {
    ...
}

/* Applys to only successor li's */
li > li {
    ...
}
```

## Further Reading

[display|CSS-Tricks](http://css-tricks.com/almanac/properties/d/display/)