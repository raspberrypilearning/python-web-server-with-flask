## Dynamische inhoud

Websites als Facebook, YouTube en BBC News hebben dynamische inhoud: deze websites tonen verschillende inhoud binnen dezelfde template.

Nu gaat u een nieuwe route op uw website aanmaken, zodat de pagina een persoonlijke begroeting toont.

\--- task ---

Open `app.py` en voeg een nieuwe route toe aan uw applicatie:

## --- code ---

language: python
line_numbers: true
line_number_start: 5
line_highlights: 9-11
----------------------------------------------------------

@app.route('/')
def index():
return render_template('index.html')

@app.route('/hello/<name>')
def hello(name):
return render_template('page.html', name=name)

\--- /code ---

\--- /task ---

\--- task ---

Maak een nieuwe HTML-sjabloon in de sjablonenmap met de naam `page.html` en voeg de volgende HTML-code eraan toe:

## --- code ---

language: html
line_numbers: true
-------------------------------------------------------

<html>
<body>
<h1>Hallo {{ name }}!</h1>
</body>
</html>

\--- /code ---

\--- /task ---

\--- task ---

Sla beide bestanden op en ga vervolgens naar `localhost:5000/hello/Paul` in de **Chromium-browser**.

De pagina die u ziet, zou er als volgt uit moeten zien:

![Een website die de tekst 'Hallo Paul!' weergeeft](images/flask-hello-paul.png)

Probeer `Paul` in de adresbalk te vervangen door een andere naam!

\--- /task ---

\--- task ---

Open uw `index.html`-sjabloon en voeg een link naar de hallo-pagina toe onder de kop.

## --- code ---

language: html
line_numbers: true
line_number_start: 6
line_highlights: 7
-------------------------------------------------------

<h1>Mijn website</h1><a href="/hello/paul">Hallo Paul</a>

\--- /code ---

\--- /task ---

\--- task ---

Sla de wijzigingen op in `index.html` en open vervolgens `localhost:5000` om de bijgewerkte versie te bekijken.

![Een website met blauwe tekst op een beige achtergrond. De tekst luidt 'Mijn website' in een koptekstlettertype en vervolgens een link naar 'Hoi Paul'](images/flask-app-link.png)

\--- /task ---

## --- collapse ---

## title: Hoe werkt deze route?

- `@app.route('/hello/<name>')`: het `<name>` gedeelte geeft de tekst die in de URL staat door aan de `hello` functie als een variabele met de naam `name`.
- `def hello(name)`: dit is de functie die bepaalt welke inhoud wordt getoond. Hierbij neemt de functie de opgegeven naam als parameter.
- `return render_template('page.html', name=name)`: deze code zoekt de sjabloon `page.html` op en geeft de variabele `name` uit de URL door, zodat de sjabloon deze kan gebruiken.

Flask maakt gebruik van `jinja`, een Python-bibliotheek voor het renderen van sjablonen. Kijk eens naar deze code met de accolades:

```html
<h1>Hallo {{ name }}!</h1>
```

Deze code vertelt de sjabloon om de variabele `name` te gebruiken die is doorgegeven in de routefunctie `hello`.

Als u `localhost:5000/hello/` bezoekt zonder een naam, ontstaat er een fout.

\--- /collapse ---