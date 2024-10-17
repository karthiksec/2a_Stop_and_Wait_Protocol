# 2a_Stop_and_Wait_Protocol
# AIM 
To write a python program to perform stop and wait protocol
# ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
# PROGRAM
## Client:
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
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
# OUTPUT
## CLIENT
![1](https://github.com/Rajkiran276/2a_Stop_and_Wait_Protocol/assets/147471453/002a567b-f6a3-43d6-8e3b-61c76d689c73)
## SERVER
![2](https://github.com/Rajkiran276/2a_Stop_and_Wait_Protocol/assets/147471453/d0312504-c75b-4535-9387-98764d9c8889)


# RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
