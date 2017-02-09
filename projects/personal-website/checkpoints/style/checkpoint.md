# Personal Website Checkpoint II: Style

Improve the look and feel of your static website.

## Objectives

  1. Gain familiarity with HTML and CSS.
  * Configure in-line, internal, and external CSS stylesheets.
  * Leverage a front-end web development framework.

## Prerequisites

  1. [Personal Website Checkpoint I: Structure](/projects/personal-website/checkpoints/structure/checkpoint.md)

## Instructions

Start with a simple `index.html` file similar to the example below:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Hello | My Site</title>
  </head>
  <body>
    <h1>Hello World</h1>

    <p>Welcome to my site.</p>

    <div>
      <p>Some paragraph text here!</p>

      <ol>
        <li>One</li>
        <li>Two</li>
        <li>Three</li>
      </ol>

      <p>Some more text at the bottom.</p>
    </div>
  </body>
</html>
````

Reference http://www.w3schools.com/css/default.asp for CSS guidance. Try adding different inline style declarations and then preview how they look when applied in the browser.

Once you have chosen a variety of styles, try acheiving the same styles using different methods of configuring your style declarations. Reference http://www.w3schools.com/css/css_howto.asp and the example instructions below for guidance on how to configure stylesheets.

### Inline Styles

Configure your `index.html` page to use inline CSS styles. Refer to the following example, below:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Hello | My Site</title>
  </head>
  <body>
    <h1 style="font-size:48px; color: red;">Hello World</h1>

    <p style="font-family: monospace; color: '#ccc';">Welcome to my site.</p>

    <div style="border: 2px solid #000;">
      <p style="font-family: monospace; color: '#ccc';">Some paragraph text here!</p>

      <ol style="list-style:none;">
        <li style="display: inline;">One</li>
        <li style="display: inline;">Two</li>
        <li style="display: inline;">Three</li>
      </ol>

      <p style="font-family: monospace; color: 'red';">Some more text at the bottom.</p>
    </div>
  </body>
</html>
````

You'll note this looks messier than the original version. The styles are mixed-in with the structure, and neither is easy to distinguish from the other at a glance.

You'll also note repetition of declarations (e.g. "display: inline;" declared on multiple `li` elements, and "font-family: monospace;" applied to multiple `p` elements).

We can simplify these repetitious and distracting style declarations by abstracting them into a single stylesheet.

### Internal Stylesheet

Configure your `index.html` page to use an internal stylesheet.

When moving from inline styles to a stylesheet, collect all your style declarations in one place, and use references known as "selectors" to specify which elements to apply the style declarations. See http://www.w3schools.com/cssref/css_selectors.asp for more information about combinations of CSS selectors. Three common selection methodologies are to reference the element by its type (e.g. `div`), reference the element by its `id` attribute value (e.g. `div#some-unique-identifier` or simply `#some-unique-identifier`), or reference the element by one of its `class` attribute values (e.g. `div.some-shared-identifier` or simply `.some-shared-identifier`).

> NOTE: No two elements on the same page should share an `id` attribute value, whereas it is common for multiple elements on the same page to share a `class` attribute value. Both `id` and `class` attributes are used to identify and classify elements.

> NOTE: In case you end up using both an internal stylesheet and inline styles, the inline style declarations override the internal stylesheet declarations. Also, declarations that come later than others may override previous, related declarations. Be careful!

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">

    <title>Hello | My Site</title>

    <style media="screen">

      h1 {
        font-size:48px;
        color: red;
      }

      p {
        font-family: monospace;
        color: '#ccc';
      }

      div#my-divider {
        border: 2px solid #000;
        height: 300px;
        width: 300px;
      }

      ol { list-style:none; }

      li.horizontal { display: inline; }

      .bottom { color:red; }

    </style>
  </head>
  <body>
    <h1>Hello World</h1>

    <p>Welcome to my site.</p>

    <div id="my-divider">
      <p>Some paragraph text here!</p>

      <ol>
        <li class="horizontal">One</li>
        <li class="horizontal">Two</li>
        <li class="horizontal">Three</li>
      </ol>

      <p class="bottom">Some more text</p>
    </div>
  </body>
</html>
````

Notice, there's still a lot going on in this simple `index.html` file. We open the file to see multiple lines of style declarations at the top, and not until we scroll down do we start to understand the structure of this HTML file.

We can simplify our view by even further separating the style declarations.

### External Local Stylesheet

Configure your `index.html` page to use an external stylesheet located in the same directory.

First create a new CSS file called in the same directory as your `index.html` file, but nest it inside one or more subdirectories (e.g. `assets/styles/my-style.css`). Then move all of the existing style declarations into it:

```` css

/* THIS IS MY EXTERNAL STYLESHEET */

h1 {
  font-size:48px;
  color: red;
}

p {
  font-family: monospace;
  color: '#ccc';
}

div#my-divider {
  border: 2px solid #000;
  height: 300px;
  width: 300px;
}

ol { list-style:none; }

li.horizontal { display: inline; }

.bottom { color:red; }

````

Finally, in the `head` of your original `index.html` file, change the `style` element to a `link` element, and configure its `href` attribute value to point to the location of the new external stylesheet:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Hello | My Site</title>
    <link rel="stylesheet" type="text/css" href="assets/styles/my-style.css">
  </head>
  <body>
    <h1>Hello World</h1>

    <p>Welcome to my site.</p>

    <div id="my-divider">
      <p>Some paragraph text here!</p>

      <ol>
        <li class="horizontal">One</li>
        <li class="horizontal">Two</li>
        <li class="horizontal">Three</li>
      </ol>

      <p class="bottom">Some more text</p>
    </div>
  </body>
</html>
````

Much better! This is cleaner to read, and may be easier to avoid mistakes when editing in the future.

### External Hosted Stylesheet

Configure your HTML page to use an external hosted stylesheet, specifically Twitter Bootstrap.

Refer to http://getbootstrap.com/getting-started/#download-cdn for guidance.

### Style

Use Twitter Bootstrap to style your site as desired!

Commit and push your changes when finished.
