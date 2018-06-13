---
# Essential Tools
---
<!-- Make a quick cat portfolio website to learn HTML
CSS (later JS)-->

Now that we have seen how front-end technologies work together to make a website
i.e.
`html` as a document framework, `css` for styles, and `JavaScript` for logic and
DOM manipulation,
we will continue to get a deeper understanding of the tools available to inspect,
detect, and debug sites and layouts.

**Google Chrome's developer tools work better and with less frustration than 
Internet Explorer so we'll be using Chrome from here on out.**

## View Source
Navigate to [css zen garden](https://csszengarden.com)

You can view the page's source code by typing the following:
`ctrl` + `shift` + `u` for windows or `cmd` + `opt` + `u` for mac.

or in the Chrome navigation bar, select:

View > Developer > View Source


Let's read through the HTML Tags top to bottom.

Note the way an HTML document is nested:
```
<html>
    <head>
       <!-- metadata -->
    </head>
    <body>
        <div class="content">content</div>
    </body>
</html>
```

In the head of the document click the link into the style sheet and walk through
the it line by line.

---

## The Inspector

`ctrl` + `shift` + `i` for windows or `cmd` + `opt` + `i` for mac.

In addition to being able to see the source code, modern browsers give us a
very powerful tool for exploring web documents.

Notice the various tabs:

`elements` refers to HTML Elements `console` will change tabs to the javascript 
console and `network` provides tools for tracking incoming and outgoing data.

Click on a section in Elements, and open the styles tab in the inspector.

## The Developer Console

To open press `ctrl` + `shift` + `j` for windows or `cmd` + `opt` + `j` for mac.
We've seen the ability to run pure javascript in the console and try out different
logic and control flow.

We can also use the console for debugging sites, and for DOM manipulation.

Try the following in the console:
`document.querySelector('body').style.display = "none"`

`document.querySelector('body').style.display = "block"`

Note the syntax `('selector').style.property = "value"`
is similar to the css syntax:

```
selector {
        property: value;
}
```

EXAMPLE

```
body {
    display: none;
}
```
## More JavaScript

Arrays.
Functions.
Objects.
Loops.
Constructor functions.
Iteration.

## Adding html and css to our hello world website

## JQuery
a [jquery sandbox](https://jquerysandbox.netlify.com/)

In a file:
In your index.html file, in a `<script>` tag in the <head> of the document,
link the 
[jquery](https://code.jquery.com/) library.
<!-- connect savvy jquery commands -->
You can now use jquery in your site.


## Exercises

1. Add some classes and ids to your index.html file
2. Using jQuery, interace and manipulate the document.
3. Using vanilla JavaScript, manipulate the document the same way.