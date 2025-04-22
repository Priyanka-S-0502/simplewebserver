# EX01 Developing a Simple Webserver
## Date:22-04-2025

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content="""<!doctype html>
<html>
<head>
<title> My Web Server</title>
<style>
    table,tr,td,th
    {
    
    border:1px solid black;
    border-collapse:collapse;
    padding:10px;
    text-align:center;
    }
    </style>
</head>
<body>
<center><h1 style="font-family: cursive;"><u>TCP/IP PROTOCOLS</u></h1><br>
<table>
<tr>
<th>S.NO</th>
<th>LAYER</th>
<th>PROTOCOLS</th>
</tr>
    
<tr>
<td>1.</td>
<td>Application layer protocol</td>
<td>HTTPS,FTP,DNS</td>
</tr>
    
<tr>
<td>2.</td>
<td>Transport layer protocol</td>
<td>TCP</td>
    
</tr>
    
<tr>
<td>3.</td>
<td>Internet layer protocol</td>
<td>IP</td>
</tr>
    
<tr>
<td>4.</td>
<td>Link layer protocol</td>
<td>MAC</td>
</tr>
</table>
</center>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:

![alt text](<Screenshot 2025-04-22 165055.png>)

![alt text](<Screenshot 2025-04-22 165121.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
