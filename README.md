# upm-rotary-http
<p>The purpose of this application is to evaluate the performance of HTTP for viewing live sensor data on an Intel board. The python container utilizes UPM and MRAA libraries to collect sensor data and POST that data (with python's requests library) to the web server. The Node server acts as a REST API, allowing us to receive the data and save it into our MongoDB container. The javascript in our index.html file sends an AJAX GET request to the API, which then queries the DB for the latest data and returns it to our visual graph. Docker Compose runs all containers at the same time on the localhost, so this does not require an external server.
</p>
<li>If you'd like to view live sensor data on a remote sever, check out: </li>
https://github.com/mdrolet01/upm-rotary-http.git
<h2>Getting Started:</h2>
First, you will need an UpSquared Board with the GROVE kit<br>
Connect the GROVEPI shield to the board <br>
Plug in the Rotary sensor to A0 (Analog pin 0)<br>
Make sure docker engine is installed on your computer<br>

<h2>Instructions:</h2>

    git clone https://github.com/mdrolet01/upm-rotary-http.git
    cd upm-rotary-http/node-container
    docker build . -t node-web-server
    cd ../upm-container
    docker build . -t upm-data
    cd ..
    docker compose up
<br>
<p>For Industrial IoT applications, we will need  a much more powerful protocol than HTTP. This is where MQTT and Websockets come into play.</p>
<li>If you'd like to view the MQTT/Websockets version of this project, check out: </li>
https://github.com/mdrolet01/upm-rotary-http.git
