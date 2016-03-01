# Day 2 - HTML/CSS (Layout) & git/github

And the fun continues!

Layouts:
![Different Layouts](https://raw.githubusercontent.com/TIY-Charleston-Front-End-May2015/notes/master/assets/grids.png)

Today we covered:

- Semantic HTML tags (sectioning tags)
- Why Semantic?
- The Box Model
- CSS properties: display, vertical-align, width (percentage/pixel), block, inline-block, margin, padding, border
- git push, git add, git status, git commit, git init
- ssh keys
- github, version control basics and value

## HTML - Semantic Markup

Continuing from yesterday, we talked about more HTML tags, but specifically in their role and how you use tags to help bring more meaning to the content.  

These 'newer' tags are generally called 'sectioning' tags
sectioning tags: <code>&lt;section&gt;</code>, <code>&lt;nav&gt;</code>, <code>&lt;aside&gt;</code>, <code>&lt;article&gt;</code>

From the MDN:
<blockquote>
Elements belonging to the sectioning content model create a section in the current outline that defines the scope of  &lt;header&gt; elements, &lt;footer&gt; elements, and heading content.
</blockquote>

Sectioning Tags:

### &lt;section&gt;

<blockquote>The HTML Section Element ( &lt;section&gt; ) represents a generic section of a document, i.e., a thematic grouping of content, typically with a heading. Each &lt;section&gt; should be identified, typically by including a heading (h1-h6 element) as a child of the &lt;section&gt; element.</blockquote> - MDN

### &lt;article&gt;

<blockquote>
The HTML <article> Element represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable, e.g., in syndication. This could be a forum post, a magazine or newspaper article, a blog entry, a user-submitted comment, an interactive widget or gadget, or any other independent item of content. Each <article> should be identified, typically by including a heading (h1-h6 element) as a child of the <article> element.
</blockquote> - MDN

### &lt;aside&gt;

<blockquote>
he HTML <aside> element represents a section of the page with content connected tangentially to the rest, which could be considered separate from that content. These sections are often represented as sidebars or inserts. They often contain the definitions on the sidebars, such as definitions from the glossary; there may also be other types of information, such as related advertisements; the biography of the author; web applications; profile information or related links on the blog.
</blockquote> - MDN

### &lt;nav&gt;

<blockquote>
The HTML Navigation Element (<nav>) represents a section of a page that links to other pages or to parts within the page: a section with navigation links.
</blockquote> - MDN

Flow Content tags:

### &lt;header&gt;

<blockquote>
The HTML <header> Element represents a group of introductory or navigational aids. It may contain some heading elements but also other elements like a logo, wrapped section's header, a search form, and so on.
</blockquote> -MDN

### &lt;footer&gt;

<blockquote>
The HTML &lt;footer&gt; Element represents a footer for its nearest sectioning content or sectioning root element (i.e, its nearest parent &lt;article&gt;, &lt;aside&gt;, &lt;nav&gt;, &lt;section&gt;, &lt;blockquote&gt;, &lt;body&gt;, &lt;details&gt;, &lt;fieldset&gt;, &lt;figure&gt;, &lt;td&gt;). A footer typically contains information about the author of the section, copyright data or links to related documents.
</blockquote> - MDN

## CSS - Layout styles

We focused most of today on layout and leveraging CSS properties to acheive different layouts while also understanding the box model, so that you can effectively create layouts that are resilient and can adapt to the different environments a browser may present your app.

Mastering creating layouts in CSS is one of the key ingredients to being able to build anything structurally on the web.

Try spending some time looking at different websites and sketching out the layout and not the content/pictures of the site.  You'll be suprised at how few layouts really exists, but its the contrast, content, and colors, etc. that really play into the actual experience.

There are a few layout strategies:

### Using `display: inline-block;` with percentage widths

Given the following markup:

```html
<!doctype html>
<html>
  <head>
    <title>Layout Example</title>
    <link type="stylesheet" href="styles.css">
  </head>
  <body>
    <header>
      <nav>
        <ul>
          <li>
            <a href="">Home</a>
          </li>
          <li>
            <a href="">About</a>
          </li>
          <li>
            <a href="">Contact</a>
          </li>
        </ul>
      </nav>
    </header>
    <section>
      <h1>My Blog</h1>
      <img src="http://fillmurray.com/200/200" alt="" />
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </section>
    <aside>
      <h3>Sidebar</h3>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </aside>
    <footer>
      <nav>
        <ul>
          <li>
            <a href="">Home</a>
          </li>
          <li>
            <a href="">About</a>
          </li>
          <li>
            <a href="">Contact</a>
          </li>
        </ul>
      </nav>
    </footer>
  </body>
</html>

```
Following would be the stylesheet to demonstrate the 2 column layout for the `<section>` (maincontent) and `<aside>` (sidebar):

```css
 section, aside {
  display: inline-block;
  vertical-align: top;
}
section {
  width: 69%;
}
aside {
  width: 30%;
}

```


### Using `float: left;` with percentage widths

Given the following markup:

```html
<!doctype html>
<html>
  <head>
    <title>Layout Example</title>
    <link type="stylesheet" href="styles.css">
  </head>
  <body>
    <header>
      <nav>
        <ul>
          <li>
            <a href="">Home</a>
          </li>
          <li>
            <a href="">About</a>
          </li>
          <li>
            <a href="">Contact</a>
          </li>
        </ul>
      </nav>
    </header>
    <section>
      <h1>My Blog</h1>
      <img src="http://fillmurray.com/200/200" alt="" />
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </section>
    <aside>
      <h3>Sidebar</h3>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
      </p>
    </aside>
    <footer>
      <nav>
        <ul>
          <li>
            <a href="">Home</a>
          </li>
          <li>
            <a href="">About</a>
          </li>
          <li>
            <a href="">Contact</a>
          </li>
        </ul>
      </nav>
    </footer>
  </body>
</html>

```
Following would be the stylesheet to demonstrate the 2 column layout for the `<section>` (maincontent) and `<aside>` (sidebar):

```css
section, aside {
 float: left;
}
section {
 width: 69%;
}
aside {
 width: 30%;
}

```

## Git & Github

Git and Github are related, but separate things.  Git is the version control software that keeps track of your html pages and other files that make up your application and Github is an online service (using git) that allows you to host your repositories on the web and explore, clone, and contribute to other software projects.

A few things to remember about using git in your projects:

### Creating and adding to your new git repository

#### 1. Whenever you create a new project, also create a new folder to hold all of the files as this will make sure that all the files exist in one location.

```zsh
$ mkdir myNewProject
$ ls -a
. .. myNewProject
$ cd myNewProject
$ pwd
/Users/calvinwebster/projects/myNewProject
```
#### 2. Once you've navigated to your new project folder, you'll want to create a new (but empty) git repository

```zsh
$ git status
fatal: Not a git repository (or any of the parent directories): .git

$ git init
Initialized empty Git repository in /Users/calvinwebster/projects/myNewProject/.git/

$ git status
On branch master

Initial commit

nothing to commit (create/copy files and use "git add" to track)

```

#### 3. Now that you have an empty git repository, you can start creating files and writing code.  When you're at a good stopping point, go ahead and add and commit those changes to the git repository.

```zsh
$ touch index.html styles.css

$ ls -a
. .. .git index.html styles.css

$ git status
On branch master

Initial commit

Untracked files:
(use "git add <file>..." to include in what will be committed)

index.html
styles.css

nothing added to commit but untracked files present (use "git add" to track)

$ git add .

$ git status
On branch master

Initial commit

Changes to be committed:
(use "git rm --cached <file>..." to unstage)

new file:   index.html
new file:   styles.css

$ git commit -am 'my first commit message'
[master (root-commit) ac7e403] my first commit message
2 files changed, 0 insertions(+), 0 deletions(-)
create mode 100644 index.html
create mode 100644 styles.css

$ git status
On branch master
nothing to commit, working directory clean

```

### Adding a remote and pushing to Github

#### Once you have created a repository on your computer and are ready to `push` it to github

- First, you must create a repo on github
![New github repo](https://raw.githubusercontent.com/TIY-Charleston-Front-End-May2015/notes/master/assets/newGHRepo.png)
- Once the new repository is created, github actually gives you really great instructions on how to proceed and `git push` your repo from your computer to github.com
![New Repo Instructions](https://raw.githubusercontent.com/TIY-Charleston-Front-End-May2015/notes/master/assets/ghDirections.png)

```sh
$ git remote add origin git@github.com:username/myNewProject.git

$ git push -u origin master

```


## Resources

[Learn Layout](http://learnlayout.com/)

[HTML tag content categories](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories)

[Try Github](https://try.github.io/levels/1/challenges/1)

[Setting up SSH Keys for Github](https://help.github.com/articles/generating-ssh-keys/)
