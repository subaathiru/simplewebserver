# EX01 Developing a Simple Webserver
## Date:29-09-2026

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
simpleweb.py
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title>laptop detail</title>
    </head>
    <body style="color : white" bgcolor="black">
    <center>
        <h3>T.Subaashinee(26011940)</h3>
    </center>
        <center>
        <table border="3" cellpadding="4" cellspacing="5">
            <tr>
                <th>1</th>
                <th>Device name</th>
                <td>TL15-53M-G2</td>
            </tr>
            <tr>
                <th>2</th>
                <th>Processor</th>
                <td>Intel(R) Core(TM) 5 210H (2.20 GHz)</td>
            </tr>
            <tr>
                <th>3</th>
                <th>Installed RAM</th>
                <td>16.0 GB (15.7 GB usable)</td>
            </tr>
            <tr>
                <th>4</th>
                <th>Graphics card</th>
                <td>Intel(Rs) Graphics (128 MB)</td>
            </tr>
            <tr>
                <th>5</th>
                <th>Storage</th>
                <td>118 GB of 477 GB used</td>
            </tr>
            <tr>
                <th>6</th>
                <th>Device ID</th>
                <td>CAE2A291-411B-4749-AD61-8CDCE33E5ABF</td>
            </tr>
            <tr>
                <th>7</th>
                <th>Product ID</th>
                <td>00342-42954-08696-AAOEM</td>
            </tr>
            <tr>
                <th>8</th>
                <th>System type</th>
                <td>64-bit operating system, x64-based processor</td>
            </tr>
            <tr>
                <th>9</th>
                <th>Pen and touch</th>
                <td>No pen or touch input is available for this display</td>
            </tr>
        </center>
        </table>
    </body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Client request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my own webserver is running successfully...")
httpd.serve_forever()
```

## OUTPUT:

Webpage
![alt text](<Screenshot 2026-11-10 122918.png>)
Server Page
![alt text](<Screenshot (14).png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
