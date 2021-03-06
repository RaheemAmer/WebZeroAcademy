# WebZeroAcademy-notes

The three types of URLs:
Absolute, Relative, and Root-Relative Links

Absolute = Page to external page
<!-- <a href='https://developer.mozilla.org/en-US/docs/Web/HTML'>Mozilla -->

Relative = page to other internal page (another folder but all inside the current page)
<!-- <li>Relative links, like to our <a href='misc/extras.html'>extras
page</a>.</li> -->

Root-Relative = connect page to other page using website domain
<!-- if your website is hosted on our-site.com, all root-relative URLs will be relative to our-site.com. -->

Image Formats:

- JPG = JPG images are designed for handling large color palettes without exorbitantly increasing file size.
- GIF = GIFs are the go-to option for simple animations, but the trade off is that they’re somewhat limited in terms of  color palette—never use them for photos.
- PNG = PNGs are great for anything that’s not a photo or animated.
- SVG = Unlike the pixel-based image formats above, SVG is a vector-based graphics format, meaning it can scale up or down to any dimension without loss of quality.

the image element uses the inherit dimensions of its image file

Body { selector
    color : red; property - value
}

The CSS hierarchy for every web page looks like this:

- The browser’s default stylesheet
- User-defined stylesheets
- External stylesheets (that’s us)
- Page-specific styles (that’s also us)
- Inline styles (that could be us, but it never should be)

Notes:

- Block boxes always appear below the previous block element. This is the “natural” or “static” flow of an HTML document when it gets rendered by a web browser.

- The width of block boxes is set automatically based on the width of its parent container. In this case, our blocks are always the width of the browser window.

- The default height of block boxes is based on the content it contains. When you narrow the browser window, the h1 gets split over two lines, and its height adjusts accordingly.

- Inline boxes don’t affect vertical spacing. They’re not for determining layout—they’re for styling stuff inside of a block.

- The width of inline boxes is based on the content it contains, not the width of the parent element.

Vertical Margin Collapse:

- Another quirk of the CSS box model is the “vertical margin collapse”. When you have two boxes with vertical margins sitting right next to each other, they will collapse. Instead of adding the margins together like you might expect, only the biggest one is displayed.
- Remember that padding doesn’t ever collapse

Solution to vertical margin-collapse:

- add div between two elements with margin
- A third option to avoid margin collapse is to stick to a bottom-only or top-only margin convention.
- Finally, the flexbox layout scheme doesn’t have collapsing margins, so this isn’t really even an issue for modern websites.

Explicit Dimensions:

- But, sometimes our desired layout calls for an explicit dimension, like a sidebar that’s exactly 250 pixels wide. For this, CSS provides the width and height properties. These take precedence over the default size of a box’s content.
- Instead of being as wide as the browser window, our button is now 200 pixels, and it hugs the left side of the page:
- Also notice that if you make the button’s title longer, it will automatically wrap to the next line, and the element will expand vertically to accommodate the new content. You can change this default behavior with the white-space and overflow properties.

Content Boxes and Border Boxes:

- The width and height properties only define the size of a box’s content. Its padding and border are both added on top of whatever explicit dimensions you set. This explains why you’ll get an image that’s 244 pixels wide when you take a screenshot of our button, despite the fact that it has a width: 200px declaration attached to it ( box-sizing: content-box)
- after changing it to box-sizing: border-box (This forces the actual width of the box to be 200px—including padding and borders. Of course, this means that the content width is now determined automatically:)
- This is much more intuitive, and as a result, using border-box for all your boxes is considered a best practice among modern web developers.

Align box:

- Aligning boxes horizontally is a common task for web developers, and the box model offers a lot of ways to do it. We already saw the text-align property, which aligns the content and inline boxes inside of a block-level element. Aligning block boxes is another story(aligning inline boxes or content using text-align)

Solution:

- There are three methods for horizontally aligning block-level elements: “auto-margins” for center alignment, “floats” for left/right alignment, and “flexbox” for complete control over alignment. Yes, unfortunately block-level alignment is totally unrelated to the text-align property.

Align inline level:

- Left, right, justify and center (text-align)

Align block level:

- Horizontal for block level (margin-auto{center alignment})
- left and right alignment (float)
- Complete control over alignment (flex-box)

