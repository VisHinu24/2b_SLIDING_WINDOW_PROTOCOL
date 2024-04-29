# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Name : H Vishinu
## Reg No : 212223220124
## AIM
To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
Client :
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send"))
l=list(range(size))
s=int(input("Enter Window Size :"))
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
Server :
```
import socket
s=socket.socket()
s.connect (('localhost',8000))
while True :
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())

```

## OUPUT
Client :
![Screenshot 2024-04-22 195106](https://github.com/VisHinu24/2b_SLIDING_WINDOW_PROTOCOL/assets/144244396/dce3c8aa-dc6d-413e-9014-e9a969912bc2)

Server :
![Screenshot 2024-04-22 195112](https://github.com/VisHinu24/2b_SLIDING_WINDOW_PROTOCOL/assets/144244396/ccaad442-1f5e-4f1a-9014-b6db0c014362)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
