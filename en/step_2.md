## Building a simple Flask web application

Now you're going to set up a basic web application with Flask and Python.

First you're going to install the Flask package. Make sure you are connected to the internet before you start.

--- task ---

Install the `flask` python module using `pip`.

[[[generic-python-installing-with-pip]]]

--- /task ---

Once Flask is installed you can create your web application.

--- task ---

Using the Terminal or Command Prompt, make a new directory for your project.

```bash
mkdir webapp
```

--- /task ---

--- task ---

Use the change directory command to open it.

```bash
cd webapp
```
--- /task ---

--- task ---

Open Python 3 IDLE.

--- /task ---

--- task ---

Create a new file by clicking **File**, **New file**, and save this as `app.py` inside the `webapp` folder you just created.

--- /task ---

--- task ---

Now enter the following lines into the blank `app.py` window:

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello world'

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```

**Note:** the `host='0.0.0.0'` means the web app will be accessible to any device on the network.

![idle](images/idle-flask.png)

--- /task ---

--- task ---

Save your changes by clicking **File**, **Save** or pressing **Ctrl + S**. 

--- /task ---

You will need to run your web app from the Terminal or Command Prompt you opened earlier.

--- task ---

### Raspberry Pi / Linux / macOS

Enter the command `python3 app.py` into the Terminal.

### Windows

Enter the command `python app.py` into the Command Prompt.

--- /task ---

If everything has been setup correctly, you should see an output similar to this:

```
 * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger pin code: ***-***-***
```

![pi run web app](images/pi-run-web-app.png)

--- task ---

Open your web browser and enter the URL `http://127.0.0.1:5000/`. You should see a white screen with the words `Hello world`:

**Note:** `127.0.0.1` means 'home' i.e. this computer, and `:5000` means 'port 5000', which is the port the web server is running on.

--- /task ---

![Flask Hello world](images/flask-hello-world.png)
