## Add a new page

To add a new page to your web app, you create a new **route**.

--- collapse ---
---
title: What is a route?
---

In the code you already have, there is a single route:

```python
@app.route('/')
def index():
    return 'Hello world'
```

This route is made up of three parts:

- `@app.route('/')`: what you add to the web address to access this route - `/`
- `def index()`: the name of the route - `index`
- `return 'Hello world'`: the contents the user will see - `Hello world`

--- /collapse ---

--- task ---

Add the code for a new route to `app.py` and **save** the file.

##
--- code ---

language: python
line_numbers: true
line_number_start: 5
line_highlights: 9-11
----------------------------------------------------------

@app.route('/')
def index():
return 'Hello world'

@app.route('/cakes')
def cakes():
return 'Yummy cakes!'

--- /code ---

--- /task ---

--- task ---

In the **Chromium web browser**, type `localhost:5000/cakes` in the address bar.

You should see a web page with the text "Yummy cakes!" on it.

![Yummy Cakes](images/flask-cakes.png)

--- /task ---
