## Dynamický obsah

Webové stránky jako Facebook, YouTube a BBC News mají dynamický obsah: tyto weby zobrazují různý obsah v rámci stejné šablony.

Nyní si na svém webu vytvoř novou trasu, aby se ti na stránce zobrazovalo personalizované uvítání.

--- task ---

Otevři soubor `app.py` a přidej do aplikace novou trasu:

##
--- code ---

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

--- /code ---

--- /task ---

--- task ---

Vytvoř novou HTML šablonu ve složce templates s názvem `page.html` a přidej do ní následující HTML kód:

##
--- code ---

language: html
line_numbers: true
-------------------------------------------------------

<html>
<body>
<h1>Ahoj {{ name }}!</h1>
</body>
</html>

--- /code ---

--- /task ---

--- task ---

Ulož oba soubory a poté v prohlížeči Chromium navštiv stránku `localhost:5000/hello/Paul`.

Stránka by měla vypadat přibližně takto:

![Webová stránka zobrazující text „Ahoj Paule!“](images/flask-hello-paul.png)

Zkus nahradit „Paul“ v adresním řádku jiným jménem!

--- /task ---

--- task ---

Otevři šablonu `index.html` a pod nadpis přidej odkaz na úvodní stránku.

##
--- code ---

language: html
line_numbers: true
line_number_start: 6
line_highlights: 7
-------------------------------------------------------

<h1>Moje webová stránka</h1><a href="/hello/paul">Ahoj Pavle</a>

--- /code ---

--- /task ---

--- task ---

Ulož změny do souboru `index.html` a poté otevři soubor `localhost:5000`, abys viděl aktualizovanou verzi.

Webová stránka s modrým textem na béžovém pozadí. Text v záhlaví zní „Moje webová stránka“ a poté odkaz na „Ahoj Paule“](images/flask-app-link.png)

--- /task ---

--- collapse ---
---
title: Jak tato trasa funguje?
---

- `@app.route('/hello/<name>')`: část `<name>` předává text zapsaný v URL do funkce `hello` jako proměnnou s názvem `name`.
- `def hello(name)`: toto je funkce, která určuje, jaký obsah se zobrazí. Zde funkce bere zadaný název jako parametr.
- `return render_template('page.html', name=name)`: tento kód vyhledá šablonu `page.html` a předá proměnnou `name` z URL adresy, aby ji šablona mohla použít.

Flask používá `jinja`, knihovnu Pythonu pro vykreslování šablon. Podívej se na tento kód se složenými závorkami:

```html
<h1>Ahoj {{ name }}!</h1>
```

Tento kód říká šabloně, aby použila proměnnou `name`, která byla předána ve funkci trasy `hello`.

Návštěva `localhost:5000/hello/` bez názvu (jména) vytvoří chybu.

--- /collapse ---