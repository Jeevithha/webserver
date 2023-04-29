# Ex01 Developing a Simple Webserver
# AIM:
To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:
### Step 1:
HTML content creation is done

### Step 2:
Design of webserver workflow

### Step 3:
Implementation using Python code

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver

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
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
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
Server Output:

![image](https://user-images.githubusercontent.com/123623197/235315891-234cbc2e-681a-406f-9604-f9fd1b4f7f58.png)

Client Output:

![image](https://user-images.githubusercontent.com/123623197/235315907-2a532aed-eda2-4b49-bb5f-67da8303b5fd.png)

## RESULT:
The program is executed succesfully
