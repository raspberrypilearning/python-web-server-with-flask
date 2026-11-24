## Udfordring: tilføj en HTML template til den anden side

Nu ved du hvordan du ændrer din 'index' side til at bruge en HTML template, prøv nu at få din 'cakes' side til også at bruge HTML template!

--- hints ---

--- hint ---

Gentage skridtene i den tidligere projekt sektion til at lave og bruge en HTML template for 'cakes' siden.

--- /hint ---

--- hint ---

Lav en `cakes.html` fil og gem den i `templates`.

Modificer `cakes()` funktionen i `app.py` til at bruge `render_template`.

--- /hint ---

--- hint ---

Din `cakes.html` template burde se sådan her ud:

```html
<html>
<body>
<h1>Yummy cakes!</h1>
</body>
</html>
```

Modificer `cakes()` funktionen i `app.py`:

```python
@app.route('/cakes')
def cakes():
    return render_template('cakes.html')
```

--- /hint ---

--- /hints ---
