# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## DEVELOPED BY : NITHYA D
## REG.NO : 212223240110

## AIM :
To write a python program for sliding window protocol.
## ALGORITHM :
1. Start the program.
2. Get the frame size from the user.
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client.
6. Stop the Program.
## PROGRAM :
### CLIENT :
```
Developed by : NITHYA D
Reg.no : 212223240110

import socket
s=socket.socket()
s.bind(('localhost',8000)) 
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send: "))
l=list(range(size))
s=int(input("Enter Window Size: "))
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
### SERVER :
```
Developed by : NITHYA D
Reg.no : 212223240110

import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
   print(s.recv(1024).decode())
   s.send("acknowledgement recived from the server".encode())
```
## OUPUT :
![image](https://github.com/NithyaDayalan/2b_SLIDING_WINDOW_PROTOCOL/assets/166380061/adec7587-4b59-46ca-ac80-65b2bfd8e593)

## RESULT :
Thus, python program to perform stop and wait protocol was successfully executed.
