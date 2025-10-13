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
## Client:
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
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT
## Client:
<img width="1348" height="298" alt="Screenshot 2025-10-12 155302" src="https://github.com/user-attachments/assets/2aa4d974-c628-46b8-92df-e7cbd894c485" />



## Server:
<img width="1335" height="254" alt="Screenshot 2025-10-12 155324" src="https://github.com/user-attachments/assets/6e6bce27-00ba-44a7-a524-7ac3a8492118" />




## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
