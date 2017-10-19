[]()

Not a replacement for Javascript

JS library- There is a syntax

jQuery is not a language, but it is a well written JavaScript code. As quoted on official jQuery website, "it is a fast and concise JavaScript Library that simplifies HTML document traversing, event handling, animating, and Ajax interactions for rapid web development."

**Pros**

- Browser compatability

- Probs easier for beginners

**Cons**

- Takes long to load because of the library

Selecting something, preforming an action on it

$(selector)

Object vs Core methods

- $().method

- $.method

# Accessing the DOM: Elements

- All elements$("*")

- Element Selector $("element")

- Class selector $(".class")

- ID selector

```
// Add the ready function rem the closing braces at the bottom.
$(document).ready(function(){

// selectors
  // select wild card
  //$("*").remove();
  // select element name
  $("section").append(" section text ");
  // select by ID
  $("#appearID").append(" ID Text ");
  // Using a time out
  setTimeout(function(){
    $("#appearID").append(" ID Text 2 ");
  }, 2000);




// Some Actions
  // hide and remove
  $(".hideClass").hide();
  $(".removeClass").remove();

  // show --- note the hide is still in the DOM but the remove is no longer there.
  $(".hideClass").hide();
  $(".removeClass").remove();


//  Exercise:
//  1) add "Some Extra Text" to .appearClass
  $(".appearClass").append("Some extra text");
//  2) look up fadeTo():
      $(".appearClass").fadeTo(2000, 0.1);
      $(".appearClass").fadeTo(2000, 1);
//    make .appearClass fade to 0.1 opacity then fade back in.
//    hint: ignore the event stuff
//      and follow format of previous actions.
});
```
# Accessing the DOM: Attributes

- Equals =

- Not equals !=

• Starts with: ^

• Ends with: $


```
$(document).ready(function(){
$("input[name$='3']").hide("text");
});
```
```
// Add the ready function rem the closing braces at the bottom.
$(document).ready(function(){

//  Accessing by attribute
  // by attribute property
  $("input[name='userName']").toggle();
  // starts with
  $("input[name^= 'add']").hide();
  // ends with
  $("input[name$='3']").toggle();
  // modify add atributes
  $("input[name$='1']").attr("value", "Enter Address");
  $("input[name$='1']").toggle();
    // look at the dev tools Elements to verify this
  // use atribute value
  console.log($("input[name$='1']").attr("value"));


// Exercise
// bring all inputs back again
  $("input[name$='2']").toggle();
});
```
