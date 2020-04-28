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

5. align-content: stretch | flex-start | flex-end | center | space-between | space-around (for rows)

item:  
1. align-self: auto | stretch | flex-start | flex-end | center | baseline

2. order: 0 | <integer>

`/* shorthand for these 3 properties: flex: 0 1 auto */`
3. flex-grow: 0 | <integer>

4. flex-shrink: 1 | <integer>

5. flex-basis: auto | <length>

# 2020-04-19
## video No.1
practice flexbox container

```css
flex-direction: row;
justify-content: center;
align-items: baseline;
```

## video No.2
practice flexbox item

flex-grow: 0 | <integer>

flex-shrink: 1 | <integer>

flex-basis: auto | <length>

# 2020-04-20
## video No.1
more properties about flexbox item

`align-content` is for rows.

## video No.2
init trillo project

## video No.3
start working on trillo, like file structure and so on.

how and why to use css custom properties

css variables can replace sass variables if you want

```css
/* make css variables global */
:root {
    --color-primary: #eb2f64;
    --color-primary-light: #FF3366;
    --color-primary-dark: #BA265D;
}
/* use var() to call css variables*/
body {
    font-family: 'Open Sans', sans-serif;
    font-weight: 400;
    line-height: 1.6;
    background-image: linear-gradient(to right bottom, var(--color-primary-light), var(--color-primary-dark));
}
```

## video No.4
build the overall layout

1. how to think about the overall layout of an project

2. use flexbox in a real-world project for the first time

## video No.5
build the header

1. why svg VS font icons:

font icons are actually a hack way to make an icon. Not as stable as svg. And screen readers cannot recognize it.

and easy to change color in css

2. how to find, generate and use svg sprites in HTML

sprite file contains all svg icons you need, so only one http request is needed

```html
<button class="search__button">
    <svg class="search__icon">
        <use xlink:href="img/sprite.svg#icon-magnifying-glass"></use>
    </svg>
</button>
```

3. how to change the color of an svg icons in css

4. how to use other flexbox techniques

## video No.6
continue to building the header

# 2020-04-22
## video No.1
finish the header

```scss
/* <span class="user-nav__notification">13</span> */

&__notification {
    font-size: .8rem;
    height: 1.75rem;
    width: 1.75rem;
    border-radius: 50%;  // text will not be at the circle's center
    background-color: var(--color-primary);
    color: #fff;
    position: absolute;
    top: 1.5rem;
    right: 1.1rem;

    display: flex;  // so use css trick to center text
    justify-content: center;
    align-items: center;
}
```

## video No.2
build the navigation

1. how to use scaleY and other transition properties to create hover effect

2. how and why to use `currentColor` css variable

3. more flexbox techniques

## video No.3
continue the navigation

## video No.4
build the hotel-view

1. how to create an infinite animation

2. `margin: auto` with flexbox

for example, use `margin-right:auto` to give space to the item and avoid stretch it to the right.

3. continue with flexbox

## video No.5
continue the hotel-view

## video No.6
build the description section

1. more flexbox: `flex-wrap` to build a multi-column list

```css
.col-1 {
    background-color: turquoise;
    flex: 0 0 60%;
}

.col-2 {
    background-color: violet;
    flex: 1;
}
```
if you want `col-1` to occupy 60%, then set `flex: 0 0 60%` and set `flex: 1` to `col-2` to let it occupy the left space.

2. how and why to use `mask-image` and `mask-size`

## video No.7
continue the above

make a 2-column list:

```html
<ul class="list">
    <li class="list__item">Close to the beach</li>
    <li class="list__item">Breakfast included</li>
    <li class="list__item">Free airport shuttle</li>
    <li class="list__item">Free wifi in all rooms</li>
    <li class="list__item">Air conditioning and heating</li>
    <li class="list__item">Pets allowed</li>
    <li class="list__item">We speak all languages</li>
    <li class="list__item">Perfect for families</li>
</ul>
```

```scss
.list {
    list-style: none;
    margin: 3rem 0;
    padding: 3rem 0;
    border-top: var(--line);
    border-bottom: var(--line);

    display: flex;
    flex-wrap: wrap;

    &__item {
        flex: 0 0 50%;  // each one occupies 50%
        margin-bottom: .7rem;
    }
}
```

# 2020-04-23
## video No.1
build the user review section by flexbox

z-index has no effect for position:static (the default).

## video No.2
build the CTA section

some creative and modern hover effect

## video No.3
media queries

flexbox is powerful for making webpages reponsive

## video No.4
media queries

**change flex direction from row to column to fix on small screen**

## video No.5
wrap up

1. this page can be also built by Grid

2. challenge:

display a user menu when hovering over the username in .user-nav

display a message menu when hovering over the chat icon in .user-nav(maybe like facebook)

display a box with search suggestions as soon as the user starts typing in the search field

create a caption for the .gallery__item with a nice hover effect

# 2020-04-24
## video No.1
CSS Grid!

1. CSS Grid Lyout is a brand new module that brings a 2D grid system to CSS for the first time.

2. CSS Grid replaces float layouts, using less and more readable and logical CSS and HTML.

