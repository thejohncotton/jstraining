# HTML Input and more DOM Manipulation

---

## The form tag:

If we want users to input data on a page we must use the `<form>` element. We'll be learning about forms in the context of a contact page.

### Exercise 1: Creating a contact page.

  1. Add a contact.html page inside the same directory as your `index.html` file.

  2. Inside of the list in your social-footer `div` area, add another list item to link to the new contact page. 
  
 **hint:**

`<li><a href="contact.html">Contact</a></li>`

  3. Copy the entire footer section (before the closing body tag) and update the link to contact.html with a link to `index.html` as `home`.

Above the footer on this contact page we'll add this form:

```html
 <!--
  The action attribute defines where on the server the form data should be sent
  The method attribute specifies the HTTP method (GET or POST)
-->

<form action="form-responses/new" method="POST">

  <input type="text" name="firstname" value="First Name" size="100" autofocus>
  <input type="text" name="lastname" value="Last Name" size="100">
  <input type="email" name="userEmail" placeholder="your.email@example.com">

  <label>What's this message about?
    <input type="radio" name="subject" value="professional" checked><span>I'd like to hire you!</span>
    <input type="radio" name="subject" value="personal" checked><span>Personal message</span>
    <input type="radio" name="subject" value="other" checked><span>Don't know/something else</span>
  </label>

  <input type="checkbox" name="optin" value="trusting" checked>Subscribe me to your newsletter!
  <input type="checkbox" name="optout" value="skeptical" disabled>Cheeky checkbox...

  <label for="marketing">How did you hear about me?</label>
  <select name="marketing">
    <optgroup label="Online">
      <option value="social">Social Media (FB, Twitter, LinkedIn)</option>
      <option value="github">Online Portfolio (GitHub)</option>
      <option value="search">Search Engine</option>
      <option value="email">Email</option>
    </optgroup>
    <optgroup label="In-Person">
      <option value="networking">We met at a networking event</option>
      <option value="referral">Personal referral</option>
      <option value="random">We met somewhere else</option>
    </optgroup>
    <option value="other">Other</option>
  </select>

  <textarea name="user_message" rows="8" cols="40"></textarea>
  <input type="submit">
</form>

```

We have a form on our page, but now it's a mess. 
Add some `<br>` tags to add line breaks in the form to clean it up a bit.
--

---
# Styling forms:

The html `form` and `input` tags currently have no style. Let's change that.

<!-- break down into steps -->
### Excercise:
Most browsers default to white backgrounds and dark text for form elements. Let's give our form a darker theme with lighter text.
1. Write a css selector that selects the `<form>` element.
**hint:** `form {}`
2. Inside the curly braces add the following rules
```css

form {
  padding-left: 10px; // add some internal space
  padding-right: 10px;
  padding-bottom: 10px;
  width: 75%;   // set the width of the form to 75% of the container
  margin-left: auto;
  margin-right: auto;
  margin-top: 4em;
  margin-bottom: 32px;
  text-align: left;
  background-color: #444; // gray
  color: white;
}
```
3. Now that there is some styling on the form container, let's add some styling to the `input` elements.

```css

input {
    width: 100%; // set width to be 100% of form width
    height: 3em;  // sets the height to 3em
    vertical-align: middle; // aligns checkbox labels with boxes
    margin-top: 2px; // adds line space
  
}
```
To declare styles for specific types of input we can use a complex selector:

```css
input[type=checkbox]{
  // apply only to inputs of type checkbox
  width: 2em;
}
input[type=radio] {
  // apply only to inputs of type radio
  width: 2em;
}
```
 You can apply the same rules to multiple selections by chaining them with a `comma` 
 i.e.
```css
input[type=text], input[type=email]  {
  font-size: 20px;
  margin-left: -6px;
  background-color: inherit;
  color: #fff;
  border: none;
}
```
`:focus` is a type of selector called a pseudo selector that places style on an element based on its condition. In this case the focus (current cursor location) of the form.

```css
input[type=text]:focus, input[type=email]:focus {
  border: solid;
  border-color: white;
  border-width: 5px;
}
```
To style a placeholder you muse use this syntax:

```css
::placeholder {
  color: #747373;
}
```
Let's add the followiing to finish styling our form.
```css
label {
  color: white; // set label text color
}

input[type=submit] {
  // style the submit button
  background-color: green;
  color: white;
  font-size: 20px;
  padding-bottom: 4px;
}

textarea {
  resize: none;
  width: 100%;
  height: 60px;
  margin-left:-4px;
}

```

---
## Specificity in JS
In a web document, scripts are loaded in the order they are imported.
i.e:

```html
<script src="script1.js"></script>
<script src="script2.js"></script>

```

`script1.js` will load, and `script2.js` will only begin loading the second
script once `script1.js` is fully loaded.

---

# Events
There are many different events in JavaScript ranging from the page loading, to a click, or a scroll, and even custom events.

## Event Listeners
Event listeners are a special type of of function in JavaScript. They take in two arguments, an event i.e. `click` and a callback function that will be executed then the event occurs i.e ` console.log("a click event occured")`

Here is what a basic click event listener looks like for a button:

```javascript
document.getElementById('hello-button').addEventListener('click', console.log("a click event has occured"))
```

## Submit
The event reserved for form submissions is the `submit` event where the form will submit the data entered as an http request to the location specified in the `action` attribute.

If you click the submit button right now notice that you get a nasty error.

## Exercise 2
Let's add an event listener to our contact form.

1. Give your form an id of `contactForm`
2. use `getElementById` to add an event listener for the `submit` event.
3. prevent the default action of the html form.

Example:
```javascript

  document.getElementById('contactForm').addEventListener('submit',function(event){ event.preventDefault();
      })
```
In addition to handling events related to our form, we can also reference and manipulate the data from our form fields.

Right beneath `event.preventDefault();` add the following:

```javascript
 var data = [];
      data.push(this.firstname.value);
      data.push(this.lastname.value);
      var message = "Here is a message from " + data.toString();
      console.log(message);
```
This script creates an empty array called `data`, pushes values to the array from the firstname and lastsname fields and then combines them into a message that is logged to the console.

Now add some data inside of your form and hit that submit button!

## onLoad and ready:
Sometimes scripts can be executed too soon.
We can control the timing of our scripts by placing them inside of an onLoad or ready event.


`window.onLoad() // run this code when the window object is loaded.`

`$(document.ready() // runs when document structure is ready`

add the following to your script.js file: 

```javascript
$(document).ready(function(){
    console.log('document is ready')
})
```
---
## Challenge

1. Set more html attributes using javascript.
    + hijack a link and send a user to another website.
   + change an image src attribute to another image

2. Make the layout your own.
   + add more of the many CSS rules to give this page style.

## Additional Resources:

### Reference Material:

1. [W3 Schools](https://www.w3schools.com/)
2. [Mozilla Developer Network](https://developer.mozilla.org/en-US/)
### Tutorials 
1. [Learn Enough HTML To Be Dangerous](https://www.learnenough.com/html-tutorial)
2. [Learn Enough CSS and Layout To Be Dangerous](https://www.learnenough.com/css-and-layout-tutorial)
3. [Learn Enough JavaScript to Be Dangerous](https://www.learnenough.com/javascript-tutorial)
4. [Savvy Coders 80 Hour Bootcamp course material](https://github.com/NAlexPear/savvy-course-materials/)


