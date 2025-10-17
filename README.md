# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:

client:
```
import socket

# Client side
s = socket.socket()
s.connect(('localhost', 8000))

while True:
    data = s.recv(1024).decode()
    print("Received:", data)
    s.send("Acknowledgement received from client".encode())
```

server:
```
import socket

# Server side
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)
print("Server is waiting for connection...")

c, addr = s.accept()
print("Connection established with:", addr)

while True:
    i = input("Enter data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    print("From Client:", ack)
```
## OUTPUT:

<img width="1915" height="1016" alt="image" src="https://github.com/user-attachments/assets/d53dd00b-5a0d-4a5e-b12a-3cb810eeb9e3" />

result:
Thus, python program to perform stop and wait protocol was successfully executed.
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