Pseudo-Classes(Basic Link Styles)::

- link – A link the user has never visited.
- visited – A link the user has visited before.
- hover – A link with the user’s mouse over it.
- active – A link that’s being pressed down by a mouse (or finger).

Pseudo-Classes For Structure(There’s also a bunch of other pseudo-classes that provide extra information about an element’s surroundings. ):

- p:last-of-type

URL Fragments:

- Schema, domain. path, fragment

Notes:

vertical-align:middle because it's not applicable to block-level elements
margin-top:auto and margin-bottom:auto because their used values would compute as zero
margin-top:-50% because percentage-based margin values are calculated relative to the width of containing block
If the display of your parent container is flex, then yes, margin: auto auto (also known as margin: auto) will work to center it both horizontally and vertically, regardless if it is an inline or block element.

<!-- #parent {
    width: 50vw;
    height: 50vh;
    background-color: gray;
    display: flex;
}
#child {
    margin: auto auto;
} -->

<!-- <div id="parent">
    <div id="child">hello world</div>
</div> -->

Mastering the css calculations:

- Content width is 100%
- Space needed (5) = (1% * 5) = (5%)
- Available Space = 95%
- Width for each element(4 elements) = (95%/4)

------------------------------------------------------------------------------------

Cover -> gonna stretch the dimensions of the image
Contain -> gonna make the dimensions of it similar to parent

Http request- solve too many request from the server for images - using spreadsheet - spirits

remove the element and don't reserve his place act like it doesn't exist - display:none;
visibility: hidden;
opacity:0; - div + div content --- rgba affects on the background only - reserve place
overflow: hidden - no reserve place - if it's width is increased -  it deletes the rest / overflow: scroll and adds scroll bar
overflow: auto if it's increased it adds scrollbar otherwise

(margin collapse) is solved using overflow
giv parent overflow: hidden;

