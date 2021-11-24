# Developing a Simple Webserver
## AIM:
To develop a simple webserver to display about the top five programming languages.

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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top five Programming Languages</h1>
<h2>1. Python:</h2>
     Python is an interpreted, object-oriented, high-level programming language with dynamic semantics. Its high-level built in data structures, combined with dynamic typing and dynamic binding, make it very attractive for Rapid Application Development, as well as for use as a scripting or glue language to connect existing components together.<br>
<h2>2. JavaScript:</h2>
     Javascript (JS) is a scripting languages, primarily used on the Web. It is used to enhance HTML pages and is commonly found embedded in HTML code. JavaScript is an interpreted language. Thus, it does not need to be compiled. JavaScript renders web pages in an interactive and dynamic fashion.<br>
<h2>3. Java:</h2>
     Java is a general-purpose, class-based, object-oriented programming language designed for having lesser implementation dependencies. It is a computing platform for application development. Java is fast, secure, and reliable.<br>
<h2>4. PHP:</h2>
     PHP (Hypertext Preprocessor) is known as a general-purpose scripting language that can be used to develop dynamic and interactive websites. It was among the first server-side languages that could be embedded into HTML, making it easier to add functionality to web pages without needing to call external files for data.<br>
<h2>5. Swift:</h2>
     Swift is a high-level programming language developed by Apple and made available in 2014. It is designed for writing apps for Apple platforms, including macOS, iOS, tvOS, and watchOS. The Swift language is based on Objective-C, which was used for NeXTSTEP development in the 1980s, and later macOS and iOS.<br>
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
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
~~~

## OUTPUT:

## CLIENT SIDE OUTPUT:

![Client Side Output](![image](https://user-images.githubusercontent.com/93427534/143291358-7d94c1ae-6150-44d9-a7ab-ee0970a64440.png)

## SERVER SIDE:

![serverside1](https://user-images.githubusercontent.com/93427534/143291497-8722b637-8621-423a-8615-5f1f048cb1be.png)


![serverside2](https://user-images.githubusercontent.com/93427534/143291665-a36e3e30-499b-4250-8069-21aad73c4480.png)


## RESULT:
Thus, a simple webserver is created to display top five programming languages.
