## Challenge: Add a HTML template to your 2nd page

Now you have changed your `index` page to use a HTML template now do the same for your `cakes` page?

--- hints ---

--- hint ---

Repeat the same process to create the index template for the cakes page.

--- /hint ---

--- hint ---

Create a `cakes.html` file and save it in `templates`.

Modify the `cakes()` function in `app.py` to use `render_template`.

--- /hint ---

--- hint ---

Create a `cakes.html` files and save it in `templates` with the code:

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