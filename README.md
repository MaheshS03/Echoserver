# Echoserver
Echo server and client using python socket

## AIM:
To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:
### Step 1:
Design of echo server and client using python socket

### Step 2:
Implementation using Python code

### Step 3:
Testing the server and client 

## PROGRAM:
### Server code
### echo-server.py
```
import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)   
```
### Client Code:
### echo-client.py
```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
```
## OUTPUT:
### echo-server.py
![WhatsApp Image 2024-02-15 at 20 22 47_3be4142d](https://github.com/MaheshS03/Echoserver/assets/128498431/d99acecb-8ad6-49bd-a81d-7e88dcce22da)

### echo-client.py
![WhatsApp Image 2024-02-15 at 20 22 48_b96b77c2](https://github.com/MaheshS03/Echoserver/assets/128498431/a6e5f245-ce72-4406-a2f0-67b58d8b0389)

## RESULT:
The program is executed successfully
