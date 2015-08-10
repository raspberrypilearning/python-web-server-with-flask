# Build a Web Server with Python Flask

Installing the lightweight Python web framework Flask and setting up a basic web server.

## Installing pip and Flask

First you're going to find your Raspberry Pi's IP address and install the Flask package.

1. Start by opening a Terminal window from the taskbar or applications menu:

    ![](images/open-terminal.png)

1. Enter the following command in the Terminal to find your Raspberry Pi's IP address:

    ```bash
    hostname -I
    ```

    *This is your Raspberry Pi's IP address on the local network. If you don't see anything then make sure you're connected to the Internet.*

1. Next, you'll need to install `pip` with the following command:

    ```bash
    sudo apt-get install python-pip
    ```

    *`pip` is a tool for installing Python packages from the Python Packaging Index (PyPi) - you can browse packages at [pypi.python.org](https://pypi.python.org/).*

1. Now use `pip` to install Flask:

    ```bash
    sudo pip install flask
    ```

## Building a basic Flask web application

Now you're going to set up the most basic web application with Flask and Python. You will be able to run a single web page and display some text on a web browser.

1. Return to the Terminal window and create a new folder in your document called `webapp`:

    ```bash
    mkdir webapp
    ```

    *`mkdir` means "make directory" - a directory is a folder, it can contain files and more folders.*

1. Navigate into this directory using the `cd` command:

    ```bash
    cd webapp
    ```

    *`cd` means "change directory" - you use it to enter a folder*

1. Flask applications can be run from a single file. Now create the file now using touch:

    ```bash
    touch app.py
    ```

    *This will create a file named `app.py`, in which all our application code will be written.*

1. Enter the following command to open this file in IDLE, the Python editor, in order to get started writing your web app:

    ```bash
    idle app.py &
    ```

    *The ampersand (&) on the end of this command tells it to open IDLE in a new process. Unlike a command like `cd`, this command doesn't "finish" until you close the IDLE window. Opening IDLE in a new process allows you to enter more commands into the Terminal without quitting IDLE.*

1. Two windows will have opened. One is the Python shell, and the other is an empty window with `app.py` in the title bar. Click on the `app.py` window to focus on it. You'll write your application code here and any printed messages or errors will be shown in the Python shell.

1. Now enter the following lines into the blank `app.py` window:

    ```python
    from flask import Flask

    app = Flask(__name__)


    @app.route('/')
    def index():
        return 'Hello world'

    if __name__ == '__main__':
        app.run(debug=True)
    ```

1. Save the file with `Ctrl + S` and run with `F5`. Your web server is now running!

    If everything has been written correctly, you should see an output similar to this:

    ```
    - Running on `http://127.0.0.1:5000/`
    - Restarting with reloader
    ```

1. Open the Pi's web browser from the taskbar or application menu and enter `http://127.0.0.1:5000/` - you should see a white screen with the words `Hello world`:

    ![](images/flask-hello-world.png)

    ```python
    @app.route('/')
    def index():
        return 'Hello world'
    ```

## Adding a new route to your web app

Now you're going to add a new route to your web app, which will create another web page.

1. In a web application, a route is a certain path into your website - determined by the request sent by the user when they type it into their web browser. It's up to you which routes are enabled, and what each of them does.

    In the "Hello Raspberry Pi" example we used a single route:

    ```python
    @app.route('/')
    def index():
        return 'Hello world'
    ```

    This route is page up of three parts:

        1. `@app.route('/')` - this determines the entry point; the `/` means the root of the website, so just `http://127.0.0.1:5000/`.
        1. `def index()` - this is the name we give to the route - here it was called `index` because it's the index of the website.
        1. `return 'Hello world'` - this is the content of the web page which is returned when the user browses the index of the website.

1. Create a new route by adding the following lines below the first route:

    ```python
    @app.route('/cakes')
    def cakes():
        return 'Yummy cakes!'
    ```

1. Now navigate to your website's cake page in the browser at `127.0.0.1:5000/cakes`. You should see a webpage with the text `Yummy cakes!` on it:

    ![](images/flask-cakes.png)

### Add HTML templates to your web app

Next you'll modify your existing routes to return full HTML templates rather than simple text strings.

1. First create a `templates` folder in your `webapp` folder by entering this into the Terminal:

    ```bash
    mkdir templates
    ```

1. Then use `touch` to create a new template file:

    ```bash
    touch index.html
    ```

1. Return to the IDLE window and click `File > Open` and navigate to your `index.html` file. Open it and add some HTML:

    ```html
    <html>
        <body>
            <h1>Hello from a template!</h1>
        </body>
    </html>
    ```

1. Return to your `app.py` file in IDLE and modify the first line of your code to import the `render_template` function as well:

    ```python
    from flask import Flask, render_template
    ```

1. Finally you'll need to modify your index view to return the HTML template instead of the normal text. Change the `index()` function to this:

    ```python
    @app.route('/')
    def index():
        return render_template('index.html')
    ```

    *Flask will look for `index.html` in a directory called `templates` in the same directory as the `app.py` file.*

1. Save all file and reload the route in your web browser (go to the base route at `http://127.0.0.1:5000/`) to see your new HTML template being displayed.

    ![](images/flask-header.png)

    *In this case it's not much different as all you've done is added a header - but there's plenty of scope to expand!*

## Adding colour to the web page with CSS

Cascading Style Sheets (CSS) are rules for how HTML content is displayed by the browser. Now you'll add some CSS to add colour to your web page.

1. First,









## Adding dynamic content to a view

So far you've learned to deliver html template through a web server running on your Raspberry Pi. Wouldn't it be cool if you could add some dynamic content to the pages so it displayed different information? It would indeed! Large websites like Facebook, Youtube and BBC news show different content depending on the route you visit, even though the templates are very similar.

Let's create a new route on our website so that when we go to `127.0.0.1/hello/name` it will say "Hello name!" and replace name with whatever we put there. So `/hello/Paul/` will display "Hello Paul!"

Create a new route in your application like so:

```python
@app.route('/hello/<my_name>')
def name(my_name):
    return render_template('page.html', name=my_name)
```

We've highlighted the new parts in blue, let's figure out what's happening here:

```python
@app.route('/hello/<my_name>')
```

The route includes an extra routing parameter surrounded by angle brackets. Flask will pass this to the function just beneath the route as a function parameter:

```python
def name(my_name):
```

You can see in the function where we are passing the variable in as a parameter.

```
return render_template('page.html', name=my_name)
```

Finally, we're the variable passing it to the template (called page.html) to be rendered

There is one last thing we need to do: add the new variable into the html template

Create a new html template called page.html (see the previous tasks if you get stuck) and add the following html code to it:

```html
<!DOCTYPE html>
<h1>Hello {{ name }}!</h1>
```

Now: when you visit `127.0.0.1:5000/hello/paul` it should render this:

```
Hello paul!
```

Try it with different names to see it working.

What's happening here?

Flask uses `jinja`, a Python library for rendering templates. Using the curly braces on this line:

```html
<h1>Hello {{ name }}!</h1>
```

It tells the template to render the variable name which we passed in the route on this line of code (the highlighted part):

```python
return render_template('page.html', name=my_name)
```

### Extra Student tasks:

What happens when you just visit `127.0.0.1:5000/hello/` ? Check out the official documentation for hints on how to prevent errors.

Add parameters to a previous route to make other views dynamic.
