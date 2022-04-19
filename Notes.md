# WebZeroAcademy-notes

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
em => time
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

control opacity in background-color using rgba (alpha) only controls color intensity
control opacity for the whole content using opacity
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
