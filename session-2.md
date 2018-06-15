
<!-- Make a quick cat portfolio website to learn HTML
CSS (later JS)-->
# More HTML and CSS
---
Let's pick back up and refactor our Hello page into something more useful.

We can pick back up in cloud9, or you can remix this [thimble project](https://thimbleprojects.org/johncotton/506245) to jump back in.

Try the following HTML exercises:

## Exercise 1
Let's refactor our site into a portfolio page.

1. Update the heading text from Hello World and change it to your name.
*hint:* `<h1>First Last</h1>`
2. Add an image to your site below this heading.   *hint:* `<img id="profile-image" src="image-url.ext" alt="profile-image">`

A full example of an image tag with cat photo:
```html
<img id="profile-image" src="https://www.telegraph.co.uk/content/dam/pets/2017/01/06/1-JS117202740-yana-two-face-cat-news_trans_NvBQzQNjv4BqJNqHJA5DVIMqgv_1zKR2kxRY9bnFVTp4QZlQjJfe6H0.jpg" alt="two-face-cat">
```
3. Below our newly added image lets add a footer with some contact information:

### **hint:** 
```html 
<!-- footer area  -->
    <div class="social-footer">
      <ul>
        <li><a href="https://facebook.com" target="_blank">Facebook</a></li>
        <li><a href="https://twitter.com" target="_blank">Twitter</a></li>
        <li><a href="https://github.com" target="_blank">Github</a></li>
      </ul>
    </div>
```

Let's take note of the following elements here:
+ `<div>` represents a logical grouping of content.
    + `class="social-footer"` gives this group a CSS class of "social-footer"
+ `<ul>` creates an unordered list of items. (`<ol>` creates an ordered list i.e. 1. 2. 3...)
+ `<li>` creates a list item inside this 
+ `<a>` (the anchor tag )creates a link.
    + `href=""` this attribute sets the HTML Reference or link via URL 
    + `target="_blank"` sets the target for opening the link into a new tab or window.

## Exercise 2
Lets add some style to this page.
In css/style.css lets add some rules to our elements:

1. add the following rules to the `img` element:



```css

img {}
  width: 50%;
  border-radius: 100%;
  margin-left: 25%;
  margin-right: 25%;
}
```
```css
div.social-footer {
/*  position: absolute;*/
  bottom: 10px;
/*  margin-left: 30%;*/
/*  margin-right: 30%;*/

}
div.social-footer li{
  align-items: center;
  display: inline;
  list-style: none;

}

```
---

# Essential Developer Tools
---

Now that we have seen how front-end technologies work together to make a website
i.e.
`html` as a document framework, `css` for styles, and `JavaScript` for logic and
DOM manipulation,
we will continue to develop a deeper understanding of the tools available to inspect,
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
Open 
this [jquery sandbox](https://jquerysandbox.netlify.com/).

To remove mystery, go ahead and use the inspector tool, or view-source to view the html document.
Make a mental note of the `<tags> ` `.classes` and `#id`'s. We'll be using these to manipulate our DOM.

 Now open your Chrome console. hint: `ctrl` + `shift` + `j`  or `cmd` + `opt` + `j` and type some of the following exercises:
1. Turn all `h1` text `blue`. HINT:
```javascript
$("h1").css("color", "blue");
```
2. Turn the `body`'s `background-color` to `red`. HINT:
```javascript
$("body").css("background-color", "red");
```
3. Increase the `font-size` of the element with an `id` of `everything`. HINT:
```javascript
$("#everything").css("font-size", "120%");
```
4. Add a `border` to all elements with a `class` of `holder`. HINT:
```javascript
$(".holder").css("border", "2px solid black");
```
5. Change the `font-weight` of all `li` elements to `bold`. HINT:
```javascript
$("li").css("font-weight", "bold");
```
6. Change the `color` of all `p` elements that come directly after the `h1` element to `green`. HINT:
```javascript
$("h1+p").css("color", "green");
```
7. Change the `#secret` to a hidden element with `display: none;`. HINT:
```javascript
$("#secret").css("display", "none");
```
8. Replace the text content of `#change-me` with "I feel like a new sentence". HINT:
```javascript
$("#change-me").text("I feel like a new sentence");
```
9. Put the new contents of `#change-me` into some paragraph tags. HINT:
```javascript
$("#change-me").html("<p>I feel like a new sentence</p>");
```

---

### Exercise 2
#### `append`, `prepend`, `hide`, and `show`

Sometimes, we don't want to overwrite all of the text or HTML contents of an element. Instead, we just want to tack some text or HTML to the end or beginning of that element. That's where `.append()` and `.prepend()` come in!

If we start out with the following HTML:

```html
<p>I'm a sentence</p>
```

...we can add content to the front and tail of the sentence like so:

```javascript
$("p").append("!"); //<p>I'm a sentence!</p>
$("p").prepend("Behold, "); //<p>Behold, I'm a sentence!</p>

//or chained together:
$("p").prepend("Behold, ").append("!");
```

This is usually much easier to read and use than String concatenation.

It's also very common to want to show and hide elements on the page. We already tried this with `.css("display", "none")`, and this works just fine. But we use this so often that jQuery has given us a shorthand in `.show()` and `.hide()`.

```javascript
// long form
$("div.toggle-stuff").css("display", "none"); // invisible
$("div.toggle-stuff").css("display", "block"); // visible

// shortcut
$("div.toggle-stuff").hide(); // invisible
$("div.toggle-stuff").show(); // visible
```

Now, using the same sandbox page we used for Exercise 1, try the following:

1. Show and hide the `#secret` element with `.show()` and `.hide()` from the console!
2. `append` a calling card with your name to the end of the page. HINT:

```javascript
var callingCard = "<div><b>Alex was here</b></div>";
$("body").append(callingCard);
```

3. `prepend` a greeting to the beginning of the page's `body`. HINT:

```javascript
var greeting = "<h1>Welcome to the jQuery SandBox</h1>";
$("body").prepend(greeting);
```

---

### Exercise 3
#### Basic Animation

While jQuery simplifies basic DOM operations, it adds also adds some unique animations of its own! Try the following in the same Sandbox we used for Exercises 1 and 2:

```javascript
$('ol li').fadeIn() // fade in a set of matched elements over time
$('p .comments').fadeOut() // fade out as set of matched elements over time
$('div#thing').slideDown() // animate an element sliding down over time
$('#message').slideUp() // animate an element sliding up over time
$('.alert').slideToggle() // toggle between an element sliding up or down over time depending on whether it's visible or not
$('#change-me').animate("font-size", "200%") // animate a CSS property of your choosing!
```

---





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