- For commenting

```html
<!-- ignore text -->
```

- Tag list: main header footer nav video article
- <!DOCTYPE html> at the top every time
- img element is a self closing tag. src is an attribute of img
- a href=”url” target=”_blank” for opening page in new tab
- main tag for specifying the main section of the page

```html
<html>
  <body>
    <h1>CatPhotoApp</h1>
    <main>
      <section>
        <h2>Cat Photos</h2>
			</section>
		</main>
	</body>
</html>
```

- ul for unordered lists, ol for ordered lists
- The figure element represents self-contained content and will allow you to associate an image with a caption. A figure caption (`figcaption`) element is used to add a caption to describe the image contained within the `figure`element. For example, `<figcaption>A cute cat</figcaption>` adds the caption `A cute cat`
- em element for emphasis (its basically italics)
- strong element for bold
- form element for making forms. Its action attribure shows where the data is to be sent
- input element for taking input. They are also self closing like img. Many different attributes for input element exist. Like text. Name attribute of input element for making sure the web page owner knows what the form is for since there can be multiple forms on the same page

```html
<input type="text" name="catphotourl">

<!-- for indicating to the user what the form is about, we use placeholder attribute of the input element -->

<input type="text" name="catphotourl" placeholder="cat photo url">

```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/564048d6-283e-40d4-9ac5-30f60ee2677f/Untitled.png)

- add “required” attribute to input to make sure the user cannot  submit without filling those details. It is a valueless attribute. Just put it there.
- button element for creating a button
- `label`
 elements are used to help associate the text for an `input`
 element with the input element itself (especially for assistive technologies like screen readers). For example, `<label><input type="radio"> cat</label>`
 makes it so clicking the word `cat`
 also selects the corresponding radio button.
- id attribute is used to identify specific HTML elements. Each id attribute’s value should be different from the others on the page. ie. they should be unique
- name attribue is important for radio buttons to function properly. Out of two buttons with the same name attribute, only one can be selected. Add the name attribute for checkboxes as well so that is easier for the server to decipher
- The `fieldset`
 element is used to group related inputs and labels together in a web form. `fieldset`
 elements are *block-level elements*, meaning that they appear on a new line.
- The `legend`
 element acts as a caption for the content in the `fieldset`
 element. It gives users context about what they should enter into that part of the form.



- Associate the text `Loving`
 with the checkbox by only nesting the text `Loving`
 in a `label`
 element and place it to the right side of the checkbox `input`
 element.

```html
<input id="loving" type="checkbox" > <label for="loving">Loving</label>
```

- For checking the radio or checkbox by default, add valueless attribute “checked”
- lang attribute of html for specifying the language of the page

```html
<html lang="en">
</html>
```

## Cat Photo App

---

---

- <meta> is as self closing element

```html
<head>
    <meta charset="utf-8" />
    <title>Camper Cafe Menu</title>
  </head>
```

- Since the `p` element added in the previous step provides supplemental information about the cafe, nest both the `h1` and `p` elements in a `header` element.

```html
<header><h1>CAMPER CAFE</h1>
    <p>Est. 2020</p></header>
```

- For CSS styling we use semi colons at EOL

```html
<style>
      h1{
        text-align: center;
      }
    </style>

<style>
      h1,h2,p {
        text-align: center;

    </style>
```

- We don’t use the styles tag actually, we just make a separate .css file and we link it to our html file

```html
<head>
    <meta charset="utf-8" />
    <link rel="stylesheet" type="text/css" href="styles.css" />
    <title>Camper Cafe Menu</title>
  </head>

<!-- Notice the / at the end of the link element  Just like meta-->
```

- div element is used for design layout purposes
- something{} is called a type selector
- Commenting in css with

```css
/*teri mammi*/
```

- for adding style to classes instead of elements, we use .classname{} instead of  classname{}
- `article`elements commonly contain multiple elements that have related information.
- hr for making a horizontal line. It is a self closing tag <hr />
- To target all the p elements which are nested inside an element which has a class “example

```css
.example p{
	background-color:brown;
}
```

- You change properties of a link when the link has actually been visited by using a *pseudo-selector*
 that looks like `a:visited { propertyName: propertyValue; }`
- You change properties of a link when the mouse hovers over them by using a *pseudo-selector*
 that looks like `a:hover { propertyName: propertyValue; }`
- You change properties of a link when the link is actually being clicked by using a *pseudo-selector*
 that looks like `a:active { propertyName: propertyValue; }`

## Cafe Menu

---

---

