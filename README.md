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

## PROGRAM

``` 
client:
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
4/17/24, 5:02 PM arbasil05/2c.ARP_RARP_PROTOCOLS 
https://github.com/arbasil05/2c.ARP_RARP_PROTOCOLS/tree/main 2/2 
 ```
 
server: 
 ```
import socket                                                              
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
REG NO: 
ip=input("Enter logical Address : ") 
s.send(ip.encode()) 
print("MAC Address",s.recv(1024).decode())
```
```
OUTPUT:
```
![Screenshot (305)](https://github.com/Ragavan762006/2c.ARP_RARP_PROTOCOLS/assets/144870714/79c9f02a-fb08-4d2b-8555-719fa93ef7f4)
## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
