## Adding dynamic content

So far you've learned to deliver static HTML web pages using templates. Lets add some dynamic content to the pages to display different information. Large websites like Facebook, YouTube and BBC News show different content depending on the page you visit, even though the templates are very similar.

Now you'll create a new route on your website so that when you go to `http://127.0.0.1/hello/name`, it will say "Hello name!" and replace 'name' with whatever you put there; so `/hello/Paul/` will display "Hello Paul!".

--- task ---

Create a new route in your application like so:

```python
@app.route('/hello/<name>')
def hello(name):
    return render_template('page.html', name=name)
```

- `@app.route('/hello/<name>')` - the `<name>` part means it passes the name into the `hello` function as a variable called `name`
- `def hello(name)` - this is the function that determines what content is shown - this time it takes the given name as a parameter
- `return render_template('page.html', name=name)` - here we look up the template `page.html` and pass in the variable `name` from the URL, so the template can use it

--- /task ---

--- task ---

Create a new HTML template called `page.html`, and add the following HTML code to it:

```html
<html>
<body>
<h1>Hello {{ name }}!</h1>
</body>
</html>
```

--- /task ---

--- task ---

Save the files and visit `http://127.0.0.1:5000/hello/paul`. It should look like this:

![Hello Paul!](images/flask-hello-paul.png)

Try it with different names!

--- /task ---

--- collapse ---

---
title: What's happening here?
---

Flask uses `jinja`, a Python library for rendering templates. Using the braces (curly brackets) on this line:

```html
<h1>Hello {{ name }}!</h1>
```

... tells the template to render the variable `name` which was passed in the route function `hello`.

Visiting `127.0.0.1:5000/hello/` without a name will create an error. Think about how you can prevent this from happening.

--- /collapse ---

--- task ---

Create a link to your new dynamic hello page from your index.

Edit `index.html` to add a link to your new hello page under the heading.

```html
<h1>My website</h1>
<a href="/hello/paul">Hi Paul</a>
```

--- /task ---

--- task ---

Save your changes and refresh the index page to see the result.

![flask app link](images/flask-app-link.png)

--- /task ---