- When the shorthand `margin`
 property has two values, it sets `margin-top`
 and `margin-bottom`
 to the first value, and `margin-left`
 and `margin-right`
 to the second value.

```css
/* I M P */
margin: 25px 3px;
/*sets the top and bottom margin to be of 25px and the left and right margins to be of 3px*/
```

- For multiple classes of a single element, just add a space between two class names

```html
<div class="one marker">
<!-- Gives this div 2 classes : one and marker -->

```

- Primary colours: red green and blue
- Secondary colours: yellow (red and green), cyan (green and blue), magenta (blue and red)
- Tertiary colours: orange( red and yellow), spring green( green and cyan), violet (blue and magenta), chartreuse green (green + yellow), azure (blue + cyan), and rose (red + magenta).
- Two colors that are opposite from each other on the color wheel are called *complementary colors*
. If two complementary colors are combined, they produce gray. But when they are placed side-by-side, these colors produce strong visual contrast and appear brighter.
- Hex color values start with a `#`
 character and take six characters from 0-9 and A-F. The first pair of characters represent red, the second pair represent green, and the third pair represent blue. For example, `#4B5320` With hex colors, `00`
 is 0% of that color, and `FF`
 is 100%. So `#00FF00`
 translates to 0% red, 100% green, and 0% blue, and is the same as `rgb(0, 255, 0)`

- The *HSL* color model, or hue, saturation, and lightness, is another way to represent colors.The CSS `hsl` function accepts 3 values: a number from 0 to 360 for hue, a percentage from 0 to 100 for saturation, and a percentage from 0 to 100 for lightness. If you imagine a color wheel, the hue red is at 0 degrees, green is at 120 degrees, and blue is at 240 degrees. Saturation is the intensity of a color from 0%, or gray, to 100% for pure color. Lightness is how bright a color appears, from 0%, or complete black, to 100%, complete white, with 50% being neutral. In the `.blue` CSS rule, use the `hsl` function to change the `background-color` property to pure blue. Set the hue to `240`, the saturation to `100%`, and the lightness to `50%`.
- A gradient is when one color transitions into another. The CSS `linear-gradient` function lets you control the direction of the transition along a line, and which colors are used. One thing to remember is that the `linear-gradient` function actually creates an `image` element, and is usually paired with the `background` property which can accept an image as a value.
- Default gradient direction is 180deg

```css
red {
  background: linear-gradient(90deg, rgb(255, 0, 0) 75%, rgb(0, 255, 0), rgb(0, 0, 255));
}
/*75% is a color stop */
```

- rgba for adding alpha channel to rgb function

```css
border-left-width: 10px;
  border-left-style: solid;
  border-left-color: black;
/*can be replaced by*/
  border-left:10px solid black;
```

```css
box-shadow: 5px 5px 5px(optional) 5px(optional) red;
 x offset y offset blurradius spreadradius color
```

- With `type="password"`
 you can use the `pattern`
 attribute to define a regular expression that the password must match to be considered valid.

```html
<label>Create a New Password: <input type="password" pattern="[a-z0-5]{8,}" required /></label>
<!--The above is a regular expression which matches eight or more lowercase letters or the digits 0 to 5.-->
```

- “select” element for creating drop downs
- use the element “textarea” for multi-line writing
- To give the `fieldset`
 elements a bit of separation, select all but the last `fieldset`
 element, and give them a `border-bottom`
 of `3px solid #3b3b4f`

```css
fieldset:not(:last-of-type){
  border-bottom:3px solid #3b3b4f
}
```

## Tutorial: Color Markers

---

---

## Tutorial Registration Form

---

---

- filter property in css for filters:

```css
filter:blur(20px);
```

- The `border-radius`
 property accepts up to four values to round the top-left, top-right, bottom-right, and bottom-left corners.
- transform property for transforming

```css
transform: rotate(-0.6deg);
/* - for anticlockwise*/
```

- #id  is an id selector
- For flex in  #gallery

```css
#gallery {
  display: flex;
  flex-direction: row; /*decidesthe main axis */
  flex-wrap: wrap;
  justify-content: center;/*for main axis*/
  align-items:center;/*for cross axis*/
}
```


Q. Create a media query for screens smaller than `800px`
 in width. In that media query, create a `#gallery img`
 rule and set the `width`
 property to `50%`
. This will convert your gallery to a two-column layout.

```css
@media (max-width:800px){
  #gallery img{
    width:50%;
  }
}
```

- Title should be between 20 and 60 characters
- Target unordered list elements within `nav`
 elements, and use *Flexbox*
 to evenly space the children.

