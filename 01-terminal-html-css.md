# Day 1 - Terminal and HTML/CSS

First day! Welcome to the Iron yard.

We talked about a few things:

- Expectations
- [install atom](https://atom.io/docs/v0.194.0/getting-started-installing-atom#atom-on-mac)
- [install google chrome](https://www.google.com/intl/en/chrome/browser/desktop/index.html)
- terminal basics
- [install iTerm2](http://iterm2.com/)
- [install Oh-My-Zsh](https://github.com/robbyrussell/oh-my-zsh)
- html introduction
- css introduction

## Terminal

The terminal is a developer's best friend, and will be used throughout the course.  Once experienced at using a terminal, you'll find that doing many things in programming are simpler and more efficient.  You'll effectively be able to accomplish more and have a better understanding of what's going on in your application.

Following are some of the commands we covered today:

### Navigation in Terminal

```
$ ls
Applications
Desktop
Documents
Downloads
```
 Lists the contents of the current directory you are in.

```
$ ls -al

drwx------     4 calvinwebster  staff     136 Dec 11 01:11 Applications
drwx------+   20 calvinwebster  staff     680 Jan  5 10:13 Desktop
drwx------+   56 calvinwebster  staff    1904 Jan  5 10:09 Documents
drwx------+  193 calvinwebster  staff    6562 Dec 29 15:27 Downloads

```
When <code>$ ls</code> is used with the <code> -al</code> flags, it will give you more information about the file and/or directories such as when it was last modified, the file/folder permissions, and the user that owns the file/folder.

```
$ pwd
/Users/yourusername

```
prints out the path of the current working directory in your file system.

```
$ cd Documents

```
The above command will navigate you inside of the Documents folder

### Creating files folders in terminal

```
$ mkdir myDirectoryName

```
Creates a directory

```
$ touch myFile.txt

```
Creates a new file.

```
$ cat myFile.txt

```
Reads the contents of myFile.txt in your shell.

```
$ echo "I am going into myFile" >> myFile.txt

```
Adds the line "I am going into myFile" to myFile.txt

## HTML

Today we talked about HTML in general, what it actually is and some of the most used tags.

Definition of HTML (via MDN):
<blockquote>
HTML adds "markup" to standard English text. "Hyper Text" refers to links that connect Web pages to one another, making the World Wide Web what it is today. By creating and uploading Web pages to the Internet, you become an active participant in the World Wide Web. HTML supports visual images and other media as well. HTML is the language that describes the structure and the semantic content of a web document. Content within a web page is tagged with HTML elements such as &lt;img&gt;, &lt;title&gt;, &lt;p&gt;, &lt;div&gt;, &lt;picture&gt;, and so forth.  These elements form the building blocks of a website.
</blockquote>

For example, following is the basic structure, tagwise, for a basic html document

```
<!-- This is a comment -->
<!DOCTYPE html>
<html>
  <head>
    <title>This is a title</title>
    <link rel="stylesheet" href="styles.css">
    <!-- The <head> tag usually contains any external CSS stylesheets or meta information about a particular page -->
  </head>
  <body>
  <!-- The <body> tag is where human-viewable content is stored -->
  </body>
</html>

```

## CSS

As defined by the Mozilla Developer Network:
<blockquote>
Cascading Style Sheets, most of the time abbreviated as CSS, is a stylesheet language used to describe the presentation of a document written in HTML or XML (including various XML languages like SVG or XHTML). CSS describes how the structured element must be rendered on screen, on paper, in speech, or on other media.
</blockquote>

In our class today, we covered some of the fundamentals of CSS.

Specifically, we covered:

- inline vs. &lt;style&gt; vs external stylesheet and how that affects the styling and 'cascade' which may override styles
- You can apply CSS styles to HTML tags like <code>&lt;h1&gt;, &lt;p&gt;, or &lt;div&gt;</code> or other elements/selectors on the page, such as classes or id's.
- We talked about a few of the properties in css that we can use to style pages such as <code>background-color, margin, padding, font-size, font-weight, color</code> - there are so many more properties that we will be exploring in the coming days/weeks, but please go forth and try to experiment with the other css properties.

```
/* This is a CSS comment */
body {
  background-color: red;
  font-size: 20px;
  font-weight: strong;
}

```

## Resources

[Command line crash course](http://cli.learncodethehardway.org/book/)

[Treehouse Tutorial of the Console](http://teamtreehouse.com/library/console-foundations)

[HTML Element Reference Guide](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

[CSS Reference Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)

[Chrome Dev Tools - Chapter 1](http://discover-devtools.codeschool.com/chapters/1?locale=en)

## Downloads & Installation

[XCode](https://developer.apple.com/xcode/downloads/)

[Google Chrome Browser](https://www.google.com/intl/en/chrome/browser/desktop/index.html)

[iTerm2 - a better terminal](http://iterm2.com/)

[Oh-My-Zsh - for your iTerm](http://ohmyz.sh/)

[Atom Text Editor](https://atom.io/)
