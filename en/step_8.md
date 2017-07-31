## Adding colour to the web page with CSS

Cascading Style Sheets (CSS) are rules for how HTML content is displayed by the browser. Now you'll add some CSS to add colour to your web page.

- First, return to the Terminal window and navigate to the `webapp` directory. If you're in the `templates` directory, go back up one level with `cd ..`.

- Create a new directory called `static`.

- Then open a new window with the basic text editor (Leafpad), or re-open the text editor from the menu.

- Save the new file as `style.css` in the new `static` directory.

- Add the following CSS rules to the file:

    ```css
    body {
        background: red;
        color: yellow;
    }
    ```
    
    Note here we've used colour names: usually colours are defined by hex codes like `#ff0000` (red) but this is a simple example.

- Save the file.

- Now modify your HTML template called `index.html` to include the CSS file, by adding a `<head>` tag containing a `<link>` tag with a reference to the stylesheet:

    ```html
    <html>
    <head>
    <link rel="stylesheet" href='/static/style.css' />
    </head>
    <body>
    <h1>Hello from a template!</h1>
    </body>
    </html>
    ```

- Save the HTML file and reload the web server. You should see a colourful version of the web app!

    ![Flask app with colour](images/flask-app-with-colour.png)

You have so far created a number of files and directories. It is worth just double-checking your `webapp` project directory, which should contain the following and have a structure like this now:

```
├── app.py
├── static
│   └── style.css
└── templates
    └── index.html
```

If your web app doesn't look right, check you saved your CSS file in the right place.

