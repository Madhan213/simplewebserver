# EX01 Developing a Simple Webserver
## Date:19/09/2023

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top FIVE Revenue companies</h1>
 <ol>
    <li>MICROSOFT</li>
    <li>Google</li>
    <li>Amazon</li>
    <li>Samsung</li>
    <li>TCS</li>
 </ol>
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
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![Screenshot 2023-10-12 094706](https://github.com/Madhan213/simplewebserver/assets/130206230/fc15466a-08a8-44ca-83f6-4d814d36e224)


## RESULT:
The program for implementing simple webserver is executed successfully.
