----------------------------------------------------------------- 

# Essential JavaScript


---
## let's get started:

1. Connect on [Slack](https://bjcjs.slack.com).
2. Create developer accounts with [Github](https://www.github.com) and [AWS](https://aws.amazon.com/cloud9/).
3. Create a new cloud9 project [(read the docs)](https://docs.c9.io/docs/)
---
## Essential Command-Line
Let's try typing the following in the console:

`echo hello, world.`

`echo hello  > hello.txt`

`echo world >> hello.txt`

---
### Working with directories
Try the following in the cloud9 console:

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

Cloud 9 has a built in modern text-editor, but sometimes it makes more sense 
to edit code from the command-line. (Many developers will argue that Vim or Emacs
are the only text editors that you should use.)

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

---

## Essential Git


---

## JS in a REPL