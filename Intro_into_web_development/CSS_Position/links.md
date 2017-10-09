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

[Position](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4459839-dt-content-rid-7897449_2/xid-7897449_2)

# Post_session reading

1) [A Hands-On Guide to Mobile-First Responsive Design](https://www.uxpin.com/studio/blog/a-hands-on-guide-to-mobile-first-design/)

**Mobile-First = Content-First**

If your site is good on a mobile device, it translates better to all devices. More important, though, is that the mobile-first approach is also a content-first approach. Mobile has the most limitations, screen size and bandwidth to name a few, and so designing within these parameters force you to prioritize content ruthlessly.

The mobile-first approach organically leads to a design that’s more content-focused, and therefore user-focused. The heart of the site is content — that’s what the users are there for.

One caveat, though, is that mobile users sometimes require different content than desktop users. Device-specific content can be gauged by considering context — what, in a given situation and a given environment, will your user appreciate more. The best way to plan ahead for these is creating user scenarios.

Another advantage to mobile-first approach is that the small-screen breakpoints can better fit around the content. Again, the alternative is worse: having to squeeze an already plump design into a tiny framework. But with the mobile-first approach, the breakpoints develop naturally around content, so you don’t need any awkward edits.

**Checklist**

**1. Content Inventory** — This is a spreadsheet or equivalent document containing all the elements you want to include.

**2. Visual Hierarchy** — Prioritize the elements in the content inventory and determine how to display the most important elements prominently.

**3. Design with the smallest breakpoints and then scale up** — Build the mobile wireframe first, then use that as the model for larger breakpoints. Expand the screen until there’s too much white space

**4. Enlarge touch targets** — Fingers are much wider than pixel-precise mouse cursors, and so need larger elements on which to tap. At the time of this writing, Apple recommends 44 pixels square for touch targets. Give hyperlinks plenty of space, and slightly enlarge buttons, and make sure that

**5. Don’t count on hovers** — It almost goes without saying, but designers often rely on hover and mouseover effects in their interactive work. If you’re thinking mobile-friendly, don’t. There is no hover control for fingertips yet.

**6. Think “app”** — Mobile users are accustomed to motion and a modicum of control in their experience. Think about off-canvas navigation, expandible widgets, AJAX calls, or other elements on the screen with which users can interact without refreshing the page.

**7. Avoid large graphics** — Landscape photos and complex graphics don’t display well when your screen is only a few inches across. Cater to mobile users with images that are readable on handheld screens.

**8. Test it in a real device** — Nothing beats discovering for yourself how usable a website is (or isn’t). Step away from your desktop/laptop computer and load up your product on a real phone or tablet. Tap through pages. Is the site easy to navigate? Does it load in a timely fashion? Are the text and graphics easy to read?

2) [Learn to Code HTML & CSS](https://learn.shayhowe.com/html-css/)

Really helpful e-book