3. CSS Grid works perfectly together with Flexbox, which is best to handle 1D components and layouts.(Grid + Flexbox)

no need to use bootstrap to layout.

cheatsheet about properties in grid

## video No.2
setup

## video No.3
first practice of grid

```scss
.container {
  background-color: #eee;
  width: 1000px;
  margin: 0 auto;
  
  display: grid;
  grid-template-rows: 150px 150px;  // height of row
  grid-template-columns: 150px 150px 150px;
  
  // grid-row-gap: 30px;
  // grid-column-gap: 50px;
  
  grid-gap: 30px;
}
```

## video No.4

1. repeat function: 

`grid-template-rows: repeat(2, 150px);`

2. `fr` unit

`grid-template-columns: repeat(3, 1fr);`

`fr` means proportional relations of space to occupy between each item

`grid-template-columns: 1fr 2fr 1fr;` so the middle one is as twice large as the others.

`fr` can also be used with other units:

`grid-template-columns: 50% 1fr 1fr;` 

## video No.5
Position grid item

```scss
&--1 {
    background-color: orangered;
    // grid-row-start: 2;
    // grid-row-end: 3;
    // grid-column-start: 2;
    // grid-column-end: 3;
    // the above equals to the shorthands:
    grid-row: 2 / 3;
    grid-column: 2 / 3; 
    // further shorthands:
    // grid-area 2 / 2 3 / 3  // row-start / column-start row-end / column-end 
  }
```

## video No.6
Spanning grid items

`grid-column: 2 / 4;` it will occupy 2 cells in this row.

## video No.7
solve the challenge

# 2020-04-26
## video No.1
A basic solution to this challenge

## video No.2
Naming grid line. It is a different sollution to the challenge.

use a name to replace each line number

```scss
.container {
    grid-template-rows: [header-start] 100px [header-end box-start] 200px [box-end main-start] 400px //... and so on 
}

.sidebar {
    grid-row: header-end / footer-start;
}
```

## video No.3
Naming grid area. This is the third solution.

```scss
.container {
    grid-template-areas: "head head head head"
                        "box box box side"
                        "main main main side"
                        "footer footer footer footer"
}

.header {
    grid-area: head;
}
```

can use `.` to set as default value for empty grid cell

```scss
.container {
    grid-template-areas: "head head head ."
                        "box box box side"
                        "main main main side"
                        "footer footer footer footer"
}
```

for small and simple layout, grid-area is easy to use.

## video No.4
Implicit VS Explicit grid

when you define 4 cells in a grid template, but you have 8 items.

The first 4 are explicit grid and the left is implicit grid.

You can also define the size of implicit grid cells: `grid-auto-rows: 80px`

Implicit grid grows as rows, because for the explicit grid, `grid-auto-flow: row` is the default value. But you can also change it to `column`.

When you do not know how many items in returned data from Ajax call, implicit grid is very useful here.

## video No.5
Align grid items

`align-items: stretch;` is the default value

we also have new property: `justify-items`.

very similar to flexbox, also has `align-self` and `justify-self`

## video No.6
Align tracks 

`justify-content: space-between | start | end ...` like flexbox

`align-content `

if you do not want holes: `grid-auto-flow: row dense`

## video No.7
min-content, max-content and minmax() function

`max-content` makes items as wide as possible by avoiding line breaks in content

`grid-template-rows: repeat(2, minmax(150px, min-content));`

`minmax` function define a upper bound and lower bound for grid items.

## video No.8
`auto-fit` and `auto-fill` and responsive layout

`grid-template-column: repeat(auto-fill, 100px)` will calculate number of columns based on container's width.

But `auto-fit` will still the same number of tracks, but auto collapse empty cells. For examle, you have 8 items but 10 tracks, the left will have 0 width.

these properties can make webpage more responsive.

## video No.9 
setup new project

# 2020-04-27
## video No.1
build the overall layout

1. how to build a complex and modern layout using advanced CSS Grid techniques.

2. how to choose different row and column track sizes for different types of content.

## video No.2
continue the layout, column tracks now

## video No.3
build the feature section

1. how and why to create grids inside of grids;

2. how to create a respinsive component without media queries

3. how to build a small component using CSS Grid

## video No.4
continue the feature section

-1 means the last **explicit** grit!

NOTE: why set `align-item` on features grid level, not single feature level???
because the children element of feature is the content of feature.

`grid-template-columns: repeat(auto-fit, minmax(25rem, 1fr));` to control the row numbers based on window width.

## video No.5
build the story section

1. how to deal with overlapping grid items

2. why images are special and behave differently than other grid items

3. how to decide flexbox is a better tool in certain situations

## video No.6
continew the story section

## video No.7
build the homes section

build a complex component using a mix of Grid properties, overlapping and flexbox

## video No.8
contine the homes section

usually just define the columns, and let the browser to decide rows implicitly.

## video No.9
1. how to create complex grid-looking gallery

2. using `object-fit` together with images for grid items

add a wrapper for img and use `object-fit`

# 2020-04-27
## video No.1
position each img in grid areas

emmit syntax: [] for attribute, () to structure it better

## video No.2
nothing new, just practice

`grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr));`


