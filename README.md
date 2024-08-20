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
## PROGRAM
### Client:
```py
import socket
s=socket.socket()
s.bind(('localhost',8080))
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

### Server:
```py
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement received".encode())
```

## OUTPUT
### Client:
![exp2aclient](https://github.com/user-attachments/assets/ab42b7a2-21a8-41b3-b45c-7b1d083692dc)

### Server:
![exp2aserver](https://github.com/user-attachments/assets/d0ece501-e2dd-4df3-957d-3e7a218d3c75)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
