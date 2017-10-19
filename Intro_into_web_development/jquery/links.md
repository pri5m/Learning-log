
[Lesson plan pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4470029-dt-content-rid-7970376_2/courses/1718-CM6112/SessionPlan.pdf)

# Pre session reading

[jquery website](https://jquery.com/)

[When to use Vanilla JavaScript vs. jQuery?](https://stackoverflow.com/questions/4651923/when-to-use-vanilla-javascript-vs-jquery)

The correct answer is that you'll always take a performance penalty when using jQuery instead of 'plain old' native JavaScript. That's because jQuery is a JavaScript Library. It is not some fancy new version of JavaScript.

The reason that jQuery is powerful is that it makes some things which are overly tedious in a cross-browser situation (AJAX is one of the best examples) and smooths over the inconsistencies between the myriad of available browsers and provides a consistent API. It also easily facilitates concepts like chaining, implied iteration, etc, to simplify working on groups of elements together.

Learning jQuery is no substitute for learning JavaScript. You should have a firm basis in the latter so that you fully appreciate what knowing the former is making easier for you.

-- Edited to encompass comments --

As the comments are quick to point out (and I agree with 100%) the statements above refer to benchmarking code. A 'native' JavaScript solution (assuming it is well written) will outperform a jQuery solution that accomplishes the same thing in nearly every case (I'd love to see an example otherwise). jQuery does speed up development time, which is a significant benefit which I do not mean to downplay. It facilitates easy to read, easy to follow code, which is more than some developers are capable of creating on their own.

In my opinion then, the answer depends on what you're attempting to achieve. If, as I presumed based on your reference to performance benefits, you're after the best possible speed out of your application, then using jQuery introduces overhead every time you call $(). If you're going for readability, consistency, cross browser compatibility, etc, then there are certainly reasons to favor jQuery over 'native' JavaScript.

# Slide

[lesson slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4472343-dt-content-rid-7997280_2/courses/1718-CM6112/jQuery.pdf)
