# EX01 Developing a Simple Webserver
## Date:17/09/2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
<title>TCP vs IP Protocol</title>
<style>
    table {
        width: 60%;
        border-collapse: collapse;
        margin: 50px auto;
        font-family: Arial, sans-serif;
        text-align: center;
    }
    th {
        background-color: #007BFF; /* Blue color */
        color: white;
        padding: 10px;
        font-size: 18px;
    }
    td {
        color: black;
        border: 1px solid #333;
        padding: 8px;
        font-size: 16px;
    }
    h1 {
        text-align: center;
        color: #007BFF;
    }
</style>
</head>
<body>
    <h1>TCP vs IP Protocol</h1>
    <table border="1">
        <tr>
            <th>Aspect</th>
            <th>TCP (Transmission Control Protocol)</th>
            <th>IP (Internet Protocol)</th>
        </tr>
        <tr>
            <td>Function</td>
            <td>Ensures reliable communication between applications.</td>
            <td>Handles addressing and routing of packets.</td>
        </tr>
        <tr>
            <td>Connection</td>
            <td>Connection-oriented protocol (requires connection setup).</td>
            <td>Connectionless protocol (no setup required).</td>
        </tr>
        <tr>
            <td>Reliability</td>
            <td>Reliable – ensures data delivery, retransmits if lost.</td>
            <td>Unreliable – does not guarantee delivery.</td>
        </tr>
        <tr>
            <td>Data Handling</td>
            <td>Divides data into segments and reassembles correctly.</td>
            <td>Divides data into packets and forwards independently.</td>
        </tr>
        <tr>
            <td>Usage</td>
            <td>Used in HTTP, FTP, Email (applications requiring reliability).</td>
            <td>Used for delivering packets across networks.</td>
        </tr>
    </table>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000
                  )
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
~~~

## OUTPUT:
![alt text](<Screenshot 2025-09-17 114355.png>)
![alt text](<Screenshot 2025-09-17 114532.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.

