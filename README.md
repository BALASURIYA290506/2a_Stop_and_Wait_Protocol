# 2a_Stop_and_Wait_Protocol
## Name : M BALASURIYA
## Register No : 212224240021

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
Client
```python
import socket
s=socket.socket()
s.bind(('localhost', 8001))
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
Server
```python
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived from the server".encode())
```




## OUTPUT
<img width="1919" height="1147" alt="image" src="https://github.com/user-attachments/assets/3e0ec0a1-d074-4ffd-a3bc-18dbaad1a2c2" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
