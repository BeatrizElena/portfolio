# JQuery

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Portfolio Page</title>
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css"/>
        <script src="https://apis.google.com/js/client.js?onload=onClientLoad" type="text/javascript"></script>
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
        <link href="animate.css" rel="stylesheet">
    </head>
    <body>
        <script>
            //target html elements through use of JQuery's class .addClass() 
            $(document).ready(function(){
                $("button").addClass("animated bounce");
                $(".well").addClass("animated bounce");
            });
        </script>
        <!-- Only change code above this line. We will modify HTML elements with JQuery scripts, not in the HTML -->
        <!-- House page within a Bootstrap Container Fluid Div -->
        <!-- Use Bootstrap classes text-primary and text-center -->
        <div class="container-fluid">
            <h4 class="text-primary text-center">Web Developer</h4>
            <!-- Create a Bootstrap row, i.e. a div with Bootstrap class "row" that creates a row into which to put our inline elements-->
            <div class="row"></div>
                <!-- Split Bootstrap Row into two columns with class col-xs-6 -->
                <div class="col-xs-6">
                    <!-- Create Bootstrap Wells. Wells create a visual sense of depth for columns -->
                    <!-- Give each well an id. Left well's id = "left-well". Right well's id: "right-well". -->
                    <!-- Label Bootstrap Wells -->
                    <h4>#left-well</h4> 
                    <div class="well" id="left-well">
                        <!-- Add button elements within the wells -->
                        <!-- Apply the Bootstrap default classes of btn and btn-default to each button -->
                        <!-- Create the class "target" that we'll use later with JQuery -->
                        <!-- Give each element a unique id so it can later we can use JQuery to target each button -->
                        <!-- Label each Bootstrap Button -->
                        <button class="btn btn-default target" id="target1">#target1</button>
                        <button class="btn btn-default target" id="target2">#target2</button>
                        <button class="btn btn-default target" id="target3">#target3</button>
                    </div>
                </div>
                <div class="col-xs-6"></div>
                    <h4>#right-well</h4>
                    <div class="well" id="right-well">
                        <button class="btn btn-default target" id="target4">#target4</button>
                        <button class="btn btn-default target" id="target5">#target5</button>
                        <button class="btn btn-default target" id="target5">#target6</button>
                    </div>
        </div>
    </body>
</html>
```

## Learn how Script Tags and Document Ready Work 

jQuery is the most popular JavaScript tool of all time.

Before we can start using jQuery, we need to add some things to our HTML.

First, add a script element at the top of your page. Be sure to close it on the following line.

Your browser will run any JavaScript inside a script element, including jQuery.

Inside your script element, add this code: `$(document).ready(function() {` to your script. Then close it on the following line (still inside your script element) with: `});`

We'll learn more about functions later. The important thing to know is that code you put inside this function will run as soon as your browser has loaded your page.

This is important because without your document ready function, your code may run before your HTML is rendered, which would cause bugs.

## Target HTML Elements with Selectors Using jQuery: The `.addClass()` JQuery's function

The `.addClass()` function allows us to add classes to any html element, as long as the element can be targeted either with its own name, e.g. "button" or its class or id name.

All jQuery functions start with a `$`, usually referred to as a **dollar sign operator**, or as **bling**.

jQuery often selects an HTML element with a **selector**, then does something to that element.

For example, let's make all of your button elements bounce. Just add this code inside your document ready function:

`$("button").addClass("animated bounce");`

Besides the `jQuery library`, we've needed the `Animate.css library` to use the `animated` and the `bounce` classes. We're using jQuery to apply the Animate.css bounce class to the button elements.

*Note for FCC editor:* Use $("button").addClass("animated bounce"); instead of $('button').addClass("animated bounce"); since single-quote selectors will not pass tests.

## Target Elements by Class Using jQuery: The `.addClass()` JQuery's function

We'll now target div elements with the class `well` by using the `$(".well")` selector. Note that, just like with CSS declarations, you type a . before the class's name.

Then use jQuery's `.addClass()` function to add the classes animated and shake. For example, you could make all the elements with the class text-primary shake by adding the following to your document ready function:
`$(".text-primary").addClass("animated shake");`

## Target Elements by Class Using jQuery: The `.removeClass()` JQuery's function

## Target Elements Using jQuery: The `.css()` function

Example of changing the color of an element with an id of #target1 to blue: `$("#target1").css("color", "blue);`

## Disable an Element Using jQuery: The `.prop()` function

You can change the non-CSS properties of HTML elements with jQuery. For example, you can disable buttons. When you disable a button, it will become grayed-out and can no longer be clicked.

jQuery has a function called `.prop()` that allows you to adjust the properties of elements. Here's how you would disable all buttons:
`$("button").prop("disabled", true);`

## Change Text Inside an Element with `.html()` and with `.text()`

Example to emphasize the text of the heading we already wrote: `$("h3").html("<em>jQuery Playground</em>");`

The difference bw `.html()` and `.text()` is that `.text()` will not evaluate any HTML tags passed to it, but will treat it as text. In the `.html()` example above, it would not emphasize the heading.

## Remove an Element with the `.remove()` function

## Move Elements with the `.appendTo()` function

Selects HTML elements and appends to another element. Example: `$("#target4").appendTo("#left-well");` takes an element with id #target4 and moves inside an element with id #left-well.

## Clone an Element with `.clone()` / Function Chaining

If we wanted to copy an element from one element and have this copy be inside another element, we'd use `.clone()` and `.appendTo()` together, or `function chaining`. Ex: `$("#target3").clone().appendTo("#right-well");`.

## Target the Parent or All the Children of an Element: `.parent()`, `.children()`

Examples:
`$("#target1").parent().css("background-color", "blue");`
`$("#left-well").children().css("color","yellow");`

## Target a Specific Child Using `.target:nth-child(<child number>)`

Ex. targeting the 3rd element of each well class: `$("#.target:nth-child(3)").addClass("animated bounce");`

## Target Even or Odd Numbered Elements using `.target:even` or `.target:odd`

Important to Remember: jQuery is *zero-indexed*, meaning that `:odd` selects the 2nd element, 4th element, and so on.
Ex: `$(".target:odd").addClass("animated shake");`

## jQuery can Modify the entire Page Using the `$("body")` Selector

Ex: `$("body").addClass("animated hinge");` 
