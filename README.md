EX.NO.2B - IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
AIM:
To implement the sliding window protocal using Python.

ALGORITHM:
Start the program.
Get the frame size from the user
To create the frame based on the user request.
To send frames to server from the client side.
If your frames reach the server it will send ACK signal to client
Stop the Program
PROGRAM:
Client:
yogeshwaran
212223040249

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
   while(i<len(l)):
    st+=s
    c.send(str(l[i:st]).encode())
    ack=c.recv(1024).decode()
    if ack:
       print(ack)
       i+=s
Server:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
OUPUT:
Client :
![image](https://github.com/user-attachments/assets/92a21442-70f2-43aa-882f-c5cf8e67a80b)


Server:
![image](https://github.com/user-attachments/assets/edb776c1-b548-4bb7-a47d-6a9aa5a40031)


RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
