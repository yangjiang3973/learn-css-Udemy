# 2020-03-31
## video No.1
1. how to reset webpage by universal selector(remove default size in different browser)
2. set font in body tag(will inherit)
3. clip-path

## video No.2
1. let parent container as relative, so children with absolute pos can be easy to center:

```css
.text-box {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

use top and left as 50% to center the top-left corner at center. Then use transform's translate to center the child's body. Because translate use itself as reference, instead of its parent.

## video No.3 
1. animation: @keyframes and animation property

`animation: moveInRight 1s ease-out;`

```css
@keyframes moveInRight {
    0% {
        opacity: 0;
        transform: translateX(100px);
    }

    80% {
        transform: translateX(-10px);
    }

    100% {
        opacity: 1;
        transform: translateX(0);
    }
}
```

## video No.4
1. pseudo class and pseudo element
2. transition in hover state

# 2020-04-01
## video No.1
responsive design, maintainable and scalable code and web performance.

responsibe web design is a standard in modern web development. including:

1. Fluid layouts
2. Media queries
3. Responsive img
4. Correct units
5. Desktop first VS mobile first

maintainable and scalable code:
1. how to organize files
2. how to name classes
3. how to structure HTML

make web faster and make it smaller in size:
1. less http request(include less files in html doc)
2. less code
3. compress code
4. use a css preprocessor
5. less img
6. compress img

## video No.2
general workflow of webpage rendering

## video No.3
details about how css is parsed

a css rule has 2 parts: selector and declaration block.

one declaration block may have multiple declarations.

each declaration has 2 parts: property and declared value.

the first step in parsing css: resolving conflicts in css declarations

when more than one declarations are applied to an element, how to determine which one wins?

Importance(weight) > Specificity > Source order

1. Importance:

User `!important` declaration > Author `!important` > author declarations > user declarations > default browser declarations

2. Specificity:

Inline styles(css in html) > ID > Classes, pseudo-classes or attribute > Elements or pseudo-elements

3. Order

the last one will win

PS: when you use a 3rd party stylesheets, it is better you place your own ones after them.

## video No.4
an example about last video: specificity

## video No.5
process final values

`em` are measured relative to their parent font-size, if used to specify `font-size`

`em` are measured relative to the current font-size, if used to specify length

# 2020-04-03
## video No.1
Inheritance

It is the computed value of parent that will be passed, not the declared value.

# 2020-04-04
## video No.1
how and why to use rem units in our project?

to avoid a lot of media query but still make webpage more responsive

workflow for converting px to rem:

set root font size to 10px, but not use the hard-coded value. Instead, use 62.5%(16 * 0.625 = 10).

then replace element's px with rem and divide it by 10.

## video No.2
visual formatting model

## video No.3
think before code

BEM(block element modifier)

7-1 pattern to organize code

## video No.4
introduction to sass

Variables

Nesting

Operators

Partials and imports: to write CSS in different files and import them all into one single file

Minxins

Functions

Extends

Control directives(not covered in this course)

## video No.5
sass variables and nesting

Example for variables:

```css
$color-primary: #fff;

nav {
    background-color: $color-primary;
}
```

Example for nesting:

```css
/* old way to select li */
.navigation {
    list-style: none;
}

.navigation li {
    /* something here*/
}

/* sassy way to use nesting */
.navigation {
    list-style: none;

    li {
        /* something here */

        &:first-child {
            /* something here */
        }
    }
}

```

`&`符号在这里是必须的，不然会变成`li :first-child`。放上`&`就连到了一起。

# 2020-04-06
## video No.1
sass mixin, extend and function

1. mixin is a piece of code that you can reuse. like a varible but has many lines of code.

```css
@mixin clearfix {
    &::after{
        content: "";
        clear: both;
        display: table;
    }
}

nav {
    margin: 30px;
    background-color: $color-primary;

    @include clearfix;
}

```

mixin can also accept an augument:

```css
@mixin style-link-text($col) {
    color: $col;
}

