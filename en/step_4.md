## Return HTML web pages

Next, you'll modify your existing routes to return a full HTML web page rather than just simple text.

The HTML web page will be created from a **template** that holds the static content of the page. In a later section of this project, you'll learn how to insert data to create a dynamic version of the page.

--- task ---

First, create a `templates` directory in your `webapp` directory by entering the following command into the terminal or command prompt window:

```bash
mkdir templates
```

--- /task ---

--- task ---

Create a new file in IDLE by clicking **File** and **New File**, and save this file as `index.html` in your `templates` folder.

--- /task ---

--- task ---

Enter the following HTML code in `index.html`:

```html
<html>
<body>
<h1>My website</h1>
</body>
</html>
```

![idle html](images/idle-html.png)

--- /task ---

--- task ---

Save your changes by clicking **File** and **Save**, or by pressing <kbd>Ctrl</kbd> and <kbd>s</kbd>. 

--- /task ---

--- task ---

Return to your `app.py` file in IDLE, and modify the first line of your code to import the `render_template` function from the `flask` module as well:

```python
from flask import Flask, render_template
```

--- /task ---

--- task ---

Finally, modify your `index()` function to return the `index.html` HTML template instead of the normal text. Change the code inside the definition so that the code looks like this:

```python
@app.route('/')
def index():
    return render_template('index.html')
```

This code makes Flask look for `index.html` in the `templates` directory that the `app.py` program is in.

--- /task ---

--- task ---

Save the file. Make sure your `app.py` program is still running. If it's not, just run it again using the terminal/command prompt.

--- /task ---

--- task ---

Load the `http://127.0.0.1:5000/` page in your web browser to see your new HTML template displayed.

![my website](images/flask-template.png)

In this case what you see is not much different, because the only new thing is a HTML header. There's plenty of scope to add other things!

--- /task ---

