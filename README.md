# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
## multi.py 
from http.server import HTTPServer,BaseHTTPRequestHandler

Content="""
<!doctype html>
<html lang="en">
<head>
<title>my webserver</title>
</head>
<body>
<h1>MULTIPLICATION TABLES OF 5</h1>
5×0=0<br>
5×1=5<br>
5×2=10<br>
5×3=15<br>
5×4=20<br>
5×5=25<br>
5×6=30<br>
5×7=35<br>
5×8=40<br>
5×9=45<br>
5×10=50<br>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request recived")

        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')             
        self.end_headers()

     #to send the responce
        self.wfile.write(Content.encode())

 #to create server address     
server_address=('',80)

#to listen at the specified port
httpd = HTTPServer(server_address,myhandler)
print("MY WEBSERVER IS RUNNING...")
httpd.serve_forever()



## OUTPUT:
![output](./static/img/v.png)


## RESULT:
Thus a website is designed for the chip manufacturing company and is hosted in the URL http://veeramalai.student.saveetha.in. HTML code is validated.
