## Add a new page

Now you're going to add a new page to your web app by creating a new **route**.

In a web application, a route is a certain path into your website, determined by the URL the user types into their web browser's address bar. You create the routes and determine what each route does.

In the code you already have in `app.py`, there is a single route:

```python
@app.route('/')
def index():
    return 'Hello world'
```

This route is made up of three parts:

- `@app.route('/')`: this determines the entry point; the `/` means the root of the website, so `http://127.0.0.1:5000/`
- `def index()`: this is the name you give the route, in this case `index`, because it's the index (or homepage) of the website
- `return 'Hello world'`: this is the content of the web page, which is returned when the user goes to this URL

The second half of the `app.py` code runs the web server and your app:

```python
if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```

**Note:** the `host='0.0.0.0'` means the web app is accessible to any device on the network.

The following instructions show how to create a new page and route called 'cakes'. If you want, you can change the name and and the content to be whatever you wish.

--- task ---

To create a new page and a route to it, add these lines of code below where the first page and route are created in `app.py`:

```python
@app.route('/cakes')
def cakes():
    return 'Yummy cakes!'
```

--- /task ---

--- collapse ---

---
title: Complete code
---

Your complete code should now look similar to this:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello world'

@app.route('/cakes')
def cakes():
    return 'Yummy cakes!'

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```

--- /collapse ---

--- task ---

Save your code and navigate to the 'cakes' page in the browser at the address `127.0.0.1:5000/cakes`. You should see a web page with the text "Yummy cakes!" on it.

![Yummy Cakes](images/flask-cakes.png)

--- /task ---
