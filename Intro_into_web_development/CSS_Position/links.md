[Lesson 3 plan](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4455013-dt-content-rid-7858971_2/courses/1718-CM6112/LessonPlanCSSLayout.pdf)

# Pre-session reading
[Learn CSS layout](http://learnlayout.com/)

**No Layout**
Having no layout whatsover is almost ok if all you want is one big column of content. However, if a user makes the browser window really wide, it gets kind of annoying to read: after each line your eyes have a long distance to travel right-to-left to the next line. Try resizing your browser to see what I mean!

**The display property**

display is CSS's most important property for controlling layout. Every element has a default display value depending on what type of element it is. The default for most elements is usually block or inline. A block element is often called a block-level element. An inline element is always just called an inline element.

block

<div>
div is the standard block-level element. A block-level element starts on a new line and stretches out to the left and right as far as it can. Other common block-level elements are p and form, and new in HTML5 are header, footer, section, and more.

</div>
inline

span is the standard inline element. An inline element can wrap some text inside a paragraph <span> like this </span> without disrupting the flow of that paragraph. The a element is the most common inline element, since you use them for links.

none

Another common display value is none. Some specialized elements such as script use this as their default. It is commonly used with JavaScript to hide and show elements without really deleting and recreating them.

This is different from visibility. Setting display to none will render the page as though the element does not exist. visibility: hidden; will hide the element, but the element will still take up the space it would if it was fully visible.

other display values

There are plenty of more exotic display values, such as list-item and table. Here is an exhaustive list. We'll discuss inline-block and flex later on.

extra credit

As I mentioned, every element has a default display type. However, you can always override this! Though it wouldn't make sense to make an inline div, you can use this to customize the display of elements that have particular semantics. A common example is making inline li elements for horizontal menus.

**Margin; auto**

#main {
  width: 600px;
  margin: 0 auto; 
}
<div id="main">
Setting the width of a block-level element will prevent it from stretching out to the edges of its container to the left and right. Then, you can set the left and right margins to auto to horizontally center that element within its container. The element will take up the width you specify, then the remaining space will be split evenly between the two margins.

The only problem occurs when the browser window is narrower than the width of your element. The browser resolves this by creating a horizontal scrollbar on the page. Let's improve the situation...

**max- width**

#main {
  max-width: 600px;
  margin: 0 auto; 
}
<div id="main">
Using max-width instead of width in this situation will improve the browser's handling of small windows. This is important when making a site usable on mobile. Resize this page to check it out!

By the way, max-width is supported by all major browsers including IE7+ so you shouldn't be afraid of using it.

# Slides

# Post_session reading
