# EX.NO.2B - IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM:
To implement the sliding window protocal using Python.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
## Client:
```
Yogeshwaran A
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
```
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
## OUPUT:
## Client :
![WhatsApp Image 2024-04-30 at 22 38 38_6737ff62](https://github.com/JAYASREE24032006/2b_SLIDING_WINDOW_PROTOCOL/assets/144360800/31861e17-455b-4f84-8052-2b8d2c71fe3d)
## Server:
![WhatsApp Image 2024-04-30 at 22 39 12_def917fa](https://github.com/JAYASREE24032006/2b_SLIDING_WINDOW_PROTOCOL/assets/144360800/5124ed5d-4b67-40e7-b827-df2f6d9955be)


## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
