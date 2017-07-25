## Browsing on other devices

Since we used `host='0.0.0.0'`, on the `app.run` line, the web server is accessible to any device on the same network, including other computers, tablets, and smartphones.

- Enter the following command in the Terminal window to find your Raspberry Pi's IP address:

    ```bash
    hostname -I
    ```
    
    You should get something like `192.168.1.3`.

- Take another computer, tablet or smartphone, and make sure it's connected to the same network as the Raspberry Pi.

- Open up a web browser on the other device and enter the Raspberry Pi's IP address into the address bar with `:5000` on the end e.g. `http://192.168.1.3:5000/`:

    ![Address bar](images/flask-on-android.png)

- You should now see the web app from the other device. Try navigating to the other pages too.