```css
nav>ul{
		display:flex;

	justify-content:space-evenly;
}
```

The key difference between tr[class="total"] and tr.total is that the first will select tr elements where the only class is total. The second will select tr elements where the class includes total.

- Combine media queries with and

```css
@media (max-width: 1199px) and (min-width: 769px) {
}
```

- loading attribute to set loading behavior

```html
<img src="somethin" loading="lazy"/>
<!-- Lazy Loading will not load the image until it is required for example it will only
 load once the user scrolls to the part where the image is -->

```

- Default font size is 16px (this is also the value of 1em)

- Animation properties shorthand:
animation: animation-name animation-duration animation-timing-function animation-iteration-count

```html
animation: animation-name animation-duration
```

# Frontend developer career path scrimba

Absolute units: px (llike cm, mm etc)

Percentage: Mainly sued for width. It is relative to the parent except when it comes to height. Things get weird when its about height

Relative units: 1. relative to font size (rem, em)  2. relative to the viewport (vw, vh, vmin, vmax)

- em is relative to its parent
- the bad thing is that when we use em for font size of an element, it can create a cascading effect. Cascading effect happens in nested elements. For example:
- 

```cpp
<li>Hello
	<p>Hi
		<h1>ok</h1></p></li>

//if we set ems for these three separately, the effect will add up. h1 will face the ems 
//used on h1 p and li

```

## rem does NOT stand for relative em. It stands for root em

rule of thumb (not hard and fast rules):

font-size: rem

padding/margin: em

widths: em or %

Note: if you use ems on the font size property, it is looking at the parent element. On any other property, it is relative to the font-size of that element. This is why it is confusing.

by default display:block is there for:
div
header
footer
main
h1 to h6
p

they stack on top of each other

inline elements stay within the flow of what’s around them
a
strong
em
span



### Media Queries

- Basic syntax of media queries is:
@media media-type  and (media-features) {}
- media types include:
screen (@media screen)
print 
speech
- media conditions include:
widths (@media (min-width: 600px){})
orientation
specific features for example @media (hover){}
- we can combine type with media condition like:
@media screen and (min-width:960px){}

- text-align:center centres the text within its parent

Note: Media queries after the required selector, not before

- <aside> tag is also there. Works as it sounds ie it is used for enclosing the sidebar design html. Not just sidebar though, anything apart from main can be put inside <aside> for semantic and organizational purposes.
- We can have multiple aside tags but only one main tag

- The <***article***> ***tag*** specifies independent, self-contained content. Again, used for organizing code and also for accessibility purposes.

- We can change the order of things in html and make them look another way using flexboxes. This is useful for accessibility reasons.

- For images, use display:block because the default is inline and that causes some spacing issues.

- Try to go Mobile first while designing a webpage. Makes the process a lot easier. min-width media query comes into play.

- object-fit property for reducing the size of images by cropping them instead of stretching/squishing them. object-position property to specify which part of the image we want to keep

 

```css
.article-image {
        width: 100%;
        min-height: 250px;
        object-fit: cover; /*sheeeeesh*/
        object-position: left; 
/* keeps the left side of the image in frame */
    }
```

text-transform for changing case

```css
text-transform:uppercase;
text-transform: capitalize; /*for sentence case*/
```

by default, images do not change their size when imported using background-image. They keep tiling if the specified size exceeds their original size

background-size:cover works the same as object-fit:cover

## Combinators

1. +

```css
h1 + p{
/*code*/
}

/*this means adjacent sibling ie. paragraph is immediately after h1 */

```

1. ~ 
    
    It means general sibling. Doesn’t necessarily have to be immediately after it. It has to be after though
    

```css

```

If we want to set the responsive height of something (in percent for example) then its parent should have a fixed height. But, setting height can be dangerous as it can cause anomalous behaviour
vmin sees which is smaller: height or width and then applies it
vmax does the opposite

- box-sizing default is content-box and it covers the specified width + margin+ padding + border
when box-sizing:border-box is done, then the specified width/height INCLUDES the margin padding etc.
use box-sizing with the * selector as it just makes things easier
- > for direct children only. If nested inside nested, then it won't be applicable.

<input type="color" />

attribute selector for example
[type="text"]{
margin-bottom:1px
}

- fonts are not inherited by default in forms. We need to explicitly state that we want to inherit.

gradients are a type of background-image!
to right to left etc.
.box-1 { background-image: linear-gradient(to right, red, blue); }
.box-2 { background-image: linear-gradient(45deg, green, yellow)}

