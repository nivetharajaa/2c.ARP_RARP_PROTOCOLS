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
### CLIENT
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
### SERVER
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
![307230852-b58b8c77-a937-4957-8272-008fbb6ba8da](https://github.com/nivetharajaa/2c.ARP_RARP_PROTOCOLS/assets/120543388/85081072-d12a-47ba-9524-556b21e8aeec)
### SERVER
![307230858-9036605f-01af-4e34-8483-49126ae2bce2](https://github.com/nivetharajaa/2c.ARP_RARP_PROTOCOLS/assets/120543388/41e2a24f-c232-48f1-abeb-b4847980e51d)

## PROGRAM - RARP
### CLIENT
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
### SERVER
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
![307232520-fbef2bb0-a6cc-463d-bb76-89f75f4a92ef](https://github.com/nivetharajaa/2c.ARP_RARP_PROTOCOLS/assets/120543388/67077580-9528-4aa1-b9ab-b7e39bda8487)
### SERVER
![307232521-5f6a0540-a321-4d6c-a163-f6df66e44c69](https://github.com/nivetharajaa/2c.ARP_RARP_PROTOCOLS/assets/120543388/ac15909f-3c3c-4c32-befe-02da4a6c66a4)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
