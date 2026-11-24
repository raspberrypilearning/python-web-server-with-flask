## Een nieuwe pagina toevoegen

Om een nieuwe pagina aan uw web-app toe te voegen, maakt u een nieuwe **route**.

--- collapse ---
---
title: Wat is een route?
---

In de code die u al hebt, is er één route:

```python
@app.route('/')
def index():
    return 'Hallo wereld'
```

Deze route bestaat uit drie delen:

- `@app.route('/')`: wat u toevoegt aan het webadres om toegang te krijgen tot deze route - `/`
- `def index()`: de naam van de route - `index`
- `return 'Hallo wereld'`: de inhoud die de gebruiker zal zien - `Hallo wereld`

--- /collapse ---

--- task ---

Voeg de code voor een nieuwe route toe aan `app.py` en **sla** het bestand op.

##
--- code ---

language: python
line_numbers: true
line_number_start: 5
line_highlights: 9-11
---

@app.route('/')
def index():
return 'Hallo wereld'

@app.route('/cakes')
def cakes():
return 'Lekkere taarten!'

--- /code ---

--- /task ---

--- task ---

Typ in de **Chromium webbrowser** `localhost:5000/cakes` in de adresbalk.

U zou een webpagina moeten zien met de tekst "Lekkere taarten!" erop.

![Lekkere taarten](images/flask-cakes.png)

--- /task ---
