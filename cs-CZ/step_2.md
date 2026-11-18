## Vytvoř aplikaci

\--- task ---

Otevři terminál a pomocí příkazu `mkdir` vytvoř ve složce dokumentů nový adresář s názvem `webapp`.

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

mkdir ~/Documents/webapp

\--- /code ---

\--- /task ---

\--- task ---

Pro otevření nového adresáře použij příkaz `cd` pro změnu adresáře.

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

cd ~/Documents/webapp

\--- /code ---

\--- /task ---

\--- task ---

V nabídce **Programování** otevři **Thony**.

\--- /task ---

\--- task ---

Přidej tento kód Pythonu do prázdného souboru.

## --- code ---

language: python
line_numbers: false
--------------------------------------------------------

from flask import Flask

app = Flask(**name**)

@app.route('/')
def index():
return 'Ahoj světe'

if **name** == '**main**':
app.run(debug=True, host='0.0.0.0')

\--- /code ---

\--- /task ---

\--- task ---

Ulož nový soubor s názvem `app.py` do složky `webapp`, kterou jsi právě vytvořil.

\--- /task ---

\--- task ---

Vrať se do terminálového okna a spusť skript, který jsi právě napsal:

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

python3 app.py

\--- /code ---

\--- /task ---

Pokud vše funguje správně, okno by mělo ukázat výstup podobný tomuto:

![spusť webovou aplikaci pi](images/pi-run-web-app.png)

\--- task ---

V nabídce Raspberry Pi otevři **Internet** > **Webový prohlížeč Chromium**

\--- /task ---

\--- task ---

Do adresního řádku zadej `localhost:5000` a stiskni <kbd>Enter</kbd>. Měl bys vidět uvítací stránku.

\--- /task ---

![Flask Ahoj světe](images/flask-hello-world.png)


