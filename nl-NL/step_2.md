## Maak de app

\--- task ---

Open een terminal en gebruik de opdracht `mkdir` om een nieuwe map met de naam `webapp` te maken in uw documentenmap.

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

mkdir ~/Documents/webapp

\--- /code ---

\--- /task ---

\--- task ---

Gebruik de opdracht `cd` om de nieuwe map te openen.

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

cd ~/Documents/webapp

\--- /code ---

\--- /task ---

\--- task ---

Open **Thonny** in het menu **Programmeren**.

\--- /task ---

\--- task ---

Voeg deze Python-code toe aan het lege bestand.

## --- code ---

language: python
line_numbers: false
--------------------------------------------------------

from flask import Flask

app = Flask(**name**)

@app.route('/')
def index():
return 'Hallo wereld'

if **name** == '**main**':
app.run(debug=True, host='0.0.0.0')

\--- /code ---

\--- /task ---

\--- task ---

Sla het nieuwe bestand op onder de naam `app.py` in de map `webapp` die u zojuist hebt gemaakt.

\--- /task ---

\--- task ---

Ga terug naar uw terminalvenster en voer het script uit dat u zojuist hebt geschreven:

## --- code ---

language: bash
line_numbers: false
--------------------------------------------------------

python3 app.py

\--- /code ---

\--- /task ---

Als alles goed werkt, ziet u in het venster uitvoer die er ongeveer zo uitziet:

![pi voert web-app uit](images/pi-run-web-app.png)

\--- task ---

Open in het menu van je Raspberry Pi **Internet** > **Chromium webbrowser**

\--- /task ---

\--- task ---

Typ `localhost:5000` in de adresbalk en druk op <kbd>en voer</kbd>in. U zou de welkomstpagina moeten zien.

\--- /task ---

![Flask Hallo wereld](images/flask-hello-world.png)


