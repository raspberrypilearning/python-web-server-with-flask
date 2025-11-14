## Použij CSS styl

**Kaskádové styly (CSS)** jsou pravidla, která prohlížeči sdělují, jak má zobrazovat obsah HTML.

--- task ---

Otevři nové okno terminálu, abys mohl nechat webový server Flask spuštěný v tom druhém.

--- /task ---

--- task ---

Ujisti se, že jsi v adresáři `webapp`, a to pomocí tohoto příkazu:

--- code ---
---
language: bash
line_numbers: false
---

cd ~/Documents/webapp

--- /code ---

--- /task ---

--- task ---

Vytvoř nový adresář s názvem `static`.

--- code ---
---
language: bash
line_numbers: false
---
mkdir static

--- /code ---

--- /task ---

--- task ---

Vrať se do **Thony** a vytvoř nový soubor. Ulož tento soubor jako `style.css` do složky `static`.

--- /task ---

--- task ---

Přidej následující CSS pravidla do souboru `style.css` a poté soubor **ulož**. Toto je tvůj stylový list.

--- code ---
---
language: css
line_numbers: true
---
body {
    background: beige;
    color: blue;
}

--- /code ---

--- /task ---

--- task ---

Nyní uprav HTML šablonu `index.html` tak, aby obsahovala CSS styly:

--- code ---
---
language: css
line_numbers: true
line_number_start: 1
line_highlights: 2-4
---
<html>
<head>
<link rel="stylesheet" href="/static/style.css" />
</head>
<body>
<h1>Moje webová stránka</h1>
</body>
</html>

--- /code ---

--- /task ---

--- task ---

Ulož změny do souboru `index.html`, poté se vrať do **Chromia** a obnov stránku prohlížeče. Měli bys vidět barevnou verzi webové aplikace!

![Aplikace Flask s barvou](images/flask-app-with-colour.png)

--- /task ---

--- collapse ---
---
title: Nevidím barvy
---

Pokud tvá webová aplikace nevypadá správně, soubor CSS se pravděpodobně nenachází ve správném adresáři.

Ujisti se, že adresář projektu `webapp` obsahuje následující soubory a má následující strukturu:

```
├── app.py
├── static
│   └── style.css
└── templates
    └── index.html
    └── cakes.html
```

--- /collapse ---