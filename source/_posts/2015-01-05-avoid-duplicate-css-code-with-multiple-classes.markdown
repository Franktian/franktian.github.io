---
layout: post
title: "Avoid duplicate CSS code with multiple classes"
date: 2015-01-05 20:39:40 -0500
comments: true
categories: 
---
Today I've been trying to re-write a multi-level vertical navigation menu like [this one](http://bootsnipp.com/snippets/featured/multi-level-dropdown-menu-bs3).

My goal is to make a set of vertical bars whose children divs lie on the same level horizontally. The way I did it first was to specify height for each divs explicitly:

```html
<li class="dropdown-submenu">
    <a href="#" class="dropdown-toggle" data-toggle="dropdown">More options 1</a>
    <div class="dropdown-menu sub-0">Hello</div>
</li>
<li class="dropdown-submenu">
    <a href="#" class="dropdown-toggle" data-toggle="dropdown">More options 2</a>
    <div class="dropdown-menu sub-1">I'm</div>
</li>
<li class="dropdown-submenu">
    <a href="#" class="dropdown-toggle" data-toggle="dropdown">More options 3</a>
    <div class="dropdown-menu sub-2">Your</div>
</li>
<li class="dropdown-submenu">
    <a href="#" class="dropdown-toggle" data-toggle="dropdown">More options 4</a>
    <div class="dropdown-menu sub-3">Dropdown Menu</div>
</li>
```

```css
.dropdown-submenu > .sub-0 {
    top: 0;
    left: 100%;
    margin-top: -6px;
    margin-left: -1px;
    -webkit-border-radius: 0 6px 6px 6px;
    -moz-border-radius: 0 6px 6px;
    border-radius: 0 6px 6px 6px;
    height: 200px;
    width: 400px;
}

.dropdown-submenu > .sub-1 {
    top: -26px;
    left: 100%;
    margin-top: -6px;
    margin-left: -1px;
    -webkit-border-radius: 0 6px 6px 6px;
    -moz-border-radius: 0 6px 6px;
    border-radius: 0 6px 6px 6px;
    height: 200px;
    width: 400px;
}

.dropdown-submenu > .sub-2 {
    top: -52px;
    left: 100%;
    margin-top: -6px;
    margin-left: -1px;
    -webkit-border-radius: 0 6px 6px 6px;
    -moz-border-radius: 0 6px 6px;
    border-radius: 0 6px 6px 6px;
    height: 200px;
    width: 400px;
}

.dropdown-submenu > .sub-3 {
    top: -78px;
    left: 100%;
    margin-top: -6px;
    margin-left: -1px;
    -webkit-border-radius: 0 6px 6px 6px;
    -moz-border-radius: 0 6px 6px;
    border-radius: 0 6px 6px 6px;
    height: 200px;
    width: 400px;
}
```

As you can easily find out that's a lot of duplicate code. And over the experience of following MOOC courses with Coursera and Code School, I've learnt two sentences -- Can you better? and Don't repeat your self. So after two minutes of thinking, I came up with a better solution:

```css
.dropdown-submenu > .dropdown-menu {
    left: 100%;
    margin-top: -6px;
    margin-left: -1px;
    -webkit-border-radius: 0 6px 6px 6px;
    -moz-border-radius: 0 6px 6px;
    border-radius: 0 6px 6px 6px;
    height: 200px;
    width: 400px;
}

.dropdown-submenu > .sub-0 {
    top: 0;
}

.dropdown-submenu > .sub-1 {
    top: -26px;
}

.dropdown-submenu > .sub-2 {
    top: -52px;
}

.dropdown-submenu > .sub-3 {
    top: -78px;
}
```

Class `dropdown-menu` takes care of the gereral rules apply to all divs, the other one just handles the specific height that make each of them lies on the same level.

Organizing my CSS code has always been a nightmare to a noob like me. And this exmaple gives me a good starting place to rethink  about how to structure CSS more elegantly, and the goodies of using mulitiple, meaning-oriented class names.

I shall admit that this is an ridiculously easy example. However during my no-even-long career as a developer, I have seen many examples where developers with years of experience don't pay too much attention about code duplication, which sometimes, will fall into such situation.


