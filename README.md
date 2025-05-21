# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
# Name: NAVEEN KUMAR B
# Reg.No: 212222230091
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
Client.py
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
Server.py
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
Client
![image](https://github.com/user-attachments/assets/07258c16-e529-481c-9eb8-fc62de13d621)

Server
![image](https://github.com/user-attachments/assets/ce1695ea-65d2-4c80-833d-dc8584f65fe6)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
