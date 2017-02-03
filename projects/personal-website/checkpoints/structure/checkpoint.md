# Personal Website Checkpoint I: Structure

Create your own static website and publish it online.

## Objectives

  1. Configure a local development environment to include a text editor, a web browser, a local web server, and a version control client.
  * Use a text editor to create and manage programmatic files.
  * Gain familiarity with HTML.
  * Practice software version control.
  * Practice website hosting.

## Prerequisites

  1. Install a [modern web browser](/README.md#browser), if necessary.
  * Install a [text editor](/README.md#text-editor), if necessary.
  * Register on [GitHub](https://github.com/), if necessary.
  * Install a [Git Client](https://git-scm.com/downloads).
  * Install a program which will allow you to run a local web server.

## Instructions

### New Directory

Create a new directory on the Desktop called "my-site", or choose another name and/or location as long as you remember it. You may either do this via user interface, or via the command line as follows:

```` sh
# Mac Terminal:
mkdir ~/Desktop/my-site

# Windows Command Prompt:
mkdir C:\Users\YOUR_USERNAME\Desktop\my-site # replace YOUR_USERNAME with the name of the user currently operating your local machine
````

### New HTML File

Open your text editor, and use it to create a new file in that directory called `index.html`. This can most likely be achieved with: "File > New", followed by "File > Save As". Alternatively, you may use the command line as follows:

```` sh
# Mac Terminal:
touch ~/Desktop/my-site/index.html

# Windows Command Prompt:
type nul > C:\Users\YOUR_USERNAME\Desktop\my-site\index.html
````

Edit the `index.html` file to include basic html page structure (`head`, `body`, etc.), leveraging your text editor's auto-completion functionality as applicable. If you are not using a text editor that possesses auto-completion functionality, consider switching text editors or leverage the following code snippet:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
  </head>
  <body>

  </body>
</html>
````

Save the file.

Insert some sample text inside the `title` tag. Also add an `h1` heading tag and sample text within it to display the top-level page heading. Your code should now resemble:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Hello World | A website by me</title>
  </head>
  <body>
    <h1>Welcome to My Site</h1>
  </body>
</html>
````

Save the file again.

### Local Web server

Its time to preview your file in a browser. To do so, you may simply right-click on the file and open it with a browser, but you are encouraged to use a local web server instead.

> NOTE: you must execute the command to run the local web server from inside the root directory which contains your index.html file!

From the command line, navigate to the directory. For example:

```` sh
# Mac Terminal:
cd ~/Desktop/my-site

# Windows Command Prompt:
cd C:\Users\YOUR_USERNAME\Desktop\my-site
````

After navigating to your directory, start a local web server on port 8888:

```` sh
# Mac Terminal:
python -m SimpleHTTPServer 8888 &

# Windows Command Prompt:
python –m http.server 8888
````

Finally, visit [localhost:8888](localhost:8888) in a browser to view your page.

### Version Control

Initialize a git repository in your directory by leveraging a GUI or command-line Git client.

Commit your changes.

### Hosting

Create a new repository on GitHub, and note its remote address.

Configure your local directory to include the remote address of your GitHub repository.

Push your changes to GitHub.

Configure GitHub Pages hosting, publish your website, and view it online.

### Iterate

Expand the HTML structure of your website as desired to meet project expectations. If you have not yet planned and designed your website, instead you may practice by expanding the HTML structure of your website to resemble that of https://prof-rossetti.github.io/student-site/, but using your own content.

Refer to http://www.w3schools.com/html/default.asp for HTML guidance.

As you develop your website, use an iterative approach, focusing on small tasks one at a time,  and commit your changes after completing each.

Push your changes to the remote repository somewhat less frequently, at least once more before you are done.

Nice Job! You are developing like a pro!
