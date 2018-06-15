----------------------------------------------------------------- 

# Essential JavaScript, CSS and layout


---
## let's get started:

<!-- 1. Connect on [Slack](https://bjcjs.slack.com). -->
1. Create developer accounts with [Github](https://www.github.com), [AWS](https://aws.amazon.com/cloud9/), and [thimble](https://thimble.mozilla.org)
.
2. Create a new cloud9 project [(read the docs)](https://docs.c9.io/docs/)
---
## Essential Command-Line
Let's try typing the following in the cloud9 terminal:

`echo hello, world.`

`echo hello  > hello.txt`

`echo world >> hello.txt`

---
### Working with directories
Try the following in the cloud9 terminal:

`mkdir www`

`ls`

`touch index.html`

`ls`

`touch www/index.html`

`rm index.html`

`ls`

`cd www`

`ls`

`touch index.js`

`ls`

`pwd`

`cd ..`

---

## Essential Text Editor

Cloud 9 has a built in modern text-editor, but there exists time where we might only be able to edit code from the command-line. (Many developers prefer to use a command-line based editor and will argue that Vim or Emacs
are the only text editors that you will ever need.)

## Vim
Vim is a command-line based text editor that switches has multiple modes and can
support many commands for keyboard/terminal speed.

Try the following command in your terminal: `vim hello.txt`
Try typing, but specifically notice that ` h j k l ` can move the cursor.

Press `i` to switch from normal mode to **insert** mode.

Edit the document to change the text to just `hello world` on one line.

To save these changes, you can use a command by pressing the `esc` key to switch
to normal mode and then using the command `:w` for 'write' and you can quit vim 
by using the `:q` command. You can also combine commands i.e. `:wq`

From now on, we'll likely be using Cloud 9's editor.

Feel free to check out this [interactive tutorial](http://www.openvim.com/) or 
[read the docs](https://www.vim.org/docs.php) for more vim.


### Opening files in the editor from the cli
While you can open files from your environment directly by clicking, a common
practice when creating directories and folders from the command line is to open 
the files directly from the command line.

Cloud 9 doesn't natively support a command to open files, but we can add an NPM
module (more on NPM later) to support this need.

Install the package c9 by typing `npm install -g c9`
Now (after restarting your workspace in some cases) you can start calling c9
commands. i.e. `c9 open hello.txt` equivalent to `program-name file-name.ext` on
unix systems.

---
## Essential HTML

Let's update our site structure so that in our environment directory we have an
index.html file, and a `css/style.css` and corresponding `js/script.js` files 
and directories.

Our structure should now contain:
```
index.html
/css/style.css
/js/script.js

```

Lets create the HTML document.

Many modern editors natively submit [*emmet*](https://emmet.io/) shortcuts.

We can initialize our `index.html` file by creating boilerplate with emmet.
In index.html, type `!` and press `tab`.

This will result in the following generated HTML:
``` 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
### Hello HTML
HTML is a markup language that uses tags for elements.

Lets start small and add a heading to our index.html page.
Between the opening and closing `body` tags write the following:
`<h1>Hello World</h1>`


### Adding style and functionality
In script.js add the following line:
`console.log("hello, world");`

In style.css add the following css rule:

``` 
h1 {
    color: red;
} 

```

### Connecting the document to css and js

Connecting CSS:
The tag for linking your style sheet in HTML is `<link>`
**notice** this tag is self closing and does not need to be closed. i.e `</>`

HTML tags contain attributes. i.e. href in ```<a href="http://example.com">This is a link</a>```

or src in ```<img src="https://images.pexels.com/photos/20787/pexels-photo.jpg">```

which will yield: ![](https://images.pexels.com/photos/20787/pexels-photo.jpg)

Code for linking CSS:
`<link src="css/style.css" rel="stylesheet">`

Code for linking JS used the script tag:

`<script href="js/script.js"></script>`

---

## Essential Git

Initializing a git repository:

`git init`

This begins tracking your changes.
To check on the status of your repository you can use the 
`git status` command.

Right now we have a repository that isn't tracking changes.

To stage a single file (or everything) we can use the `git add` command.

Example: `git add file.ext`

We can add all files in our working directory by typing `git add .`

Now that we are tracking changes we can check our status again.

`git status`

Git histories are grouped into pieces of meaningful changes called commits.

For instance: `git commit -m "initialize repository"`
or `git commit -m "resize paragraph text"`

where `-m` is your commit mesage.

let's create our initial commit:
`git commit -m "initialize repo"`

Now check the status once more:

`git status`

We have now successully initialized a repository and commited come code.

There is one more step to successfully securing our code.

## Setting up a remote

This is where Github comes into play. Github allows its users to backup their git
repositories remotely for free (as long as it's public).

Go to [github](https://github.com) and click the + in the top right corner of the window.

Create a new repository with the same name as your cloud9 project,
but don't initialize the repo with a readme.md file.

Once created, copy the address of your repository ending in `.git`

To link our local repository with the remote repository we can use the `git remote`
commands. 

`git remote add origin url-of-remote.git`

Now that we have our remote connected we can push our changes by typing 
`git push origin master`

Now refresh github and see your files update.

<!------->
<!--### gitignore-->

<!--We don't always want to track everything (like secret keys or environment specific-->
<!--folder). With cloud9 we have a hidden directory called `.c9`-->
<!--You'll notice this in your repo, but it's hidden in the directory on cloud9.-->
<!--To see this in c9 type `ls -a` in the CLI.-->

<!--We can simply create an ignore file called gitignore by typing `touch gitignore`-->
<!--and adding the following to ignore this directory.-->

<!--`/.c9`-->

<!--Which will tell git not to track this folder.-->


---
## Deployment

Since we already have a github account, we can now deploy our site using 
[netlify](https://www.netlify.com).

A continuous deployment platform that triggers deploys based on git commits.

Click the 'New Site From Git' button, and link to your github repository.

Now you can deploy your site and also give it a custom url.


---
## Exercises

1. Add more content to your site in index.html
i.e. paragraphs, links, images and more.
2. Add a function to your js file.
3. Add more css rules to style.css

Common git commands:

`git add . `

`git commit -m "commit message"`

`git push origin master` or shortform `git push`

## JS in a REPL

To open up a JS REPL from the CLI you can use the 
`node` command.
You can now type JavaScript directly in the console.
try `2 + 2` `"2" + "2"`