/*
outline doesn't add up to the width of the box

border can act like outline if we made box-sizing: border-box

/*
outline can't pick each side you want
there is no outline-radius

display: block;
-block takes full width as long as you didn't mention a specified width
-apply all width, height and margin and padding
-add line break

display:inline
-no line break
-no to all (padding and margin only works left and right) top and bottom if added block line like div, it will overflow the content of div

display:inline-block;
-combines both inline and block
-width if fitted according to content's width

Display: none
removed and hidden even from workflow

visibility: hidden;
hide the element but keeps it's place in the workflow

Use case:
if there is a possibility that your box will increase size in the future or stretched out then
min-width is better than width, same for max-width (height also has the same properties)

using display: inline-block to make width fit content is not the best practice so we use
width: fit-content;

overflow: visible; (default behavior) - can control x and y axis

- hidden when it exceeds the width of the div, the content is hidden
- scroll when it exceeds a right scroll bar appears

text-shadow:
horizontal - x axis
vertical - y axis
noise - increase fog
color - use rgba for alpha opacity

text-align:

- justify -> extend text to fit the width of box
!important

text-direction:
control content position in the page
direction:
control direction of content in the page

letter-spacing:
word-spacing:
text-indent: better than padding for text
lne-height: 1.6
white-space:nowrap -> doesn't break line
word-break: works if words are outside the div -> break-word;
text-overflow: ellipsis; put three dots to show that the words is still not finished

div:hover{
    overflow:visible;
}
    instead using this we use html attribute called title

    div - border: 2px solid red
    div p - border-color: initial;

CSS units
px
percentage
em => time = takes initial values from parent
rem => root time - takes initial values from parent which is html tag
vw => viewport width
vh => viewport height
vmin => viewport minimum

Notes:
1em = 16px (This is wrong) - em according to parent's font size
default font size is 16px

font-variant: small-caps only makes capital word  but with smaller font-size compared to text-transform: capitalize

Solve float issues with overflow-hidden;
use case:
if you have a pop up or drop down menu then this is not gonna work
or
specify a height for the parent element not optimal solution

content width is: 100%
5 spaces is 1% * 5 => 5% from content width
95% available space
4 elements, the width is gonna be 95% / 4

instead of calculating values for float we can use
width:calc(95% / 4);

if we want margin-left: 15px;
6 spaces - 15px * 6 => 90px from content width
100% - 90px available space
5 elements width:calc((100% - 90px) / 5);

<!-- 
control opacity in background-color using rgba (alpha) only controls color intensity
control opacity for the whole content using opacity 
-->

1 is the largest - while 0 is the least amount of value
use case:
like modal in bootstrap

when we use margin the whole workflow is moved even if we picked one div

position: static; default behavior

position: relative; compared to his position - his position is his initial value
can freely move in the workflow with no effect on others

position:absolute;
the parent dimensions which is the page is his initial values - this can make the other div overlap the original div

So when we give it
bottom:0;
right:0;

now when we make margin to the first div, it won't affect the other div we put position: absolute to

to make the nested div inside the parent move within the parent's dimensions, put position: relative to the father
and our div has position: absolute

position: fixed;
the div that has the position fixed doesn't take into his consideration the main position of the parent nor the parent div,
he is connected to the viewport

use case:
scroll to up button
position fixed;
bottom:0;
right; 0;

position: sticky;
it reserves his place normally in the workflow

use case:
when we scroll down, some navbar styles stick to the top viewport ( used to be made using javascript but now sticky is easier)

position: sticky;
top: 0;

z-index
position: absolute;
3 divs
last one will be the first one (according to html order)

z-index works with bigger numbers as it's indicator for priority
use case:
if 2 elements take same z-index then order of html decides who is gonna be shown - last element in html has more priority as it works line by line

in order to make position works - we have to put position: absolute

z-index helps us to put order to elements that overlays each other like modal and side nav or drop down
/

list-style-position: outside; / inside
list-style-image: url();
list-style: type position image
list-style: none;
padding-left: 0;

in table
we would like to add spacing => border-spacing: 10px;

state like hover or visited
a:hover{
    color: red;
}
.ch:checked + label{
 color: red;
}

div:empty{
border: 10x solid red;

:empty{
background-color: blue;
}

in:focus{
background-color: blue;
}

pseudo elements
.two::first-letter{
    color: red;
}
.two::first-line{
    color: red;
}  

control selection color
::selection{
background-color: yellow;
}
.four::selection{
background-color: yellow;
}

Pseudo elements (most important) (before, after and content)

after and before pseudo element:
we have to add content in order to make the element appear
<!-- 
.one::after{
    content:""
}
-->

<!--
counter-increment: members-counter;
counter(members-counter);
--------------------------
data-transfer:"text"
content: attr(data-text);
-->

<!--
Vendor prefix:
 ------------------------ 
 prefix is used until the property is fully ready
(webkit = chrome, safari, new opera version)
(mos = firefox)
(ms = ie, edge)
(o = old version of opera)
------------------------
-webkit-border-radius: 10px;
-moz-border-radius: 10px;
-o-border-radius: 10px;
-ms-border-radius: 10px;
border-radius: 10px;
------------------------
Task runner - auto implement prefix for css
border-top-left-radius: 20px 10px;
------------------------
Box-shadow has more values than text-shadow  
h-shadow
v-shadow
blur
spread
color
inset or outset
box-shadow: 10px 10px 5px 10px grey, 10px 10px 5px 10px grey ;
------------------------
default => box-sizing: content-box (any margin, padding or border is added to width and height)
if you didn't add height - it will take value from padding 

*{
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
-->

<!--
flex-box uses two new properties:
flex-containers and flex-items
flex-container => group a bunch of flex-items together and positions them 
-->

<!-- 
Every direct child of container is an item, flex item can be manipulated individually (container determines the layout)

to activate the flexbox functionality in your div, write display: flex to control it

Explicitly defining flex containers means that you can mix and match flexbox with other layout models (e.g., floats and everything we’re going to learn in Advanced Positioning).

Flex can change their alignment, direction, order, and size

Define the flex-container: (go to the parent div)
display:flex;

Aligning a flex-item: (Define a horizontal alignment for the flex-item, also in the parent div)
justify-content: center; 
(same effect as adding margin: 0px auto;), (flex-start, center, flex-end, space-around, space-between)

Using multiple flex-items together:
justify-content: space-around and space-between;

Flex-containers only understand how to position one level deep children elements, doesn't care what's inside the 
flex-item, grouping flex-items is different

Vertical-alignment:
using align-items
center
flex-start (top)
flex-end (bottom)
stretch
baseline

flex-wrap: nowrap or wrap

Direction (row, column)
flex-direction: column;

(in column)
flex-direction: column;
justify-content:center;
align-items: flex-start;

(in rows)
flex-direction: row;
align-items:center;
justify-content: flex-start;

flex property:
no-flex
equal-flex
unequal-flex

We can even mix-and-match flexible boxes with fixed-width ones
flex: initial

Flex Items and Auto-Margins(Auto-margins in flexbox are special. They can be used as an alternative to an extra <div> when trying to align a group of items to the left/right of a container. )
-----------------------
Properties:
    Use display: flex; to create a flex container.
    Use justify-content to define the horizontal alignment of items.
    Use align-items to define the vertical alignment of items.
    Use flex-direction if you need columns instead of rows.
    Use the row-reverse or column-reverse values to flip item order.
    Use order to customize the order of individual elements.
    Use align-self to vertically align individual items.
    Use flex to create flexible boxes that can stretch and shrink.
-->

<!-- 
main-axis =>  “horizontal”
cross axis => “vertical”
 -->

<!-- 
6 different properties the flex container can take on.

1. Flex-direction#
  flex-direction: row || column || row-reverse || column-reverse;
  Technically, “horizontal” and “vertical” isn’t what the directions are called in the “flex world”.
  These are described as main-axis and cross axis

2. Flex-wrap#
    flex-wrap: wrap || no-wrap || wrap-reverse;
    This is because the flex-wrap property defaults to nowrap. This causes the flex container to NOT wrap.
    the flex-items now break up into multiple lines when needed. after using flex-wrap: wrap;

3. Flex-flow#
	flex-flow: row wrap; /*direction 'row' and yes, please wrap the items.*/
    The flex-flow is a shorthand property which takes flex-direction and Flex-wrap values.

