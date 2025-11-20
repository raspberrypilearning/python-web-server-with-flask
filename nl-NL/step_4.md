## Een HTML-sjabloon maken

U kunt een **sjabloon** gebruiken om uw pagina een stijl te geven. De sjabloon maakt gebruik van **HyperText Markup Language (HTML)**.

--- task ---

Ga naar je terminal en druk op <kbd>Ctrl</kbd> + <kbd>C</kbd> om je Flask-server te stoppen.

--- /task ---

--- task ---

Maak een `templates`-map in uw `webapp`-map:

##
--- code ---

language: bash
line_numbers: false
--------------------------------------------------------

mkdir templates

--- /code ---

--- /task ---

--- task ---

Ga terug naar **Thomny** en maak een nieuw bestand. Sla dit bestand op als `index.html` in uw `templates`-map.

--- /task ---

--- task ---

Voeg deze code toe aan `index.html` en **sla** uw wijzigingen op.

##
--- code ---

language: html
line_numbers: true
-------------------------------------------------------

<html>
<body>
<h1>Mijn website</h1>
</body>
</html>

--- /code ---

![Een nieuw bestand genaamd index.html met de bovenstaande code](images/html-file.png)

--- /task ---

--- task ---

--- /task ---

--- task ---

Ga terug naar uw `app.py`-bestand en wijzig de eerste regel code:

##
--- code ---

language: python
line_numbers: true
-------------------------------------------------------

from flask import Flask, render_template

--- /code ---

--- /task ---

--- task ---

Wijzig de `index()`-route om uw `index.html` HTML-sjabloon te gebruiken:

##
--- code ---

language: python
line_numbers: true
line_number_start: 5
line_highlights: 7
-------------------------------------------------------

@app.route('/')
def index():
return render_template('index.html')

--- /code ---

--- /task ---

--- task ---

Sla `app.py` op en ga terug naar de terminal om het bestand uit te voeren en uw server opnieuw op te starten:

##
--- code ---

language: bash
line_numbers: false
--------------------------------------------------------

python3 app.py

--- /code ---

--- /task ---

--- task ---

Ga naar de pagina `localhost:5000/` in **Chromium** om uw nieuwe HTML-sjabloon te zien.

![Een webbrowser verwees naar localhost:5000 met de tekst 'Mijn website' in een groot koptekstlettertype](images/flask-template.png)

--- /task ---

