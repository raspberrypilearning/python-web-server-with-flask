# Build a Web Server with Python Flask

Setting up the Raspberry Pi and installing the required libraries

When starting up the Raspberry Pi, note the IP address of the device. This will appear just before the login screen. Alternatively, if your Pi is set to boot straight into the GUI: open a terminal window and type:

```bash
ifconfig
```

This task can be performed in the terminal or with the GUI, nearly all the work will be done on the terminal command line. This scheme assumes you are using the GUI and a terminal window.

To install the Python Flask library you'll have to install `pip`. This can be done on the terminal with the code:

```bash
sudo apt-get install python-setuptools && easy_install pip
```

Now we can use pip to install Flask (on the terminal, again):

```bash
sudo apt-get install python-flask
```

Flask will now be installed and will be ready to use.

## Building a basic Flask web application

This task will show you how to set up the most basic web application with Flask and Python. You will be able to run a single web page and display some text on a web browser. You must have followed the setup steps shown above.

Open a terminal window and create a new folder in your document called `webapp`:

```bash
mkdir webapp
```

Navigate into this directory using the cd command:

```bash
cd webapp
```

Flask applications can be run from a single file. Let's create the file now using touch:

```bash
touch app.py
```

This will create a file named app.py, in which all our application code will be written.

You can now open this file in a text editor of your choice, or use the terminal editor nano, in order to write the first lines of code needed to set up Flask. We'll use nano to load the file:

```bash
sudo nano app.py
```

(note you'll need to use `sudo` with `nano` to ensure you have write permissions.)

Now let's write the basic Flask application code. We'll explain this line-by-line afterwards:

```python
from flask import Flask

app = Flask(__name__)


@app.route('/')
def index():
    return 'Hello Raspberry Pi!'

if __name__ == '__main__':
    app.run(debug=True)
```

In nano; we can save the file using `Ctrl + X` then by typing `y` and pressing `Enter`, otherwise save it through the standard way of your text editor.

The last step to run this now is to use Python in the terminal to run the file:

```bash
python app.py
```

If everything has been written correctly, you should see an output similar to this:

 - Running on `http://127.0.0.1:5000/`
 - Restarting with reloader

Finally: go to a web browser and navigate to the url address shown above (`http://127.0.0.1:5000/`) on the Raspberry Pi to see the content `Hello Raspberry Pi!` displayed.
If you are using SSH, or want to view this on a separate computer on the same network: type in the ip address followed by `:5000` to view the web page (for example: IP address `192.168.1.1:5000`).

Explaining the basic Flask code

Now that we've set up a simple web server, let's figure out exactly what the code is doing. We'll do this by going line-by-line through the code we just wrote:

```python
from flask import Flask
```

This line of code is importing the Flask library into our Python application. If you're familiar with Python this is a common practice of adding third party libraries to your software.

```python
app = Flask(__name__)
```

This line is a little complex, but we're basically creating an object called app, which is an instance of a Flask application, and we're passing in a variable called `__name__`.

Where does `__name__` come from? It is a global constant variable used by Python to define who is currently running this file. We'll use this again further down in the code, which will help explain it a bit better. For now: remember that Python defines it.

```python
@app.route('/')
def index():
    return 'Hello Raspberry Pi!'
```

This is the most interesting part of the code for us: this is how we create new URLs in our web application. The first line `@app.route('/')` tells us:

when we visit this route on our web server: run this function below.

It is a decorator, a fairly complex concept in Python: a function that returns a function. We don't need to learn exactly how it works today, just that we need one for each new route that we want to create.

```
if __name__ == '__main__':
	app.run(debug=True)
```

These final lines tell Python to run the application if `__name__` is `__main__`, in other words: if you're running the file in the command line.

## Adding a new route to your web app

Let's add a new route to our web app.

Underneath the first route, which is this code:

```python
@app.route('/')
def index():
    return 'Hello Raspberry Pi!'
```

We can create a new route:

```python
@app.route('/cakes')
def cakes():
    return 'Yummy cakes!'
```

Now navigate to you server (127.0.0.1:5000) and add /cakes to the end, like this:

```
127.0.0.1:5000/cakes
```

to see the new route.

### Extra student tasks:

Test what the students have learned by getting them to add their own route to the application and demonstrating it to you.

Add html templates to your web app

Returning plain text is pretty boring, there are plenty of complicated and impressive websites on the web that use html. This next task will show you how to use a html template in your web application.

The first step is to import the template renderer. Modify the first line of code to look like this (new code is highlighted in blue):

```python
from flask import Flask, render_template
```

The `render_template` object is used by Flask to help render html templates.

Next we'll need to modify our basic view to return a html template instead of the normal text, change the `index()` function to this (new code in blue):

```python
@app.route('/')
def index():
    return render_template('index.html')
```

But wait! This won't work because the template doesn't exist yet. We'll have to make one:

Flask will look in a directory called templates in the same directory as the `app.py` file to find these, so create a directory called templates in the webapp directory. This can be done with the terminal using the command:

```bash
mkdir templates
```

Then we can use touch to create a new template:

```bash
touch index.html
```

Open the file with nano (or your text editor of choice) and add some html:

```html
<!DOCTYPE html>
<html>
  <body>
    Hello from a template!
  </body>
</html>
```

Save this file and reload the route in your web browser (`127.0.0.1:5000/`) to see your new html template being displayed.

### Extra student tasks:

Modify the html template to include images, styling and some content.
Add a new template to an existing or new view.
Create `<a>` tags in html to link between the two views.

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
