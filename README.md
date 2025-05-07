# EX01 Developing a Simple Webserver
## Date:07-05-2025

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

Name: Arunsamy D

Register Number: 212224240016 / 24900591


```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>TCP/IP PROTOCOLS</title>
    <style>
        .head-box{
            border:2px black solid;
            border-radius: 20px;
            text-align: center;
            font-family: 'Times New Roman', Times, serif;
            font-size: medium;
            width: 50%;
            margin: 20px auto;
            background: linear-gradient(to bottom, #ffffff, #9ee4fe) ;
            color: black solid;
        }
        .info-box{
            margin: 20px auto;
            width: 60%;
            border-radius: 20px;
            overflow: hidden;
            border: 2px solid black;
        }
        .info-box table{
            width: 100%; 
            border-collapse: collapse;
            font-family: 'Times New Roman', Times, serif;
            background-color: #9ee4fe;
        }
        
        
        .info-box th, .info-box td{
            font-size: larger;
            padding: 20px;
            text-align: left;    
            border: 1px solid black;
            
        }
        
    </style>
</head>
<body>
    <div class="container">
        <div class="head-box">
            <h1 id="111">TCP/IP</h1>
        </div>

        <div class="info-box" >
        <table>
           <tr><th><b>TCP/IP LAYER</b></th><th><b>PROTOCOL</b></th></tr>
           <tr><td>Application Layer</td><td>HTTP, FTP, SMTP, DNS, DHCF</td></tr>
           <tr><td>Transport Layer</td><td>TCP, UDP</td></tr>
              <tr><td>Internet Layer</td><td>IP(IPv4, IPv6), ICMP, ARP, IGMP</td></tr>
              <tr><td>Network Access Layer</td><td>Ethernet, WI-FI, PPP, Slip</td></tr>
             
        </table>
        </div>
    </div>
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

![alt text](<Screenshot (80).png>)

![alt text](<Screenshot (79).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
