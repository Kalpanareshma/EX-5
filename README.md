# EX-5 IMPLEMENTATION OF REVERSE ADDRESS RESOLUTION PROTOCOL ( RARP )
## DATE :06.04.2023
## AIM :
To write a python program for simulating RARP protocols using UDP
## ALGORITHM :
## CLIENT:
### STEP 1: Start the program
### STEP 2: Using datagram sockets UDP function is established.
### STEP 3: Get the MAC address to be converted into IP address.
### STEP 4: Send this MAC address to server.
### STEP 5: Server returns the IP address to client
## SERVER:
### STEP 1:Start the program.
### STEP 2: Server maintains the table in which IP and corresponding MAC addresses are stored.
### STEP 3: Read the MAC address which is send by the client.
### STEP 4: Map the IP address with its MAC address and return the IP address to client
## CLIENT PROGRAM :
## Developed : Kalpana S
## Reg no : 212222040069
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode()
```
## SERVER PROGRAM :
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter MAC Address : ")
    s.send(ip.encode())
    print("Logical Address",s.recv(1024).decode())
```
## OUTPUT :
### CLIENT :
![ex05 client output](https://github.com/Kalpanareshma/EX-5/assets/122040453/2ae6cc38-3a10-487a-88a1-dafdfacf0b0a)
### SERVER :
![ex05 server output](https://github.com/Kalpanareshma/EX-5/assets/122040453/58fdf001-6dce-42df-b7b5-e2bf2e2ffd73)


## RESULT :
Thus, python program for simulating RARP protocols using UDP was successfully executed.
