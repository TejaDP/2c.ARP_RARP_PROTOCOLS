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
## OUPUT - ARP
<img width="1600" height="901" alt="WhatsApp Image 2026-05-22 at 8 25 49 AM" src="https://github.com/user-attachments/assets/1e7da1ce-54c7-442d-9883-017a978adc8c" />

## PROGRAM - RARP
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
<img width="1600" height="900" alt="WhatsApp Image 2026-05-22 at 8 25 50 AM" src="https://github.com/user-attachments/assets/d0444e5b-5327-4999-aec6-b2d73bd7affe" />

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