4. Justify-content#
    justify-content: flex-start || flex-end || center || space-between || space-around || space-evenly
    The justify content property defines how flex items are laid out on the main axis.

5. Align-items#
	align-items: flex-start || flex-end || center || stretch || baseline
    It defines how flex-items are laid out on the cross axis.
    (Default-value: stretch=> to fit content(so if you give a flex-item different height, the others will be stretched))
Stretch#
The default value is stretch. This will “stretch” the flex-items so they fill the entire height of the flex container.

Baseline#
It aligns flex-items along their baseline

6. Align-content#
    Align-content: flex-start || flex-end || center || stretch || baseline
    By definition, it controls how the flex-items are aligned in a multi-line flex container.
-->

<!-- 
5 different properties the flex items can take on.

    1. Order#
    order: 1;
    The order property allows for reordering the flex items within a container.

    2. Flex grow and flex shrink#
    flex-grow: 1;
    The flex-grow and flex-shrink properties control how much a flex-item should “grow” (extend) if there are extra spaces, or “shrink” if there are no extra spaces.
    They may take up any values ranging from 0 to any positive number. 0 || positive number
    By default, the flex-grow property is set to 0. By implication, the flex-item does NOT grow to fit the entire space available.
    The value 0is like a “turn-off” switch. The flex-grow switch is turned off.However, if you changed the flex-grow value to 1, here’s what happens.
    similar to width: fit-content;

    3. Flex basis#
    flex-basis: auto; percentages || ems || rems || pixels
    The flex-basis property specifies the initial size of a flex-item. Before the flex-grow or flex-shrink properties adjust it’s size to fit the container or not.

    4. The flex shorthand#
    The flex shorthand allows you set the flex-grow, flex-shrink and flex-basis properties all at once.
    flex: 0 1 auto;

    //this is an absolute flex item
    li {
    flex: 1 1; //flex-basis defaults to 0;
    }

    //this is a relative flex item
    li {
    flex-basis: 200px; //only flex-basis is set
    }

    5. Align-self#
    	align-self: auto || flex-start || flex-end || center || baseline || stretch
    What if you wanted to change the position of a single flex-item along the cross-axis, without affecting the neighboring flex-items?
 -->

<!--
The spacing within a relative flex item is computed based on it’s content size. In an absolute flex item, it is based solely on “flex”, not content. 
-->

