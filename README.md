# 2a_Stop_and_Wait_Protocol

## NAME: KRISHNA KUMAR R
## REGISTER NO: 212223230107

## AIM 

To write a python program to perform stop and wait protocol

## ALGORITHM

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

## PROGRAM

## Client Program:
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

## Server Program:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT

![Screenshot 2024-08-20 092756](https://github.com/user-attachments/assets/c71e4d16-b3d9-433e-91ea-f3b7a3a89d4b)

![Screenshot 2024-08-20 092819](https://github.com/user-attachments/assets/fe87b255-a798-431f-872d-0df7215bdd9a)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
