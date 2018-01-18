## Building a basic Flask web application

Now you're going to set up a basic web application with Flask and Python. You will be able to run a single web page and display some text on a web browser.

- Using the Terminal, make a new directory for your project.

```bash
mkdir mywebserver
```

- Use the change directory command to open it.

```bash
cd mywebserver
```

- Open Python 3 from the main menu.

- Open a new window by clicking `File > New file`, and save this as `app.py` inside the project folder you created.

- You'll write your application code here and when you run your code, any printed messages or errors will be shown in the Python shell window which opened first.

- Now enter the following lines into the blank `app.py` window:

    ```python
    from flask import Flask

    app = Flask(__name__)

    @app.route('/')
    def index():
        return 'Hello world'

    if __name__ == '__main__':
        app.run(debug=True, host='0.0.0.0')
    ```
    
    Note here the `host='0.0.0.0'` means the web app will be accessible to any device on the network.

- Save the file with `Ctrl + S`. 

- Return to the Terminal window and enter `python3 app.py` to run the web server.

    If everything has been written correctly, you should see an output similar to this:

    ```
    * Running on http://0.0.0.0:5000/
    * Restarting with reloader
    ```

- Open the Pi's web browser from the taskbar or application menu and navigate to `http://127.0.0.1:5000/`. You should see a white screen with the words `Hello world`:

    ![Flask Hello world](images/flask-hello-world.png)

    *Note: `127.0.0.1` means 'home' i.e. this computer, and `:5000` means 'port 5000', which is the port the web server is running on*

