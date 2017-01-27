# Website from Scratch

Create your own static website and publish it online.

## Objectives

  1. Configure a local development environment to include a text editor, a web browser, a local web server, and a version control client.
  * Use a text editor to create and manage programmatic files.
  * Gain familiarity with HTML and CSS.
  * Use in-line and internal CSS stylesheets.
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

Create a new directory on the Desktop called "my-site", or choose another name and/or location as long as you remember it.

### New HTML File

Open your text editor, and use it to create a new file in that directory called `index.html`.

Edit the `index.html` file to include basic html page structure (`head`, `body`, etc.), leveraging your text editor's auto-completion functionality as applicable. Save the file.

### Local Web server

From the command line, navigate to the directory. For example:

```` sh
cd ~/Desktop/my-site # (Mac Terminal)

cd C:\Users\YOUR_USERNAME/Desktop/my-site # (Windows Command Prompt), where YOUR_USERNAME is the user name associated with the operating system account you use on your local machine
````

After navigating to your directory, start a local web server on port 8888. For example:

```` sh
python –m http.server 8888
````

Visit [localhost:8888](localhost:8888) in a browser to view your page.

### Version Control

Initialize a git repository in your directory by leveraging a GUI or command-line Git client.

Commit your changes.

### Hosting

Create a new repository on GitHub, and note its remote address.

Configure your local directory to include the remote address of your GitHub repository.

Push your changes to GitHub.

Configure GitHub Pages hosting, publish your website, and view it online.

### Iterate

Expand the HTML structure of your website to resemble the HTML structure of https://prof-rossetti.github.io/student-site/, but use your own content.

Refer to http://www.w3schools.com/html/default.asp for HTML guidance.

As you develop your website, use an iterative approach, focusing on small tasks one at a time,  and commit your changes after completing each. Push your changes to the remote repository somewhat less frequently, at least once more before you are done.
