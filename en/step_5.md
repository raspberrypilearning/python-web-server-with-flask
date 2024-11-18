## Use CSS styles

**Cascading Style Sheets (CSS)** are rules to tell a browser how to display HTML content.

--- task ---

Go to the **terminal** and press <kbd>Ctrl</kbd> + <kbd>C</kbd> again to stop the flask server.

Make sure you are in the `webapp` directory using this command:

--- code ---
---
language: bash
line_numbers: false
---
cd ~/Documents/webapp/templates/
--- /code ---

--- /task ---

--- task ---

Create a new directory called `static`.

--- code ---
---
language: bash
line_numbers: false
---
mkdir static
--- /code ---

--- /task ---

--- task ---

Go back to **Thonny** and create a new file. Save this file as `style.css` inside your `static` folder.

--- /task ---

--- task ---

Add the following CSS rules to `style.css` then **save** the file. This is your stylesheet.

--- code ---
---
language: css
line_numbers: true
---
body {
    background: red;
    color: yellow;
}
--- /code ---

--- /task ---

--- task ---

Now modify your `index.html` HTML template to include the CSS rules by adding a `<head>` tag containing a `<link>` tag with a reference to the style sheet file:

```html
<html>
<head>
<link rel="stylesheet" href='/static/style.css' />
</head>
<body>
<h1>My website</h1>
</body>
</html>
```

--- /task ---

--- task ---

Save the change to `index.html` and refresh your browser. You should see a colourful version of your web app!

![Flask app with colour](images/flask-app-with-colour.png)

--- /task ---

If your web app doesn't look right, your CSS file might not be in the right directory.

You now have a number of files and directories for your web app. It is worth making sure your `webapp` project directory contains the following files and has the following structure:

```
├── app.py
├── static
│   └── style.css
└── templates
    └── index.html
    └── cakes.html
```
