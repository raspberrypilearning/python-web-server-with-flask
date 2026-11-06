## Gebruik CSS-stijlen

**Cascading Style Sheets (CSS)** zijn regels die een browser vertellen hoe HTML-inhoud moet worden weergegeven.

\--- task ---

Open een nieuw terminalvenster, zodat u de Flask-webserver in het andere venster draaiende kunt laten.

\--- /task ---

\--- task ---

Zorg ervoor dat u zich in de map `webapp` bevindt met behulp van deze opdracht:

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

cd ~/Documents/webapp

\--- /code ---

\--- /task ---

\--- task ---

Maak een nieuwe map met de naam `static`.

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

mkdir static

\--- /code ---

\--- /task ---

\--- task ---

Ga terug naar **Thomny** en maak een nieuw bestand. Sla dit bestand op als `style.css` in uw `static` map.

\--- /task ---

\--- task ---

Voeg de volgende CSS-regels toe aan `style.css` en **sla** het bestand op. Dit is uw stijlblad.

## --- code ---

language: css
line_numbers: true
-------------------------------------------------------

body {
background: beige;
color: blue;
}

\--- /code ---

\--- /task ---

\--- task ---

Wijzig nu uw HTML-sjabloon `index.html` zodat deze het CSS-stijlblad bevat:

## --- code ---

language: css
line_numbers: true
line_number_start: 1
line_highlights: 2-4
---------------------------------------------------------

<html>
<head>
<link rel="stylesheet" href="/static/style.css" />
</head>
<body>
<h1>Mijn website</h1>
</body>
</html>

\--- /code ---

\--- /task ---

\--- task ---

Sla de wijzigingen op in `index.html` en ga terug naar **Chromium** om de browser te vernieuwen. U zou een kleurrijke versie van uw web-app moeten zien!

![Flask-app met kleur](images/flask-app-with-colour.png)

\--- /task ---

## --- collapse ---

## titel: Ik kan de kleuren niet zien

Als uw webapp er niet goed uitziet, staat uw CSS-bestand mogelijk niet in de juiste map.

Zorg ervoor dat de projectmap `webapp` de volgende bestanden bevat en de volgende structuur heeft:

```
├── app.py
├── static
│   └── style.css
└── templates
    └── index.html
    └── cakes.html
```

\--- /collapse ---