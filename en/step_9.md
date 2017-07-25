## Adding dynamic content to a view

So far you've learned to deliver HTML template through a web server running on your Raspberry Pi. Wouldn't it be good if you could add some dynamic content to the pages to display different information? Large websites like Facebook, YouTube and BBC News show different content depending on the route you visit, even though the templates are very similar.

Now you'll create a new route on your website so that when you go to `http://127.0.0.1/hello/name`, it will say "Hello name!" and replace 'name' with whatever you put there; so `/hello/Paul/` will display "Hello Paul!".

- Create a new route in your application like so:

    ```python
    @app.route('/hello/<name>')
    def hello(name):
        return render_template('page.html', name=name)
    ```

    - `@app.route('/hello/<name>')` - the `<name>` part means it passes the name into the `hello` function as a variable called `name`
    - `def hello(name)` - this is the function that determines what content is shown - this time it takes the given name as a parameter
    - `return render_template('page.html', name=name)` - here we look up the template `page.html` and pass in the variable `name` from the URL, so the template can use it

- Create a new HTML template called `page.html` using the text editor, and add the following HTML code to it:

    ```html
    <h1>Hello {{ name }}!</h1>
    ```
    
    Note here we've neglected the `<html>` and `<body>` tags. This is OK for testing but real websites should have a full HTML structure.

- Save the files, reload the web server and visit `http://127.0.0.1:5000/hello/paul`. It should look like this:

    ![Hello Paul!](images/flask-hello-paul.png)

    Try it with different names!

### What's happening here?

Flask uses `jinja`, a Python library for rendering templates. Use the braces (curly brackets) on this line:

```html
<h1>Hello {{ name }}!</h1>
```

It tells the template to render the variable `name` which was passed in the route function `hello`.

What happens when you just visit `127.0.0.1:5000/hello/` without a name? Think about how you can prevent this giving an error.

