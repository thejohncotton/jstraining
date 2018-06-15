---
# More DOM Manipulation and HTML Input
---

## The form tag

<!-- on index add -->
`<li><a href="contact.html">Contact</a></li>`
and 

`<li><a href="contact.html">Contact</a></li>`

Let's add a contact page to our demo site:

On this new page we'll add this form:

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

---
## Specificity in JS
In a web document, scripts are loaded in the order they are imported.
i.e:
```
<script src="script1.js"></script>
<script src="script2.js"></script>

```
`script1.js` will load, and `script2.js` will only begin loading the second
script once `script1.js` is fully loaded.
---

## On Load and ready:

`window.onLoad() // run this code when the window object is loaded.`

`document.ready() // runs when document is ready`

```
$(document).ready(function(){
    // begin to execute this code
    //now that the DOM has been initialized.
})
```

