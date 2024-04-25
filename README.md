# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
### CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
### SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```
## OUPUT - ARP
### CLIENT
![image](https://github.com/Afsarjumail/2c.ARP_RARP_PROTOCOLS/assets/118343395/c78526fd-72aa-4148-8720-a434d59bb917)
### SERVER
![image](https://github.com/Afsarjumail/2c.ARP_RARP_PROTOCOLS/assets/118343395/474cbff5-3e2e-4ba3-b2c0-78f49c1d93e2)

## PROGRAM - RARP
### CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
 ip=c.recv(1024).decode()
 try:
   c.send(address[ip].encode())
 except KeyError:
   c.send("Not Found".encode())
```
### SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
### CLIENT
![image](https://github.com/Afsarjumail/2c.ARP_RARP_PROTOCOLS/assets/118343395/3fc4b1a3-600f-4955-8a36-0a6510b73c43)

### SERVER
![image](https://github.com/Afsarjumail/2c.ARP_RARP_PROTOCOLS/assets/118343395/1f9f139d-7eb5-4a16-bf0e-32b6aa9b867f)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
