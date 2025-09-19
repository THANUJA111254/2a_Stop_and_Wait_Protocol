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
## SERVER.PY
```python
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


## CLIENT.PY
```python
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT

## SERVER.PY

<img width="1476" height="771" alt="image" src="https://github.com/user-attachments/assets/5f36e1c6-727a-4ff1-a7c2-39036acb6a07" />

## CLIENT.PY

<img width="1472" height="742" alt="image" src="https://github.com/user-attachments/assets/6d2d92af-9f3c-42b6-a538-219656eada73" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