<!-- 
Beware of margin: auto alignment on flex items.
Remember what I said earlier? When you use margin:auto on a flex-item, the direction (left, right or both) that has the value auto will take up any empty spaces available. It doesn’t end with just one side. What if you wanted a margin auto alignment on both sides of a flex-item?
-->

<!-- 
When to use flex Grow:
when you want flex-items to scale up to take remaining width from the flex-container.

Flex-grow default size is zero

When to use flex-shrink?
when the sum of flex-items have bigger width than the container, so you tell them instead of over-sizing the flex-container shrink to fit it.
Flex-grow default size is one

Default behavior:
when giving the flex-items a width bigger than the flex-container it will shrink then to fit the parent
-->
<!-- 
order=> least value of number equals highest priority
-->
<!-- 
flex-basis:
determines the width or height of the element or flex-item according to the flex-direction of flex-container

if we gave it row - then width 
if we gave i column - then height
flex-basis default size is auto
 -->

<!--
Examples:
    Bootstrapped Navigation
    AirBnB desktop Navigation
    Twitter desktop Navigation
-->

<!-- 
Transition:
Duration
Property
Delay
Timing Function
-->

<!-- 
Margin-collapse:
[1] only happens in vertical alignment
[2] bigger margin wins
[3] happens only if they are right below each other (no divider between them)
[4] nesting doesn't stop margin collapsing from happening
-->

