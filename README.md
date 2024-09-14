# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

NAME : MOHAMED ASIL S
REGISTER NO : 212223040112

## CLIENT :

```
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

## SERVER :

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
   print(s.recv(1024).decode())
   s.send("acknowledgement recieved from the server".encode())

```
## OUPUT

![image](https://github.com/user-attachments/assets/08b15921-4458-4265-b0c0-71118ec0af8f)


![image](https://github.com/user-attachments/assets/cfb90502-cf26-4980-a9cc-867cb0dacc4c)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
