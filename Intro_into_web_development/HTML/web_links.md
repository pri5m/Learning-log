# Web links

# Pre reading

1) [Internet history](http://www.internetsociety.org/internet/what-internet/history-internet/brief-history-internet)
2) [History of the web](http://webfoundation.org/about/vision/history-of-the-web/)
3) [A more informal history of HTML and CSS](http://www.wdtonline.com/wdtMagazine/MemberWorks/WiserWays/csshtml.htm)

# Silde links
1) [HTML element reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
2) [Aside](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/aside)
3) [html5 and the document outlining algorithm](https://www.smashingmagazine.com/2011/08/html5-and-the-document-outlining-algorithm/)
4) [Using HTML sections and outlines](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines)
5) [Global attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes)

# Post session homework

1) [HTML5 And The Document Outlining Algorithm](http://www.smashingmagazine.com/2011/08/html5-and-the-document-outlining-algorithm/)

One important part of HTML5 that is still not widely understood is sectioning content: *section, article, aside and nav.* To understand sectioning content, we need to grasp the document outlining algorithm.

The **document outlining algorithm** is a mechanism for producing outline summaries of Web pages based on how they are marked up. Every Web page has an outline, and checking it is easy using a really simple free online tool, which we’ll cover shortly.

Now, I know what you’re thinking, but I haven’t taken leave of my senses with these crazy headings. I am making a very important point, which is that the outline is created by the sectioning content, not the headings.
Go ahead and copy and paste that code into the outliner, and you will see that the heading levels have absolutely no effect on the outline where sectioning content is used.

The section, article, aside and nav elements are what create the outline, and this time the sections are called explicit sections.
One of the most talked about features of HTML5 is that multiple h1 elements are allowed, and this is why. It’s not an open invitation to mark up every heading on the page as h1; rather, it’s an acknowledgement that where sectioning content is used, it creates the outline, and that each explicit section has its own heading structure.

**Sections may contain headings of any rank, but authors are strongly encouraged to either use only h1 elements, or to use elements of the appropriate rank for the section’s nesting level.**

I would strongly advise that until browsers — and, more critically, screen readers — understand that sectioning content introduces a sub-section, using multiple h1 elements is less safe than using a heading structure that reflects the level of each heading in the document, as shown in figure 6 below.

This means that user agents that haven’t implemented the outlining algorithm can use implicit sectioning, and those that have implemented it can effectively ignore the heading levels and use sectioning content to create the outline.
At the time of this writing, no browsers or screen readers have implemented the outlining algorithm, which is why we need third-party testing tools such as the outliner. The latest versions of Chrome and Firefox style h1 elements in nested sections differently, but that is very different from actually implementing the algorithm.

*The section element represents a generic section of a document or application. A section, in this context, is a thematic grouping of content, typically with a heading.*

*Sectioning content elements are always considered subsections of their nearest ancestor sectioning root or their nearest ancestor element of sectioning content, whichever is nearest, regardless of what implied sections other headings may have created.*

But if you remember the basics — that *section, article, aside and nav* create sub-sections on Web pages — then you are 90% of the way there. Get used to marking up content with sectioning elements and to checking your pages in the outliner, because the more you practice creating well-outlined documents, the sooner you will grasp the algorithm.

2) [Using HTML sections and outlines](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Sections_and_Outlines_of_an_HTML5_document)

The structure of a document, i.e., the semantic structure of what is between <body> and </body>, is fundamental to presenting the page to the user. HTML4 uses the notion of sections and sub-sections of a document to describe its structure. A section is defined by a (<div>) element with heading elements (<h1>, <h2>, <h3>, <h4>, <h5>, or <h6>) within it, defining its title. The relationships of these elements leads to the structure of the document and its outline.
  
More generally, HTML5 brings precision to the sectioning and heading features, allowing document outlines to be predictable and used by the browser to improve the user experience.

The heading elements have a rank given by the number in the element name, where <h1> has the highest rank, and <h6> has the lowest rank. Relative ranking matters only within a section; the structure of the sections determines the outline, not the heading rank of the sections.


The new semantic elements introduced in HTML5 bring the ability to describe the structure and the outline of a web document in a standard way. They bring a big advantage for people having HTML5 browsers and needing the structure to help them understand the page, for instance people needing the help of some assistive technology. These new semantic elements are simple to use and, with very few burdens, can be made to work also in non-HTML5 browsers. Therefore they should be used without restrictions.

3) [MDN docs on semantic tags](http://html5doctor.com/resources/#flowchart)

HTML5 Sectioning Element Flowchart pdf. Refer to tag names