<!-- 
Css variables:
    Global Variable
    Local Variables
}
(Global)
:root{
    --mainColor: blue;
    --secondaryColor: yellow

var(variable name, fallback value)
var(mainColor, red)

(Local)
.local{
    color: var(--mainColor);
}
-->
<!-- 
Header
Main
Footer
-->

<!-- 
In order to work align-content, we must have multiple wrapping rows - space distributed between them and also o parent's height to be taller than the children
-->

<!-- 
shorthand for align-content and justify content is to use place-content: center 
-->

<!-- 
Justify content - according to content (Scale up according to width and height of content)
Align-items - Scale up into the line of content more like baseline
-->

<!-- 
filter: grayscale(100%) - blur(4px) - invert(100%) - 
-->

<!-- 
Gradients:
linear-gradient(Direction || Angle, color stop1, color stop2)

background-image: linear-gradient(0deg = top, red, green)
background-image: linear-gradient(90deg = right, red, green)
background-image: linear-gradient(to right, red 80%, green)
background-image: linear-gradient(to right, red 20%, green 20%, green 100%)
background-image: linear-gradient(to right, red 20%, green 20%, yellow 30%, yellow 50%)

width:800px;
height:200px;
-->

<!-- 
<p contenteditable="true">
content can be edited
</p>

change caret-color => 
caret-color: red;

pointer-events: none;
 -->

<!-- 
Grid system
Grid:
number of columns is 3
measurement unit [px, %, auto, repeat, fraction ]
grid-template-columns: 100px 100px 100px ;
grid-template-columns: repeat(5, auto) ;
grid-template-columns: 100px 200px 25% auto;
100px -200px -> 300px
25% from 800px => 200px
100px - 200px - 500px

fr = 1 time space left
fraction vs auto: 
fraction is greedy
auto is shy

width is 800px
100px 100px 1fr 1fr
each fr equals 300px

100px 100px 1fr 2fr
each fr equals 100px

auto min-width is scaled up at least to fit content
-->

<!-- 
grid-template-rows: 100px ;
so if i made 3 columns and added one value in rows then this height will be applied only on first row  and the rest is divided on the remainder rows

number of rows height:
grid-template-rows: repeat(5, auto) ;

row-gap:20px
column-gap:20px
gap:20px [row-gap , column-gap]
-->

<!--
no movement if there is no space left (if you used fr for example) 
so if we have  
justify-content: flex-end
-->

<!--
 grid-template-areas:"logo logo logo nav nav nav" 
 grid-area:nav
-->

<!-- 
grid for child:
starts with column 1 and end with 5
grid-column-start:1
grid-column-end:5
grid-column:1/5

instead of doing this, we do
grid-column: span 4; => take 4 columns - ignoring start and end

pick a child and put 
grid-column: 2/ span 3; it will leave the first space - (offset) and take 3 columns

grid-row:same like column
-->
<!-- if we added row 0r column more than listed a row or column will be added -->
<!--
grid-template-columns:repeat(6,, 1fr)
there are 3 rows - 6 columns
grid-row-start:2;
grid-row-end:3;

grid-column-start:2;
grid-column-end:2;

grid-area: 2/2/5/6;
grid-row-start:2;
grid-column-start:2;
grid-row-end:3;
grid-column-end:2;
-->
<!-- 
    grid-template-columns: repeat(3,minmax(90px, 1fr));
-->
<!-- 
grid-template-areas: "head head head head head"
->
<!--Autofill - calculates the number of column according to the value of the width - so if we have a full width of 500 and have width 100 for each column, then they're gonna be 5 columns   -->
<!-- grid-template-columns:repeat(auto-fill, minmax(200px, 1fr)) -->
<!-- 
Absolute Links

Links to pages on other websites on the internet are called absolute link

Relative Links

Links to other pages within our own website are called relative links.
-->
<!-- 
The form element accepts two essential attributes; the first is the action attribute which takes a URL value that tells the form where it should send its data to be processed. Later in the curriculum, we will learn to hook backend systems up to frontend forms using this attribute. For now, it’s only essential to know what the action attribute is used for.

The second is the method attribute which tells the browser which HTTP request method it should use to submit the form. The GET and POST request methods are the two you will find yourself using the most.

We use GET when we want to retrieve something from a server. For example, Google uses a GET request when you search as it gets the search results.

POST is used when we want to change something on the server, for example, when a user makes an account or makes a payment on a website.
-->

<!-- 
Styling Validations

We can target form controls that have passed or failed validations using the :valid and :invalid pseudo-classes.
-->

<!-- 
2D - Transform:
scaleX - horizontal => default value = 1
scaleY - vertical => default value = 1  
scale - shorthand - if you want to apply both of them

there is a huge difference between width and scaling:
 - width only enlarge dimensions of box
 - scale, stretch everything out, margin, padding and content are all enlarged

what if we gave negative value?
 it will be flipped into the opposite direction 

Examples:
 transform: scaleX(-1);
 transform: scale(-1)
 transition: 0.5s
-->

<!-- 
 2d transform:
 rotate

Measuring units:
 deg => degree
 rad => Radians
 grad => Gradians
 turn => Turn
-->

<!-- 
 transform: rotate(0deg);
 transform: rotate(10deg);
 transform: rotate(20deg);
 transform: rotate(30deg);
 //
 transform: rotate(90deg);
 transform: rotate(180deg);
 transform: rotate(360deg);
 //
 transform: rotate(0.5turn);
 transform: rotate(0.25turn);
 //
 Negative value?
 rotate in the opposite direction
 //
 transition: 0.5s;
-->

<!-- 
Use Cases of scale and rotate:
 img in html file

 .image{
     overflow: hidden;
     width: 720px;
     height: 350px
 }
  .image img{
  transition: 0.3s;
  }

  .image:hover img{
      transform: scale(1.3);
  }
-->

<!-- 
 If we put 
 transform: scale(1.3;)
 transform: rotate(180deg);

 => Scale won't work, cuz rotate resets the work done by scale

 Solution if we want to use both of them:
    transform: scale(1.3) rotate(5deg);
    opacity: 0.6;
-->

<!-- 
    2d Transform translate:
    measuring units => px, rem or percentages
    2nd value default number is zero

    Example:
    (horizontally)
    transform: translate(100px, 0);
    transform: translate(-100px, 0);

    (vertically)
    transform: translate(0x, 100px);
    transform: translate(0, -100px);

    Why we use translate instead of margin padding and any other stuff?
    => better in animation, better performance and many more stuff

    Centering a div using translate?
    ->  transform: translate(-50%, 50%);

    Note:
    Don't forget to use prefixes
-->

<!-- 
    Skew
    transform: skewX(10deg)
    transform: skewY(120deg)
    transform: skew(10deg, 50deg)
-->

<!--
    Matrix
    You only write value, not degrees or measurement tools
    transform: matrix(scaleX(), skewY(), skewX(), scaleY(), translateX(), translateY());
    note:
    order of functions matter
-->

<!-- 
    origin
    picking a main point
    transform-origin: 50% 50% or center center
-->

<!-- 
    3d Transform (x, y, z)
    transform: rotate3d(0, 1, 1, (5deg));
-->

<!-- 
    3d Transform 
    translate3d(x, y, z)
    perspective > decide the distance between the parent and the child- by increasing value, you will reach the vanishing point
    perspective-origin
-->

<!-- 
    back-face visibility and flip product
    default value is visible
    backface-visibility: hidden
    ---
    transform-style: flat; => doesn't preserve it's position in 3rd
    transform-style: preserve-3d;
-->

<!-- 
    Animation - keyframes
    ---
    give animation name to the desired div
    animation-name: change-color
    animation-duration: 6s;
    ----
    @keyframes change-color {
        from {
            background-color: red;
        }
        to {
            background-color: blue;
        }

        0% {
            background-color: red;
        }

        100% {
            background-color: blue;
        }
    }
    ---
    animation-duration: 1s;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
-->

<!-- 
    animation-direction, fill-mode, play-state, delay
    animation-fill-mode:forwards ;
    after finishing the pattern, it stops with the last keyframe attributes
-->

<!-- 
    Loading animation (UP & Down)
-->

<!-- 
  - Element => [p, div, h2]
  - Element OtherElement => div p
  - .class-name
  - #id-name
  - .parent .child
  - .class-one.class-two
  - .class-name div, .class-name p
  - Element.class-name => p.class-name
  - .parent > .child => Direct Child
-->

<!-- 
  - Element + Other Element => [div + p]
  - Element ~ Other Elements => [p ~ div]
  - [Attribute]
  - Element[Attribute]
  - [Attribute=Value]
  - Element[Attribute=Value] => input[type="submit"]
  - [Attribute~=Value] => Contains A Word
  - [Attribute*=Value] => Contains A String
  - [Attribute^=Value] => Start With A String
-->

<!-- 
  CSS Selectors
  - :first-child
  - :last-child
  - :first-of-type
  - :last-of-type
  - :only-child
-->

<!-- 
  - :not(Selectors)
  - :nth-child(n)
  - :nth-last-child(n)
  - :nth-of-type(n)
  - :nth-last-of-type(n)
-->

<!-- 
  - :root
  - :checked
  - :empty
  - :disabled
  - :required
  - :focus
  - ::selection
  - ::placeholder
-->

<!-- 
    Responsive - Media Queries
    <link rel="stylesheet" href="css/print.css" media="print" or media="(width:5px) and font-size:5px">
    <style media="print>.parent{font-size:10px;}</style>
    (Breakpoint)
-->

<!-- 
    Mobile First Design:
    Test Devices
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
-->

<!-- 
    Create your framework
    Make custom css group (If you gonna use it in many cases - if you have a lot of thing so you group it)
-->

<!-- 
    Css Global Values:
    inherit
    initial => default value for any element is inline and browser style agent differentiate between elements like p, heading and others by changing display's value into block
    color property's value differ from browser to another
    unset
        if inherit => inherit (If it can inherit it's value then go for it)
        if not => initial (If it can't inherit it's value then go for initial value)
    revert css level [4] - make it uses styles of user agent
    all    
-->

<!-- 
    Notes:
    use paddings instead of margins for (a) buttons
-->

<!-- 
    Reset all the default values for button by using:
    all: unset;

    in order to reassign it's value, order of unset is important
    so unset is better be oat the top to remove the default value

    Give image width: (percentage)
    height: auto
    give it max-width instead of just width when using height:auto
-->

<!-- 
    there is attribute in image called loading="lazy" => works on firefox
-->

<!-- 
Reference:
https://www.internetingishard.com/html-and-css/flexbox/
https://www.educative.io/courses/understanding-flexbox-everything-you-need-to-know/B8nngXNzgQX
https://www.educative.io/courses/understanding-flexbox-everything-you-need-to-know/m2OD8lPmjO3
https://courses.kevinpowell.co/view/courses/conquering-responsive-layouts/233002-introduction/1007804-intro-why-the-course-is-formatted-in-this-way
https://css-tricks.com/a-complete-guide-to-css-media-queries/
https://css-tricks.com/snippets/css/media-queries-for-standard-devices/
 -->