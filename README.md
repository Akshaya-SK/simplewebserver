# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to display the configuration details of my laptop.

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

content = '''<html>
    <head>
        <title> Web experiment 1 </title>
    </head>
    <body>
        <table border = "1" style = "border-collapse:collapse" align = "center">
            <tr>
                <td>BRAND </td>
                <td>Lenovo</td>
            </tr>
            <tr>
                <td>MODEL NAME </td>
                <td>E15 Gen4</td>
            </tr>
            <tr>
                <td>SCREEN SIZE</td>
                <td>15.6 Inches</td>
            </tr>
            <tr>
                <td>COLOUR</td>
                <td>Black</td>
            </tr>
            <tr>
                <td>HARD DRIVE SIZE</td>
                <td>512 GB</td>
            </tr> 
            <tr>
                <td>CPU MODEL</td>
                <td>Core 15-1235U</td>
            </tr>
            <tr>
                <td>RAM MEMORY</td>
                <td>8 GB</td>
            </tr>
            <tr>
                <td>OPERATING SYSTEM </td>
                <td>Windows 11 Home</td>
            </tr>
        </table>
    </body>
</html>
'''

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
![image](https://github.com/user-attachments/assets/72513569-ea29-4dd9-aa9f-ce35d9a8a48e)


## RESULT:
The program for implementing simple webserver is executed successfully.
