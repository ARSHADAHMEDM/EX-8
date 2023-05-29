# EX-8 APPLICATION USING TCP SOCKETS - CREATING ECHO CLIENT-SERVER
# DATE : 27.04.2023
# AIM :
### To write a python program for creating Echo Client and Echo Server using TCP Sockets Links.
# ALGORITHM :
### 1.Start the program.
### 2.Get the frame size from the user
### 3.To create the frame based on the user request.
### 4.To send frames to server from the client side.
### 5.If your frames reach the server, it will send ACK signal to client otherwise it will send NACKsignal to client.
### 6.Stop the program.
# CLIENT PROGRAM :
```python 
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    msg = input("Client > ")
    s.send(msg.encode())
    print("Server > ", s.recv(1024).decode())
```
# SERVER PROGRAM :
```py
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()
while True:
    ClientMessage = c.recv(1024).decode()
    c.send(ClientMessage.encode())
```
#  CLIENT OUTPUT :
![8c](https://github.com/ARSHADAHMEDM/EX-8/assets/128116503/3a67a9e6-57ad-454d-9689-48ae8bcc36a6)

# SEVER OUTPUT :
![8s](https://github.com/ARSHADAHMEDM/EX-8/assets/128116503/433a2f03-08c7-45e5-aa79-e4ecf2507383)
# RESULT :
### Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links was successfully created and executed.
