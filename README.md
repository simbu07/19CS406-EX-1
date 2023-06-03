## 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL
								                		 DATE : 06-03-2023
### AIM :
To write a python program to perform stop and wait protocol

 ### ALGORITHM :
```
1. Start the program.
2. Get the frame size from the user 
3. To create the frame based on the user request. 
4. To send frames to server from the client side. 
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client. 
6. Stop the program
```

### Client Program:
```
Developed By : Silambarasan K
Reg No : 212221230101
```

```Py
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
   i=input("ENter a data:")
   c.send(i.encode())
   ack=c.recv(1024).decode()
   if ack:
   	print(ack)
   	continue
   else:
   	c.close()
   	break
```
### Server Program :
```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
```
### OUTPUT:
### SERVER OUTPUT:
![S](https://user-images.githubusercontent.com/122860624/242962266-23a672cd-ac43-4141-94f9-8d5bcdd3ba02.png)

### CLIENT OUTPUT:
![C](https://user-images.githubusercontent.com/122860624/242962322-76c7fdb9-2a29-4289-a199-e4d9dab8f032.png)

### RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
