## Build a Flask website

You're going to set up a basic web application with Flask and Python.

First you'll need to install the Flask package. Make sure you are connected to the internet before you start.

--- task ---

Install the `flask` Python module using `pip`.

[[[generic-python-installing-with-pip]]]

--- /task ---

Once Flask is installed, you can create your web application.

--- task ---

Open a terminal or command prompt window, and make a new directory called `webapp` for your project.

```bash
mkdir webapp
```

--- /task ---

--- task ---

Use the change directory command `cd` to open the new directory.

```bash
cd webapp
```
--- /task ---

--- task ---

Open Python 3 IDLE.

--- /task ---

--- task ---

Create a new file by clicking **File** and then **New file**, and save it as `app.py` inside the `webapp` folder you just created.

--- /task ---

--- task ---

Now enter the following lines of code into the blank `app.py` window:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello world'

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```

You will explore this code in more detail in the next step, but for now let's keep it simple and make sure everything works.

![idle](images/idle-flask.png)

--- /task ---

--- task ---

Save your changes by clicking **File** and then **Save**, or by pressing <kbd>Ctrl</kbd> and <kbd>S</kbd>. 

--- /task ---

You will need to run your web app from the terminal/command prompt window you opened earlier.

--- task ---

### On Raspberry Pi/Linux/macOS

Enter the command `python3 app.py` into the terminal window.

### On Windows

Enter the command `python app.py` into the command prompt window.

--- /task ---

If everything has been set up correctly, you should see an output similar to this:

```
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger pin code: ***-***-***
```

![pi run web app](images/pi-run-web-app.png)

--- task ---

Open your web browser and enter the URL `http://127.0.0.1:5000/`. You should see a white screen with the words `Hello world`.

**Note:** `127.0.0.1` means 'home', i.e. this computer. `:5000` means 'port 5000', which is the port the web server is running on.

--- /task ---

![Flask Hello world](images/flask-hello-world.png)
