# FreeCodeCamp Responsive Web Design

## HTML Notes

- Commenting OUT (removes the coded text so it is no longer available. Like this:
    ```html
    <!--<h1>Hello World</h1>-->
    ```

- HTML5 Elements
    - Using the appropriate tag is important for SEO and accessibility. 
    - They include: header, footer, nav, video, article, section and others.
    - The ```main``` tag helps search engines know the main content of your page. It can wrap larger segments with other tags. For more info and benefits, go to the applied accessibility section.
- Adding Images to your website. 
    - Use the ```img``` element and point to a specific image URL with the src attribute. 
    - Ex: ```<img src="https://www.your-image-source.com/your-image.jpg">```
    - All ```img``` elements must have an alt attribute. Put it after the ```.jpg” alt=”picture description”>```
- Forms (HTML Forms W3 Schools)
    -```<form>``` Element: You must use the ```<form>``` text fields like ```radio```
    - Inside the opening ```<form>``` attribute you need to add an ```action```, ```target```, and ```method```.
        - ```action```: this attribute defines what will be done when the page is submitted. If it is omitted the action is set to the current page. 
        - ```target```: this attribute specifies if the submitted result will open in a new browser tab, a fram, or in the current window.
        The default value is “_self” which means the form will be submitted in the current window. To make the form result open in a new browser tab, use the value ```_blank```
    - ```<input>``` Element: input is the most important, that’s how people answer the form! There are several types:
        - ```<input type="text">``` Text: defines one-line text input field
        - ```<input type="radio">``` Radio: Defines a radio button 
        - ```<input type="submit">``` Submit: Defines a submit button. Submit: You’ll need a submit button to finish a form!
        ```<input type="submit" value="Submit">```
        - Required Field: Require a field by putting required at the end of the ```<input>``` area. 
        ```<input type="text" required>```

##Basic CSS
###Introduction

- CSS stands for Cascading Style Sheets, tells the browser how to display the text and other content that you write in HTML.
- All CSS is case-sensitive. CSS has been adopted by all major browsers and allows you to control:
    - Color
    - fonts
    - positioning
    - spacing
    - sizing
    - decorations
    - transitions
- Applying Style: There are three main ways to apply styles: 
    1. Directly to HTML elements: with the style attribute. Reg:  <h2> CatPhotoApp </h2>
    2. Inline style: ```<h2 style=”color:blue;”>CatPhotoApp</h2>```
        - You can place CSS rules within a style in an HTML document.
        - At the top of the code  place a style block like this
      ```html 
        <style>
        h2 {color: red;}
        </style>
      ```

- Finally (and most common) is an external style sheet, while referencing the sheet in the HTML document. 
  - Pros for this: keeps HTML and CSS documents separate, also improves readability of your code. 
  - The idea behind CSS is that you use a selector to target an HTML element in the DOM (Document Object Model) and then apply a variety of attributes to that element to change the way it is displayed on the page. 

- Changing colors:
    - Insert into the element after the name (e.g. regular <h2> CatPhotoApp </h2> becomes <h2 style=”color:blue;”>CatPhotoApp</h2> (this is an example of styling with inline CSS)

- Use CSS Selectors to Style Elements:
  - There are hundreds of properties that you can use to change the way an element looks on your page. 
  - At the top of the code  place a style block like this:
  ```html
  <style>
  h2 {color: red;}
  </style>
  ```

- Use CSS Class to Style and Element
  - Create a class by declaring it with a name and defining what it does like this:
    - Declare it:
    ```html
    <style>
      .blue-text {
        color: blue;
      }
    </style>
    ```
    - Then apply it like so:
    ```html 
    <h2 class=”blue-text”>CatPhotoApp</h2>
    ```
    - Note that in the declaration the class name starts with a period, but in the application you don’t use a period.

- Style multiple elements with a CSS class
  - Simply add the ```class=”class-title”``` inside the opening ```< >```

- Change the font size of an element
  - Font size is controlled by the font-size CSS property like this:
  ```css
  h1 {
    font-size: 30px;
  }
  ```
  Inside the same ```<style>``` tag

- Fonts
  - Set the Font Family of an Element
  - You can set a font family by using the font-family property.
  - For example:
  ```css  
  h2 {
    font-family: sans-serif;
  }
  ```

- Import a Google Font
  - Google Fonts is a free library of web fonts you can use by referencing the fonts URL.
  - Start by adding the link above the opening style element like so:
  ```html
  <link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css"> 
  ```
  - This references the URL of the font, gives it a family name and where it is a related, and the type. If you are importing a Google font, it will give you all of this generated in its link. 
  - Family names are case-sensitive and need to be wrapped in quotes. 
  - Apply the font to specific elements by then adding the font name in the style sheet like so:
  ```css
  h2 {
    font-family: Lobster;
  }```
- Degrading Fonts or Font Family deferrals 
  - In the event a font may not be available, you can specify the font that a site should defer to. These are called “generic fonts.” They are not case-sensitive because they are CSS keywords.
  ```Monospace```, ```serif```, and ```sans-serif``` are examples of these.
  - You add a degrading font after a common of the font you are wanting to upload like this:
  ```css
  p {
    font-family: Helvetica, sans-serif;
  }
  ```

- Sizing Images
  - CSS has a property called width that controls just that, the width. You’ll use px to specify the width.
  - For example, creating a CSS class called larger-image that gave HTML Elements a width of 500 pixels you’d write this:
  ```html 
  <style>
    .larger-image {
      width: 500px;
    }
  </style>
  ```
  - When you when you use the class put it at the end of the href src URL like so:
  ```html 
  <a href="#"> <img src="https://bit.ly/fcc-relaxing-cat" class="smaller-image" alt="A cute orange cat lying on its back." ></a>
  ```

- Borders around Elements
  - You can add borders around elements, and there are three properties: style, color, and width.
  - Example style declaration:
  ```html 
  <style>
  .thin-red-border {
    border-color: red;
    border-width: 5px;
    border-style: solid;
  }
  </style>
  ```
  - Reminder: when applying multiple classes, put them in the same “ “ and separate with a space like so:
  ```html
  <a href="#"><img class="smaller-image thick-green-border" src="https://bit.ly/fcc-relaxing-cat" alt="A cute orange cat lying on its back." ></a>
  ```
  - You can also, round the corners of an image with a CSS property called: ```border-radius```. This goes inside the stylesheet
  - It can either go with the image width definition or the border definition like this:
  ```css
  .thick-green-border {
   border-color: green;
   border-width: 10px;
   border-style: solid;
   border-radius: 10px;
  }```

- Make an image circular with border-radius by using a percentage. 
  - Same as above, with a small exception: ```border-radius: 50%;```
- Give a background color to a div element
  - Set an element’s background color with the ```background-color``` property.
- For example:
  ```css
  .green-background {
    background-color: green;
  }
  ```

- Set the id of an element
  - In addition to classes, each HTML element can also have an id attribute. 
  - Benefits of id attributes.
  - Use an id to style a single element and later you’ll find that you can use them to select and modify specific elements with JavaScript.
  - *id attributes should be unique.* Browsers won’t enforce this, but it is a widely agreed upon best practice. Tl:dr don’t give more than one element the same id attribute. 
  - Example: ```<h2 id="cat-photo-app">```.

- Use an id attribute to style an element.
  - Cool thing about id attributes is that you can style them, like classes.
  - However an id is not reusable and should only be applied to on element. An id also has a higher specificity (importance) than a class so if both are applied to the same element and have conflicting styles, the id attribute will be applied. 
  - *Tl:dr id attribute override classes that also apply.*
  - Classes are always references with the ```.``` before it, an id attribute similarly always has a ```#```

- Padding, Margins and Borders
  - Padding: controls the amount of space between the elements content and its border.
  - You can control four individual sides padding with the padding-top, padding-right, padding-bottom, and padding-left properties. You can also control it by using one line called Clockwise Notation and placing the four numbers clock-wise (top, right, bottom, left) like this: ```padding: 10px 20px 10px 20px;```
  - Margin controls the amount of space between an element’s border and the surrounding elements. If you set the element’s margin to a negative value the element will grow larger. You can control the margin on all four individual sides with the margin-top, margin-right, margin-bottom, and margin-left properties. The same Clockwise Notation works with margin as with padding

- Use attribute selectors to style elements
  - We’ve been using id or class attributes to style elements. However there are other ways to style things. Like ```[attr=value]``` to style a checkbox.
  ``` css
  [type='checkbox'] {
      margin-top: 10px;
      margin-bottom: 15px;
    }
  ```

- *Style*
- Absolute vs Relative Units
  - Absolute: px = pixels, in = inches, mm = millimeters
  - Relative: em or rem are relative to another length value. For example if you use it to set the font-size property itself, it’s relative to the parent’s font-size.

- Style the HTML Body Element
  - Every HTML page has a ```body``` element. You can style the whole thing with by using it like this:
  ```css
  body {
    background-color: black;
    Font-family: helvetica;
  }
  ```

- Prioritize One Style Over Another
  - A class can override a body style
  - If more than one class applies to an element, then the one declared the furthest down in the style sheet will apply, no matter what the order of the class in the element itself.
  - For example:

  ```html
  <style>
  .pink-text {
    color: pink;
  }
  .blue-text {
    color: blue;
  }
  </style>
  <h1 class="blue-text pink-text">Hello World!</h1>
  ```
  - This will always come out as BLUE because the .blue-text comes second in the style sheet. 
  HOWEVER an id attribute will supercede a class. Even if they are all applied in the same line. 
  Next an inline style will ultimately override everything.
  ```html
  <h1 style="color: green">.
  ```
  - You can add ```!important``` which will override all of this.
  - This is useful because sometimes you’ll use exterior CSS libraries which might override your CSS. You’ll want to make sure something happens, so use !important. It will look like this:
  ```css
  .pink-text {
    color: pink !important;
  }
  ```

- Colors
  - Using Hex Codes for Specific Colors
    - Use Hex codes for any specific color anywhere that you’ve previously written a color.
    - ``#000000`` ← Black
  - You can also use “Abbreviated Hex Code”
    - This limits one digit to R, G, and B. So for Red the hex code is #FF0000 but the abbreviated is #F00 which is the exact same color. The only difference is less code and less options instead of 16million hex colors there are only 4000 abbreviated hex codes.
- RGB Values to Color Elements
  - You can also use RGB which instead of mixing specifies a brightness of R G and B. It would look like this in the style sheet:
  ```css
  body {
    background-color: rgb(255, 165, 0);
  }
  ```

- Use CSS Variables
  - ...to change several elements at once
  - CSS Variables allow you to change many CSS style properties at once
  - Create a CSS Variable
    - Give it a name and two dashes in front of it and assign it a value like this: ```--penguin-skin: gray;```
    Doing this will create a variable named penguin skin and give it the value gray. 
  - Use a Custom CSS Variable
  - Apply the variable by calling the name that you gave it in the example above you’d put ```var(--penguin-skin)```

- Attach a fallback value to a CSS Variable
  - Works similarly to the fallback on fonts, using the same example as before it would. ```background: var(--penguin-skin, black);```
  - Specifically this will be helpful in debugging, by putting a weird value in the fallback case.

- Cascading CSS variables
  - When a variable is created, it becomes available inside the element in which you create it, but it is also available in any elements nested within it. This is called “cascading.” 
  - Because of this cascading principle, CSS variables are often defined in the ```:root``` element.
  - The ```:root``` element is like a container for the entire HTML document. In the same way an html element a container for the body element.
  - By creating variables in ```:root```, they will be available throughout the whole web page.
  - The same principles of prioritization used in style apply here as well. You can override the prioritization by adding lower in the code.

- Using a media query: (Mozilla Devs Media Queries)
  - Using CSS variables can simplify media queries. For example if your screen is smaller or larger than your media query breakpoint, you can change the value of a variable and it will apply its style whenever its used.
  - Basically this can apply a specific sizing restraints when needed.

## Applied Visual Design
HTML gives structure and semantics to a page’s content. CSSS controls the layout and appearance of it. 
Text-align
Text is a large part of websites so you need to know how to align it with the text-align property. 
text-align: justify; Justify causes all the lines of the text except the last line to meet the left and right edges of the line box. 
text-align: center; Centers the text
text-align: right; Right aligns the text.
text-align: left; (default) left aligns the text. 
Width and Height Property
You can specify the width of an element using the width property in CSS. Values can be given in relative length units (like em), as  absolute units (like px), or as a percentage of its containing parent element. 
img {
  width: 220px;
} .
The height property works basically the same way. 
Make Text bold
To make a specific text bold you use the strong tag. 
...students at <strong> Stanford  University</strong>.</p>
Would look like this: “… students at Stanford University.”
To apply to a whole element, declare it in the style sheet with 
font-weight: bold;.
Underline text
Works similarly to bold. Use the u tag.  
Can also be applied to an entire element with the declaration: 
text-decoration: underline;. 
Tip: avoid using the u tag when it could be confused with a link. 
Italicize text
Like bold and underline. 
Use the em tag for italicizing
Or apply to an element like this: 
font-style: italic;.
Strikethrough text
Just like bold, underline, and italicize
Use the del tag
For an element: 
text-decoration: line-through;.
Create a horizontal line 
Use the hr tag to add a horizontal line across the width of its containing element. This can be used for many purposes like changing topic or groups of content. 
hr Is a self-closing tag so it doesn’t need a separate closing tag. 
Looks like this: 
<p> This is a sentence </p>
<hr>
<h2> more text </h2>
Adjust the background color Property of Text
Instead of adjusting your overall background or the color of the text to make the foreground easily readable, you can add a background-color to the element holding the element holding the text you want to emphasize. 
You can also use rgba() to do this, the a stands for the alpha/level of opacity. 
rgba stands for:
  r = red
  g = green
  b = blue
  a = alpha/level of opacity
RGB ranges 0-255
Alpha ranges from 0-1 with zero being fully transparent and one being opaque. 
This is great to use in order to make your text stand out better, especially when you want text of a specific color. 
Example: background-color: rgba(45, 45, 45, 0.1);
.Adjust the size of a header vs paragraph tag. 
There are six header tags (h1 through h6). They should generally all be larger than your paragraph text size. They are called headers because they show the level of importance of everything on your page.
Use the font-size element to adjust the size of the text in an element. 
Add a box-shadow to a card like element
The box-shadow property applies one or more shadows to an element.
box-shadow takes values for offset-x (horizontal) offset-y (vertical), blur-radius, spread-radius,  and a color value. IN that order. Blur-radius and spread-radius values are optional. 
Example:
box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
Decrease the opacity of an element
The opacity property in CSS is used to adjust the transparency of an item. 
1 = opaque, 0 is transparent. .5 is halfway. 
Example 
 .links {
   text-align: left;
   color: black;
   opacity: .7;
}


Use Text transform: to change a text a to a different format 
lowercase
"transform me"
uppercase
"TRANSFORM ME"
capitalize
"Transform Me"
initial
Use the default value
inherit
Use the text-transformvalue from the parent element
none
Default: Use the original text

Set the font size for multiple heading elements. 
The font-size property is used to specify how large the text is in a given element. 
H3 {
     Font-size: 34px;
}
Font weight, choose the weight of the text. 
Declare it like this: 
H1 {
     Font-weight: 800; 
}
Set the Line Height of Paragraphs
CSS offers the line-height property that changes the height of each line in a block of text. 
Declare it like this: 
H1 {
     line-height: 25px;
}
Adjust the Hover State of an Anchor Tag
A hover class is a type of pseudo-class. A  pseudo-class is a keyword that can be added to selectors, in order to select a specific state of element. 
CSS Box Model
CSS treats each HTML element as its own box, this is called CSS Box Model. Block-level items automatically start on a new line (like headings, paragraphs, and divs) while inline items sit within surrounding content (like images or spans). The default layout of elements in this way is called normal flow of a document, but CSS offers the position property to override it. 
When the position of an element is set to relative, it allows you to specify how CSS should move it relative to its current position in the normal flow of the page. It pairs with the CSS offset properties of left or right, and top or bottom. These say how many pixels, percentages, or ems to move the item away from where it is normally positioned. 
position Properties
Change an Element’s Relative Position
CSS treats each element as its own box, this is referred to as the CSS Box Model. Block-level items start on a new line (like headings and paragraphs) while inline items (like images or spans) sit within the surrounding content. The default setting is called normal flow, but CSS offers the ability to override it. 
When the position is set to relative, it allows you to specify how CSS should move it relative to its current position in the normal flow of the page. It also pairs with the offset properties of left/right and top/bottom. This can say how many pixels, percentages, or ems to move the item away from where it is normally positioned. 
Example: 
p {
  position: relative;
  bottom: 10px;
}
Changing an element’s position to relative does not remove it from the normal flow; other elements around it will still behave as if that item were in it’s default position. 
You can do this to move items where you would rather they be. 
Lock an element to its parent with Absolute positioning. 
The absolute property locks an element in place relative to its parent container. Unlike the relative position, this removes the element from the normal flow of the document so surrounding items ignore it. The CSS offset properties (top/bottom/left/right) are used to adjust the position. 
One nuance, with absolute positioning is that it will be locked relative to its closest positioned ancestor. If you forget to add a position rule to the parent item, the browser will keep looking up the chain and ultimately default to the body tag. This is typically done with position: relative;.
Fixed Positioning 
CSS offers another layout scheme called fixed position. Which is a type of absolute positioning that locks an element relative to the browser window. It uses the same CSS offset properties as absolute positioning, it also removes the element from the normal flow of the document. 
The big difference between fixed and absolute is that the fixed element won’t move when the user scrolls. 
Push elements left or right with the float property
float is actually not related to position, but instead the float property removes elements from the normal flow of the document and are either pushed to the right or left of their containing parent element. It is commonly used with the width property to specify how much horizontal space the floated element requires. 
Change the position of overlapping elements with the z-index property. 
When elements are positioned to overlap, the element coming later in the HTML markup will, by default, appear on the TOP of the other elements. However, the z-index property can specify the order of how elements are stacked on top of one another. It must be an integer, and higher values for the z-index property of an element move it higher in the stack than those with lower values. 
Center an element Horizontally using the margin property. 
Another positioning technique is to center a block element horizontally. One way to do this is to set its margin to a value of auto.
This method works for images too. Images are inline elements by default, but can be changed to block elements if you set the display property to block. 
Adjust the Hue/Saturation/Lightness of a Color
Colors have several characteristics including: hue, saturation, and lightness. The hsl() property is an alternative way to pick a color by directly stating these characteristics. 
Hue: is what people generally think of as “color.” if you think of color as a spectrum, it’s hue is where it lies along that spectrum, only instead of a straight line, it is a 360˚ circle. Values 0-360.
Saturation: is the amount of gray in a coor. Fully saturated = NO gray. Minimally is almost completely gray. It is given in a percentage 0-100%. 
Lightness is the amount of white or black in a color. A percentage ranging from 0% (black) to 100% (white), where 50% is the normal color. 
Adjust the tone of a color
The hsl() option in CSS also makes it easy to adjust the tone of a color. Mixing white will make a tint; mixing black will make a shade. Alternatively a tone is produced by adding gray or by both tinting and shading. This is useful if you have a specific color but want different variations on it. 
Create a Gradual CSS Linear Gradient
Using the background property, linear-gradient() function allows you to apply a gradient. 
Here’s the general usage
background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);
Doesn’t have to be a hex value. 
Can also use a repeating-linear-gradient() to apply a repeating gradient, but you also specify the length of each color in the gradient. Like so:
background: repeating-linear-gradient(     
     90deg,
     yellow 0px,
     blue 40px,
     green 40px,
     red 80px
);.
Background: use the background property to add a background. You can also add a URL to make a background.background: url(https://something.com); .
Use Transform scale to change the size of an element. Just add it to an element and the amount of times you want to change it. Like this:
p {
  transform:scale(2);
}
You can also use a cover. So for the last one p:hover pseudo-class
p:hover {
     transform: scale(1.1);
}
To skew, you have to put it on an axis with skewX or skewY:
p:  {
    skewX(32deg);
}
To rotate you use 
p {
     Transform: rotate(#deg);
}
Create a Graphic with CSS
This makes a crescent-moon shape. 
.center
{
 position: absolute;
 margin: auto;
 top: 0;
 right: 0;
 bottom: 0;
 left: 0;
 width: 100px;
 height: 100px;
 background-color: transparent;
 border-radius: 50%;
 box-shadow: 25px 10px 0px 0px blue;
}
Reminder: box-shadow takes: offset-x, offset-y, blur-radius, and spread-radius. 
Lots of times you’ll use ::before and ::after (which are pseudo-classes) to place things before/after a predefined object. 
How to draw a heart using ::before and ::after 
Animation
Using @keyframes for animation
There are 8 animation properties in total. 
animation-name sets the name of the animation which is later used by @keyframes to tell CSS which rules go with which animations. 
animation-duration sets the length of time for an animation. 
@keyframes Is how to specify exactly what happens within an animation over the duration. 
#anim {
  animation-name: colorful;
  animation-duration: 3s;
  animation-fill-mode: forwards;
}
@keyframes colorful {
  0% {
    background-color: blue;
  }
  100% {
    background-color: yellow;
  }
}

@keyframes also has fill modes that allow the animation to have a final stopping place and not revert. use : animation-fill-mode: forwards;to do this.
Position animation: when elements have a specified position, like fixed or relative, the CSS offset properties (right, left, top, and bottom) can be used in animation rules to create movement. 
@keyframes colorful {
  0% {
    left: 0px;
  }
  100% {
    Left: 50px;
  }
}
Opacity animation: using the opacity property just like the offset property  you can animate an element’s opacity. 
 @keyframes fade {
   50% {
     left: 60%;
     opacity: .1;
   }
 }
Iteration counts: another animation property is the animation-iteration-count which allows you to control how many times an animation occurs. It can also be set to infinite. 
Variable rates: changing the % of the @keyframes allows you to change the rate that two similar objects animate. You can also change their animation-duration. Below I’ve bolded the two ways:
@keyframes twinkle {
    20% {
      transform: scale(0.5);
      opacity: 0.5;
    }
  .star-1 {
    margin-top: 15%; 
    margin-left: 60%;
    animation-duration: 1s;
    animation-name: twinkle;
  }
The animation-timing-function property controls how quickly an animated element changes over the duration of the animation. 
ease: starts slow and speeds up in the middle, slowing down at the end. 
ease-out: starts quick and slows down.
ease-in: starts slow and speeds up. 
linear: constant speed for the  animation. 
Looks like: animation-timing-function: ease-out;.
Bezier Curves: these use the cubic-bezier function. The shape of the curve represents how the animation plays out. It uses a 1 by 1 coordinate system. The x-axis is the duration of the animation (aka time) and the y-axis is the change. The first (p0) and last (p3) points are set for you (0.0 and 1,1). You set the x and y values for the other two points. So you declare the other points by writing it as (x1, y1, x2, y2) in the declaration. 
Here’s how it looks: animation-timing-function: cubic-bezier(0.25, 0.25, 0.75, 0.75);
This is the same as using animation-timing-function: linear;.
X-axis only accepts values 0-1, but y-axis can accept larger values. 

## Applied Accessibility

- General Principles of Applied Accessibility
  - Well-organized code that uses appropriate markup
  - Ensure text alternatives exist for non-text and visual content
  - Create an easily-navigated page that’s keyboard friendly
  - W3’s Web Content Accessibility Guidelines (WCAG): These are the standards for Web Accessibility

- Add a text alternative to images for impaired accessibility
  - Alt text is also useful for SEO in addition to helping the visually impaired.
  ```html
  <img src=”link” alt=”description of text”>
  ```
  - Sometimes the alt text needs to be left blank. But only if the photo is described elsewhere OR only there for decoration.
  - Background images don’t count, as they are only decorations, and have CSS rules applied to them. 
  - If the CSS needs to be blank, it still has to be included but its <img src=”link” alt=””>

- Heading Elements:
  - They EACH correspond to a level of heading or sub-heading. Don’t just choose a header type because it looks good in the browser. Pick the appropriate one and edit its CSS.
  - H1: there should only ever be one H1 element in your page.

- Specific Elements and Tags
  - Main Element: is used to wrap the “main” content of the page. Its meant to be for the central topic of the page, and NOT items that are repeated, like navbars or footers. And it can also be used specifically with assistive technology that can “jump to main content”
  - Article Element: useful for blogs, forums, and news articles. You can determine by asking: if you removed all the surrounding context would that content still make sense. Groups independent, self-contained content.
  - ```<div>``` groups content
  - ```<section>``` - groups related content. 
  - ```<header>``` Tag: it is used to wrap introductory information or navigation links for its parent tag. It words well with content repeated on multiple pages.
    - Note: ```<header>``` is different than ```<head>```. ```<head>``` is for title, meta info, etc…
  - ```<nav>``` Element: This tag is meant to wrap around the main navigation links in your page.
  - ```<footer>``` Element: primarily used to contain copyright info or links to related docs that normally sit at the bottom of the page.
  - ```<audio>``` Element: used to add audio. The controls attribute brings up the default play/pause controls.
    - Example:
    ```html
    <audio controls> <source src=”link” type=”audio/file-type” </audio>
    ```
- Figure Element: ```figure``` and ```figcaption``` when used together, these items wrap a visual representation (like an image, diagram or chart) along with its caption.
- Label tag: the ```label``` tag wraps text for a specific form control item, usually the name or label for a choice. This ties meaning to the item and makes the form more readable. The for attribute on a label tag explicitly associates that label with the form control and is used by screen readers. The value of the for attribute must be the same as the value of the id attribute of the form control.
- Fieldset and Legend tags:
  - ```<fieldset>``` is a wrapper for radio buttons. It uses the ```<legend>``` tag to provide a description for the grouping. Neither of these are necessary for self-explanatory options.
- Date input type: much like the text and submit input types, the ```type=”date”``` available in HTML5 allows for a date picker.
  - ```datetime``` attribute: put it inside the opening ```<time>``` tag with ```datetime=”20xx-MM-DD”```
  - Custom CSS for only Screen Readers: so far, none of the applied accessibility challenges have used CSS, that’s just to show that you need good logical tags and formatting. Here’s an example:
```css
  .sr-only {
    position: absolute;
    left: -10000px;
    width: 1px;
    height: 1px;
    top: auto;
    overflow: hidden;
  }
  ```
- Improve Readiblity with High Contrast Text
  - WCAG recommends at least a 4.5 to 1 contrast ration for normal text. 1:1 is no contrast which is the same color. 21:1 is white against black whic is the most contrast.
- Avoid Colorblindness issues with contrast
  - The same 4.5:1 rule applies to color. 
- Give Links meaning by using descriptive link text.
  - This is useful, because "click here" buttons have no meaning for visually impaired, so instead describe what the click will do. "click here for information about cats"
- ```accesskey``` attribute:
  - this attribute allows for a shortcut key to be applied to any HTML element, but it's particularly useful for interative ones like links and buttons.
  - declare like so:
  ```html
  <a accesskey="a" href="">Learn about Andy!</a>
  ```
- Use ```tabindex``` to add keyboard focus to an element.
  - The ```tabindex``` has three distinct functions relating to an elements keyboard focus. For example, if you have a form, you may want to force the user to focus on the instructions first by adding a ```<p tabindex="0">Instructions:...</p>``` Instead of allowing the user to go straight to the form. You can also continue on to force the user to a specific set of places by incrementing the ```tabindex="#"``` this overides the HTML source.


## Responsive Web Design Principles

- Media Queries: change the presentation of content based on different viewport sizes. The viewport is the user’s visible area of a web page and is different depending on the device used to access the site. 
- Media Queries consist of: a media type, and if that media type matches the type of device the document is displayed on, the styles are applied. You can have as many selectors and styles inside your media query as you want. 
  - Looks like this: 
    ``` html
      <style>
            P {
            Font-size: 20px;
            }

        @media (max-width: 800px) {
            P {
                Font-size: 10px;
            }
        }
        ```
- This would change the font size of the <p> element if the max-width of the viewport is 800-px or less.
- Responsive Images:
  - Absolute width: ```img { width: 720px; }```
  - Responsive:
    ```css
    img {
        Max-width: 100%;
        Display: block;
        Height: auto;
    }
    ```
- Retina Images for Hi-Res Displays:
  - The simplest way to make your images appear “hi-res” or “retina” is to define their width and height values as only half what the original file is.
- Make Typography Responsive:
  - Instead of using em or px to size text. You can use viewport units for responsive typography. These are relative units, like percentages.
  - There are 4 types:
    - ``vw``: is relative to the viewport’s WIDTH
    - ``vh``: is relative to the viewport’s HEIGHT
    - ```vmin```: is relative to the viewport’s SMALLER DIMENSION
    - ```vmax```: is relative to the viewport’s LARGER DIMENSION

## CSS Flexbox

- Website UI has two components:
  1. Visual Elements: colors, fonts, elements.
  2. Placement or positioning of those elements.
  - In Responsive Web Design, UI must accommodate many different browsers and devices.
- Flexbox was introduced in CSS3 to create page layouts for a dynamic UI. It is a layout mode that arranges elements in a predictable way for different screensizes.
- Applying ```display: flex;``` to an element allows you to use other flex properties to build a responsive page.
- Adding ```display: flex;``` turns it into a flex container. This makes it possible to align any child element into rows or columns with ```flex: direction;``` then adding either ```row``` or ```column```. You can also add ```row-reverse``` or ```column-reverse```.
- ```justify-content: ``` is a way to organize items in a flex-container.
  - ```center```: centers the items together.
  - ```flex-start```: aligns the items to start of the container.
  - ```flex-end```: aligns items to the end container. For a row this would be to the right, for a column it would push to the bottom.
  - ```space-between```: aligns items to the center of the main axis.
  - ```space-around```: similar to space-between but the first and last items aren't locked to the edges the space is distributed around all the items equally.
- ```align-items:``` is a property is similar to ```justify-content:```, however instead of aligning on the main axis, it aligns on the *cross-axis*. Values include:
  - ```flex-start```: aligns items to the start of the container.
  - ```flex-end```: aligns items to the end of the flex container.
  - ```center```: aligns items to the center.
  - ```stretch```: stretch the items to fill the flex container.
  - ```baseline```: aligns items to their baselines. Baseline is a text concept, think of it as the line that the letters sit on.
- ```flex-wrap```: By default a flex container will fit all items together, but the ```flex-wrap``` property allows you to wrap items. Options for it include:
  - ```nowrap```: this is default, and does not wrap items.
  - ```wrap```: wraps items from left-to-right (row) or top-to-bottom (column)
  - ```wrap-reverse```: wraps items opposite to ```wrap```
- ```flex-shrink```: is a property that applies to flex items. It allows you to alter them, and choose how much space they take up.
- ```flex-grow```: works opposite to ```flex-shrink```, and makes items larger.
- ```flex-basis```: specifies the initial size of the item before CSS makes adjustments with ```flex-shrink``` or ```flex-grow```. It uses normal ```px```, ```em```, ```%```, etc values. You can also use ```auto``` which sizes items based on content.
- You can use a shorcut to set several flex properties at once. Using a simple ```flex``` property. It goes in order of ```flex-grow```, ```flex-shrink```, ```flex-basis```. For example these two CSS declarations are the same:
  ```css
  flex: 0 1 auto;
  ```
  ```css
  flex-grow: 0;
  flex-shrink: 1;
  flex-basis auto;
  ```
- the ```order``` property allows you to specify the order of flex items. Otherwise it defaults to where they show up in the HTML. It accepts positive integers as values.
- ```align-self``` is a property that allows you to adjust each item individually. It accepts all the same values as ```align-items``` and will override any value from ```align-items```



## CSS Grid

- First Grid
  - Setting the ```display: grid;``` of any element will put it into the grid. This gives you the ability to use all the other properties associated with ```CSS grid```
  - Parent elements are called the ```container``` and the child elements are called ```items```.
- Grid Template Columns
  - To add columns to the grid use ```grid-template-columns``` property. like this:
  ``` css
  .container {
    display: grid;
    grid-template-columns: 100px 100px 50px;
  }
  ```
- Rows with ```grid-template-rows```
  - this tells how large the rows should be. For example:
    ``` css
  .container {
    display: grid;
    grid-template-rows: 50px 50px 50px;
  } ```
- More flexible rows/column sizing
  - There are a few different ones that help set the size:
    - ```fr```: sets the row/column to a fraction of the available space.
    - ```auto```: sets the row/column to a natural height/width.
    - ```%```: adjusts the row/column to the % of the container.
    - all of these can be chained together for any combination of sizing you need. Like so:
    ``` css
    .container {
      grid-template-columns: auto 50px 10% 2fr 1fr;
    } 
    ```
    - this would create 5 columns the first being sized to its content, the next being 50 pixels, the next being 10% of the window and the final two being divided between each other with 2 parts given to the first and the final remaining part to the last section.
- Creating gaps
  - use ```grid-column-gap: 10px;``` to put a gap between every column. This can be any amount.
  - ```grid-row-gap``` works the same way, but for rows.
  - ```grid-gap``` is shorthand and can be used to put gaps between both rows and columns. If it has one value it will put a gap between both, if there are two values the first will apply a row gap and the second a column gap.
- Controlling Spacing:
  - use ```grid-column``` to tell an item how much space it should take up. For example: 
  ``` css
  .item5 {
    background: green;
    grid-column: 2 / 4;
  }
  ```
  - this would allow the item to take up the last two columns instead of one, in a 3x3 grid.
  - ```grid-row``` works the same but deals with vertical space.
- Horizontal Alignment with ```justify-self```:
  - In CSS Grid, the content of each item is contained in a box known as a *cell*.
  - You can align the content's position within the cell **horizontally** with ```justify-self```
  - There are several properties that can be applied to a cell.
    - ```stretch``` (default value) makes the content fill the width of the cell.
    - ```start```: aligns the content at the left of the cell.
    - ```center```: aligns the content in the middle of the cell.
    - ```end```: aligns the content at the right of the cell.
  - If you want to justify all the items in a container, use ```justify-items```. Works the same, but applies to all items in a given class. 
- Vertical Alignment with ```align-self```:
  - Works the same as ```justify-self``` accepts all the same values, simply applies the values vertically. 
  - Like ```justify-items```, ```align-items``` can apply all vertical alignment to ever property in a given class/container. It also accepts the same arugments as the others.
- Grid Template Areas:
  - To give yourself the ability to specifically designate where a cell fits in the grid. You can almost apply a class/id type to the template areas to make them clearer. For example:
  ```css
  .container {
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-template-areas:
      "header header header"
      "sidebar content content"
      "sidebar footer footer";
  }
  ```
  - From there you can just apply the specific ```div```'s classes using:
  ```css 
  .d1 {
    grid-area: footer;
  }
  ```
  - You can also use the syntax simlar to above when you don't have the template reference. Like so:
  ```css
  .d1 {
    grid-area: 3/2/4/4
  }
  ```
  - this would place the ```div``` with the class ```d1``` at the same position. 
- Reduce Repetition with the ```repeat``` Function:
  - If you are adding many rows/columns of the same size, it will be tedious to type them same 100 times. that's where ```repeat``` comes in. Use it like so:
  ```css
  .container {
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(100, 20px, 1fr);
  }
  ```
- Limit Item Size with ```minmax```:
  - use this when you are declaring your rows/columns in order to set the boundaries of their size. Like so:
  ```css
  .container {
    grid-template-columns: 100px minmax(50px, 200px);
  }
  ```
  - this creates two columns, one that is a static 100px, and another that will be between 50 and 200.
  - ```minmax``` can also be nested in a ```repeat```.
- The repeat function comes with a function called *auto-fill*. This lets you automatically insert as many rows or columns of the desired size, until the container is filled. You can create flexible layouts when combining ```auto-fill``` with ```minmax```. Like so:
```css
.container {
  grid-template-columns: repeat(auto-fill, minmax(60px, 1fr));
}
```
- ```auto-fit``` works almost identically to ```auto-fill```. The only difference is that when the container's size exceeds the size of all the items combined, ```auto-fill``` keeps inserting empty rows or columns while ```auto-fit``` collapses those empty rows/columns and stretches your items to fit the size of the container. If the container can't fit all the items on one row it will bump them down a row.
- using ```@media``` queries to responsively alter your layout.
  - create two layouts using media queries like so:
  ```css
  @media (max-width: 399px) {
    .container {
      grid-template-columns: auto 1fr;
      grid-template-rows: auto 1fr auto;
      grid-template-areas: 
        "header header"
        "advert advert"
        "content content"
        "footer footer";
    }
  }
  @media (min-width: 400px) {
    .container {
      /* assumes the grid-template-columns (and rows) have already been defined in the container class */
      grid-template-areas:
        "header header"
        "advert content"
        "advert content"
        "footer footer";
    }
  }
  ```
- Grids within Grids
  - all it takes is nesting a class that is in a grid and setting up the ```display: grid;``` and columns/rows appropriately. It would look like that.