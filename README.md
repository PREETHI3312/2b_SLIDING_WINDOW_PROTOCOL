# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## NAME: A K PREETHI
## REG NO:212223230156
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

CLIENT

import socket

    s=socket.socket()

s.bind(('localhost', 8000))

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
          
SERVER:

import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:

     print(s.recv(1024).decode())
     
     s.send("Acknowledgement received from the client".encode())
## OUPUT
## CLIENT
![IMG-20240304-WA0031](https://github.com/PREETHI3312/2b_SLIDING_WINDOW_PROTOCOL/assets/151625222/9f01b659-3e45-464f-9b14-23e9afdda46d)
## SERVER
![IMG-20240304-WA0032](https://github.com/PREETHI3312/2b_SLIDING_WINDOW_PROTOCOL/assets/151625222/c865e671-179d-4b77-b954-ea2568ad2c6b)








## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
