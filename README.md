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


