# EXP-01 Developing a Simple Webserver
## Date: 08-03-2024

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Revenue from Companies</h1>
<table border=2>
<tr>
<th> Company Name </th>
<th> Revenue </th>
<th> Financial Year </th>
</tr>

<tr>
<td> Microsoft </td>
<td> 86$ </td>
<td> 2014 </td>
</tr>

<tr>
<td> Oracle </td>
<td> 37$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> SAP </td>
<td> 20$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> VMware </td>
<td> 5.2$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> CA Technologies </td>
<td> 4.7$ </td>
<td> 2013 </td>
</tr>

</body>
</html>
'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
![WhatsApp Image 2024-05-06 at 09 11 54_dbc5659d](https://github.com/Ajith1413/simplewebserver/assets/139842524/0d1ee9b7-900c-42b9-8c57-386cbcce6524)


## RESULT:
The program for implementing simple webserver is executed successfully.