background: linear-gradient...
will also work

transition property
transition: color 500ms

border-image: linear....
for border gradient

when both background-image and background-color properties are there, we can use background-blend-mode property (like photoshop). It has values like: mmultiply (for keeping the darkest pixels), screen (light), overlay (neutral and increases contrast)

CSS properties for full page background image

[https://css-tricks.com/perfect-full-page-background-image/#awesome-easy-progressive-css3-way](https://css-tricks.com/perfect-full-page-background-image/#awesome-easy-progressive-css3-way))

- flex-flow combines flex-direction and flex-wrap. So it is basically a shorthand for those two.

```css
flex-flow: row-reverse wrap;
```

- justify-content
    - space evenly: |—1—2—3—|
    - space around: |-1—2—3-|
    - space between: |1—2—3|

- align-items: for all the rows in the flexbox (when the flex direction default ie. row)
- align-content: for each row in the flexbox .So it only comes into play when there are multiple rows

- flex-grow by default is 0. Takes up available space

```css
flex-grow: x 
/*where x is the number of times that particulat item is wider than the rest
```

- flex-shrink by default is 1

- flex-basis: default is auto ( based on the content that is inside). Flex basis looks at the main axis. The difference between setting regular width and flex basis becomes clear when we introduce a media query and change the flex-direction in it.

Default align items for flex is stretch

- Flex shorthand

```css
flex: growvalue shrinkvalue basisvalue;
/*default being*/
flex: 0 1 auto;

/*another example */
flex : 1 1 0;
/* Here the flex gorw is 0, flex shrink is 1, flex basis is auto */

flex: 1 ;
/* here it sets gorw to 1 and basis to 0 */

flex: 200px;
/* sets flex basis to 400px */

```

- align-self: for aligning only that item relative to its parent flexbox

- Margin works differently in flexboxes. In regular boxes, margin-top and bottom become 0 when we give `margin:auto` . However, this is not the case in flexboxes and we can vertically center and horizontally center something using `margin:auto`. ironically, margin-top aligns something to the bottom lmao.
- Align-items works on the cross-axis
- When dealing with images in flex-basis, make sure to set min-width and min-height as 0 because otherwise it can create bugs

## Grid

- Flexbox lags behind when we have to work on both the rows and the columns. This is where grid comes in
- By default grid items turn into a row
- Remember that numbering of columns and rows starts from the border. negative numbering also works

```css
grid-template-columns: 120px, 23px, 23px;
grid-template-rows: 120px, 120px, 120px;

/*shorthand*/

	grid-template: 100px 400px / 250px 250px;
/*rows (height) / columns (width)*/

grid-column-start: 1;
grid-column-end: 2;
grid-row-start: 1;
grid-row-end: 3;

/*shorthand */
grid-row: start/end;
grid-column: start/end;
```

- We can also write how many lines we want to stretch the element to like so:

```css
grid-column: 1/ span 2;

/* this column starts from 1 and the nspans for two more lines meaning that it ends at 
line 3
*/
```

- auto for making the size of a column/row according to the content that is inside, not explicitly. This is the default value as well! It `stretch`es the cell by default and we can use `align-items` to change this behaviour
- Instead of flex-start in flexbox, here it’s just start

- justify-items: by default horizontal alignment
- align-items: by default vertical alignment
- width and height of the elements inside will go according to the size of the cell, not of the parent

- grid-gap

```css
grid-column-gap: 24px;
grid-row-gap: 23px;
grid-gap: 23px, 24px;
```

- grid-template-areas
    
    for naming the areas
    

```css
/*example*/
display:grid;
grid-template-columns: 200px 200px 350px;
grid-template-rows: 50px 200px;

grid-template-areas: "header header header"
											"sidebar content content";
 
.main{
grid-area:content;
}
```

- . or …….. for creating empty cells in grid-template-areas

- minmax( minimum, maximum)

- fr unit: fraction of the available space
- It can’t be as the minimum size of minmax though

- repeat for making columns/rows of the same size

```css
grid-template-columns : repeat(4, 300px);
```

- auto-fill and auto-fit: auto-fill will keep creating new empty columns whereas auto-fit will distribute the remaining space
- place-content: center
    
    for centering things vertically and horizontally in a grid
    

- padding-block is a new property that allows us to specify top and bottom padding in one go

- Indent in form text can be done using the property:

```css
text-indent: 23px;
```

- #222222 is the perfect dark background (best black)
- outer border = padding + inner border
-
