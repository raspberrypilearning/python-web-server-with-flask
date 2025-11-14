## Vytvoř HTML šablonu

Styl stránky můžeš upravit pomocí **šablony**. Šablona bude používat **HyperText Markup Language (HTML)**.

--- task ---

Přejdi do terminálu a stiskni <kbd>Ctrl</kbd> + <kbd>C</kbd> pro zastavení Flask serveru.

--- /task ---

--- task ---

Vytvoř adresář `templates` ve tvém adresáři `webapp`:

--- code ---
---
language: bash
line_numbers: false
---
mkdir templates

--- /code ---

--- /task ---

--- task ---

Vrať se do **Thony** a vytvoř nový soubor. Ulož tento soubor jako `index.html` do složky `templates`.

--- /task ---

--- task ---

Přidej tento kód do souboru `index.html` a **ulož** změny.

--- code ---
---
language: html
line_numbers: true
---

<html>
<body>
<h1>Moje webová stránka</h1>
</body>
</html>

--- /code ---

![Nový soubor s názvem index.html obsahující výše uvedený kód](images/html-file.png)

--- /task ---

--- task ---

--- /task ---

--- task ---

Vrať se do souboru `app.py` a změň první řádek kódu:

--- code ---
---
language: python
line_numbers: true
---

from flask import Flask, render_template

--- /code ---

--- /task ---

--- task ---

Změň trasu `index()` tak, aby používala tvou HTML šablonu `index.html`:

--- code ---
---
language: python
line_numbers: true
line_number_start: 5
line_highlights: 7
---

@app.route('/')
def index():
    return render_template('index.html')

--- /code ---

--- /task ---

--- task ---

Ulož soubor `app.py` a poté se vrať do terminálu a spusť jej pro restartování serveru:

--- code ---
---
language: bash
line_numbers: false
---

python3 app.py

--- /code ---

--- /task ---

--- task ---

V prohlížeči **Chromium** přejdi na stránku `localhost:5000/` a zobrazí se ti nová HTML šablona.

![Webový prohlížeč ukazoval na localhost:5000 s textem „Moje webová stránka“ velkým písmem v záhlaví](images/flask-template.png)

--- /task ---

