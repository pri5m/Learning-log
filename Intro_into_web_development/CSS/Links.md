[Lesson Plan](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4447737-dt-content-rid-7822420_2/courses/1718-CM6112/CSS%20LessonPlan.pdf)

# Pre-session reading

1) [HTML.net](http://html.net/tutorials/css/lesson1.php)

CSS is an acronym for Cascading Style Sheets.

CSS is a style language that defines layout of HTML documents. For example, CSS covers fonts, colours, margins, lines, height, width, background images, advanced positions and many other things. Just wait and see!

HTML can be (mis-)used to add layout to websites. But CSS offers more options and is more accurate and sophisticated. CSS is supported by all browsers today.

HTML is used to structure content. CSS is used for formatting structured content.

As the Web gained popularity, designers started looking for possibilities to add layout to online documents. To meet this demand, the browser producers (at that time Netscape and Microsoft) invented new HTML tags such as for example <font> which differed from the original HTML tags by defining layout - and not structure.

This also led to a situation where original structure tags such as <table> were increasingly being misused to layout pages instead of adding structure to text. Many new layout tags such as <blink> were only supported by one type of browser. "You need browser X to view this page" became a common disclaimer on web sites.

CSS was invented to remedy this situation by providing web designers with sophisticated layout opportunities supported by all browsers. At the same time, separation of the presentation style of documents from the content of documents, makes site maintenance a lot easier.

CSS was a revolution in the world of web design. The concrete benefits of CSS include:

- control layout of many documents from one single style sheet;
- more precise control of layout;
- apply different layout to different media-types (screen, print, etc.);
- numerous advanced and sophisticated techniques.

2) [How CSS works](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/How_CSS_works)

Web browsers apply CSS rules to a document to affect how they are displayed. A CSS rule is formed from:

- A set of properties, which have values set to update how the HTML content is displayed, for example I want my element's width to be 50% of its parent element, and its background to be red.
- A selector, which selects the element(s) you want to apply the updated property values to. For example, I want to apply my CSS rule to all the paragraphs in my HTML document.
- A set of CSS rules contained within a stylesheet determines how a webpage should look. 

You will learn a lot more about what CSS syntax looks like in the next article of the module — CSS Syntax.

When a browser displays a document, it must combine the document's content with its style information. It processes the document in two stages:

- The browser converts HTML and CSS into the DOM (Document Object Model). The DOM represents the document in the computer's memory. It combines the document's content with its style.
- The browser displays the contents of the DOM.

A DOM has a tree-like structure. Each element, attribute and piece of text in the markup language becomes a DOM node in the tree structure. The nodes are defined by their relationship to other DOM nodes. Some elements are parents of child nodes, and child nodes have siblings.

Understanding the DOM helps you design, debug and maintain your CSS because the DOM is where your CSS and the document's content meet up.

There are three different ways to apply CSS to an HTML document that you'll commonly come across, some more useful than others. Here we'll briefly review each one.

**External stylesheet**
You've already seen external stylesheets in this article, but not by that name. An external stylesheet is when you have your CSS written in a separate file with a .css extension, and you reference it from an HTML <link> element.

**Internal stylesheet**
An internal stylesheet is where you don't have an external CSS file, but instead place your CSS inside a <style> element, contained inside the HTML head.
  
**Inline styles**
Inline styles are CSS declarations that affect one element only, contained within a style attribute
*Please don't do this, unless you really have to! It is really bad for maintenance (you might have to update the same information multiple times per document), and it also mixes your presentational CSS information with your HTML structural information, making the CSS harder to read and understand. Keeping your different types of code separated and pure makes for a much easier job for all who work on the code.*

*The only time you might have to resort to using inline styles is when your working environment is really restrictive (perhaps your CMS only allows you to edit the HTML body.)*

3) [CSS reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

Contans keyword index

# Slides
 [Session slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4454992-dt-content-rid-7858968_2/courses/1718-CM6112/Session2_CSS.pdf)

1) [w3schools demo page](https://www.w3schools.com/css/demo_default.htm)

2) [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

3) [Scoped CSS](http://caniuse.com/#search=scoped)

4) [MDN web docs- CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)

5) [Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

6) [Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

# Post session reading
