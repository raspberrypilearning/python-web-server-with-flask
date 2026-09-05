## Use CSS styles

**Cascading Style Sheets (CSS)** are rules to tell a browser how to display HTML content.

\--- task ---

Open a new terminal window, so that you can leave the Flask web server running in the other one.

\--- /task ---

\--- task ---

Make sure you are in the `webapp` directory using this command:

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

cd ~/Documents/webapp

\--- /code ---

\--- /task ---

\--- task ---

Create a new directory called `static`.

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

mkdir static

\--- /code ---

\--- /task ---

\--- task ---

Go back to **Thonny** and create a new file. Save this file as `style.css` inside your `static` folder.

\--- /task ---

\--- task ---

Add the following CSS rules to `style.css` then **save** the file. This is your stylesheet.

## --- code ---

language: css
line_numbers: true
-------------------------------------------------------

body {
background: beige;
color: blue;
}

\--- /code ---

\--- /task ---

\--- task ---

Now modify your `index.html` HTML template to include the CSS stylesheet:

## --- code ---

language: css
line_numbers: true
line_number_start: 1
line_highlights: 2-4
---------------------------------------------------------

<html>
<head>
<link rel="stylesheet" href="/static/style.css" />
</head>
<body>
<h1>My website</h1>
</body>
</html>

\--- /code ---

\--- /task ---

\--- task ---

Save the changes to `index.html` then go back to **Chromium** and refresh the browser. You should see a colourful version of your web app!

![Flask app with colour](images/flask-app-with-colour.png)

\--- /task ---

## --- collapse ---

## title: I can't see the colours

If your web app doesn't look right, your CSS file might not be in the right directory.

Make sure your `webapp` project directory contains the following files and has the following structure:

```
├── app.py
├── static
│   └── style.css
└── templates
    └── index.html
    └── cakes.html
```

\--- /collapse ---