@include style-link-text(#fff);
```

2. sass has built-in functions, like darken() or lighten(). But you also can define functions by yourself.

```css
@function divide($a, $b) {
    @return ($a / $b);
}
```

3. extend looks like mixin, but they are actually different.

mixin is to reuse code and copy code to different places. But extends is to replace selector for the placeholder.

extends are usually used for related selectors, not very common. mixin is prefered usually.

## video No.2
An introduction to the command line

## video No.3
install node and sass    

# 2020-04-07
## video No.1
init sass and install live-server

## video No.2
convert current css to sass

## video No.3
implement 7-1 pattern

theme and vendors are missing in this project

## video No.4
review 3 rules for responsive design

1. Fluid grids and layouts:

Use % rather than px for all layout-related length

2. Flexible/responsive img
Need to make sure images can adapt nicely to the current viewport

3. Media query
set break points for different width of viewport

Layout types:

1. Float layouts

2. Flexbox

3. CSS grid

## video No.5
Build a custom grid with floats

## video No.6
## video No.7
## video No.8
all about building the About section

PS: need to learn details of each params of `box-shadow`

## video No.9
build the feature section

1. how to use font icons

## video No.10
build the Tour section:

1. rotate card

2. perspective?

3. how to make a card have front and back 2 sides

## video No.11
continue to building the card:

background-blend-mode

## video No.12
finished building other 2 cards

## video No.13
build the story section

1. make text around shapes: `shape-outside` and `float`

2. apply filter to img

3. use <video> and make background video cover an entire section

4. `object-fit`

## video No.14
continue the above

## video No.15
continue the above: background video

## video No.16
build the booking section:

1. `solid-color gradients`

2. how the general and adjacent sibling selectors work and why we need them

3. how to use the `::input-placeholder` pseudo-element

4. how and when to use `:focus :invalid placeholder-shown and :check` pseudo-classes

5. techniques to build custom radio buttons

```css
/* solid-color gradient is a special way to make a polygon*/
background-image: linear-gradient(
                                    105deg, 
                                    rgba($color-white, .9) 0%,
                                    rgba($color-white, .9) 50%,
                                    transparent 50%
                                    ), 
                      url(../img/nat-10.jpg);
```

# 2020-04-11
## video No.1
continue with the booking section:

```css
/* use pseudo element to change placeholder text style */
::placeholder {
    color: blue;
}
```

# 2020-04-12
## video No.1
continue with the booking section:

# 2020-04-13
## video No.1
build the footer section

# 2020-04-14
## video No.1
build the navigation

1. what is the `checkbox hack`

2. custom animation timing function using cubic bezier curvers

3. how to animate `solid-color` gradients

4. how to use `transform-origin`

## video No.2
continue to building the navigation

Q: background-size and background-position

## video No.3
finished buding the navigation.

how to use css only to make a nav button and change to close button

## video No.4
build popup

1. how to use popup section

2. how to use `:target` pseudo class

3. how to create boxes with equal height using `display: table-cell`

4. how to create text column

5. how to hyphen words

## video No.5
continue to building popup(to make it showup and disappear)

Q: difference between `display: none` and `opacity: 0; visibility: hidden`

## video No.6
### responsive design
desktop first or mobile first

breakpoints:

good way to choose breakpoints is to check popular devices and group the size.

**StatCounter** has the data.

1. phone  600

2. portrait tablet  600 - 900

3. landscape tablet  900 - 1200

4. desktop  1200+

# 2020-04-15
## video No.1
1. use media query in sass mixin

2. @content and @if sass directives

3. Chrome DevTools

```css
@mixin respond-phone {
    @media (max-width: 600px) {
        @content 
    }
}

@include respond-phone {
    font-size: 50%;
}
```

`@content` is similar to passing arguments to a mixin, but it can allow you to pass a block of code 

This is a simple way to use media query, it is better to make a media query manager(like a function)

## video No.2
polish order: Base + typography > general layout + grid > page layout > components

## video No.3
continue to fix

## video No.4
continue to fix component

`www.sizzy.co` is to test webpage on different devices
 
**TODO** homework: make popup box responsive

also most done, but the two img do not have the same height...

**Done** use flex

# 2020-04-16
## video No.1
responsive image

It is not only for responsive web design, but also for web performance.

The goal is to server the right image to the right screen size and device,
in order to avoid downloading unnecessary large images on smaller screens.

## video No.2
art direction and density switching

1. `srcset` attribute on `img`, <source> element and density descriptor

2. `<picture>` element

3. media query in HTML

For `srcset`, you can pass more than one src and let browser to choose the best one.
```html
<div class="footer__logo-box">
    <img srcset="img/logo-green-1x.png 1x, img/logo-green-2x.png 2x" alt="Full logo" class="footer__logo">
</div>
```

In art direction, we choose different img on different width:
```html
<div class="footer__logo-box">
    <picture class="footer__logo">
        <source srcset="img/logo-green-small-1x.png 1x, img/logo-green-small-2x.png 2x"
                media="(max-width: 37.5rem)">
        <img srcset="img/logo-green-1x.png 1x, img/logo-green-2x.png 2x" alt="Full logo">                 
    </picture>
</div>
```
in `<source>`, use media to write media query for small screen, and the <img> below has srcset for other screen.

## video No.3
resolution switching

allow the browser to decide the best img to download, using the `srcset` attribute, width descriptor, and the `size` attribute of `<img>` element.

```html
<img 
srcset="img/nat-1.jpg 300w, img/nat-1-large.jpg 1000w"
sizes="(max-width: 900px) 20vw, (max-width: 600px) 30vw, 300px"
class="composition__photo composition__photo--p1"
src="img/nat-1-large.jpg" 
alt="Photo 1">
```

# 2020-04-17
## video No.1
Responsive img in CSS, mainly for background img

write different media queries for different situation.

```css
@media (min-resolution: 192dpi) and (min-width:37.5em), // comma means OR
       (min-width: 125em)
    {
        background-image: linear-gradient(to right bottom, rgba($color-primary-light,0.8), rgba($color-primary-dark,0.8)) ,url(../img/hero.jpg);
    }

```

## video No.2
Browser support! 

1. @supports

```css
@supports (-webkit-backdrop-filter: blur(10px)) or (backdrop-filter: blur(10px)) {  /* if either property is supported*/
        -webkit-backdrop-filter: blur(10px);
        backdrop-filter: blur(10px);
        background-color: rgba($color-black, .3);   /* set opecity to .3 under this condition to cooperate backdrop-filter*/
    }
```

2. graceful degradation

3. backdrop-filter

## video No.3
Build process

use npm to build final css file

## video No.4
finalize

```css
::selection {
    color: $color-white;
    background-color: $color-primary;
}
```

improve media query:
```css
@media only screen and (max-width: 37.5em) { @content }; /*  if print, this media query will not apply*/
```


in order to make webpage responsive, keep this line in html:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

for larger screen but cannot hover(big touch device):
```css
@media only screen and (hover: none) {

}
```

## video No.5
Section: introduction to flexbox plus other things like svg

## video No.6
philosophy behind flexbox


flexbox is a new module in CSS3 that makes it easy to align elements to on another, in different directions and order.

the main idea behind flexbox is to give the container the ability to expand and to shrink elements to best use all the available space.

flexbox replaces float layouts, using less, and more readable and logical code.

flexbox completely change the way that we build one-dimensional layouts

```css
/* flex container*/
display: flex;
/* display: flex-inline (not often used)*/
```

main axis 

cross axis

container:  
1. flex-direction: row | row-reverse | column | column-reverse

2. flex-wrap: nowrap | wrap | wrap-reverse

3. justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly  (main axis)

4. align-items: stretch | flex-start | flex-end | center | baseline  (cross axis)

5. align-content: stretch | flex-start | flex-end | center | space-between | space-around

item:  
1. align-self: auto | stretch | flex-start | flex-end | center | baseline

2. order: 0 | <integer>

`/* shorthand for these 3 properties: flex: 0 1 auto */`
3. flex-grow: 0 | <integer>

4. flex-shrink: 1 | <integer>

5. flex-basis: auto | <length>


