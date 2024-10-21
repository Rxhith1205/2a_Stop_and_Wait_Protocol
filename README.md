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
# client 
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
# Server 
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```


![Screenshot 2024-09-02 142148](https://github.com/user-attachments/assets/69345839-93e1-4411-b24b-31e70e4230e4)

## OUTPUT

![Screenshot 2024-09-02 142202](https://github.com/user-attachments/assets/17522c4b-b659-473f-a341-07dce00d375a)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
