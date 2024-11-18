## Challenge: add a HTML template to the second page

Now you know how to change your 'index' page to use a HTML template, make your 'cakes' page use a HTML template too!

--- hints ---

--- hint ---

Repeat the steps in the previous project section to create and use a HTML template for the 'cakes' page.

--- /hint ---

--- hint ---

Create a `cakes.html` file and save it in `templates`.

Modify the `cakes()` function in `app.py` to use `render_template`.

--- /hint ---

--- hint ---

Your `cakes.html` template should look this:

```html
<html>
<body>
<h1>Yummy cakes!</h1>
</body>
</html>
```

Modify the `cakes()` function in `app.py`:

```python
@app.route('/cakes')
def cakes():
    return render_template('cakes.html')
```

--- /hint ---

--- /hints ---
