## Přidej novou stránku

Chceš-li do webové aplikace přidat novou stránku, vytvoř novou **trasu**.

## --- collapse ---

## title: Co je to trasa?

V kódu, který již máš, je jedna trasa:

```python
@app.route('/')
def index():
    return 'Ahoj světe'
```

Tato trasa se skládá ze tří částí:

- `@app.route('/')`: co přidáš k webové adrese pro přístup k této trase - `/`
- `def index()`: název trasy - `index`
- `return 'Hello world'`: obsah, který uživatel uvidí - `Hello world`

\--- /collapse ---

\--- task ---

Přidej kód pro novou trasu do souboru `app.py` a soubor **ulož**.

## --- code ---

language: python
line_numbers: true
line_number_start: 5
line_highlights: 9-11
----------------------------------------------------------

@app.route('/')
def index():
return 'Ahoj světe'

@app.route('/dorty')
def dorty():
return 'Vynikající dorty!'

\--- /code ---

\--- /task ---

\--- task ---

V prohlížeči Chromium zadej do adresního řádku adresu `localhost:5000/cakes`.

Měl bys vidět webovou stránku s textem „Mňam dorty!“.

![Chutné dorty](images/flask-cakes.png)

\--- /task ---
