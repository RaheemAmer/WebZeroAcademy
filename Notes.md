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

---------------------------------------------

after and before pseudo element:
we have to add content in order to nake the element appear
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
    justify-content: flex-start || flex-end || center || space-between || space-around
    The justify content property defines how flex items are laid out on the main axis.

5. Align-items#
	align-items: flex-start || flex-end || center || stretch || baseline
    It defines how flex-items are laid out on the cross axis.

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
Reference:
https://www.internetingishard.com/html-and-css/flexbox/
https://www.educative.io/courses/understanding-flexbox-everything-you-need-to-know/B8nngXNzgQX
https://www.educative.io/courses/understanding-flexbox-everything-you-need-to-know/m2OD8lPmjO3
 -->
