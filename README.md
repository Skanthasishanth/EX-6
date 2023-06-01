# IMPLEMENTATION OF PING COMMAND

# EXP : 6
# DATE : 12-04-2023
# AIM :
To write the python program for simulating ping command.
# ALGORITHM :
1. Start the program.
2. Include necessary package in java.
3. To create a process object p to implement the ping command.
4. Declare one Buffered Reader stream class object.
5. Get the details of the server : 
(a) Length of the IP address.
(b) Time required to get the details.
(c) Send packets, receive packets and lost packets.
(d) Minimum, maximum and average times.
6. Print the results.
7. Stop the program.
# PROGRAM:
# CLIENT:
```python3
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost'8000))
s.listen(5)
c,addr=s.accept()
while True:
   hostname=c.recv(1024).decode()
try:
   c.send(str(ping(hostname, verbose=False)).encode())
except KeyError:
   c.send("Not Found".encode())
```
# SERVER:
```python3
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   ip=input("Enter the website you want to ping ")
   s.send(ip.encode())
   print(s.recv(1024).decode())
```

# CLIENT OUTPUT :


![client](https://github.com/Skanthasishanth/EX-6/assets/118298456/5ffd2602-600b-4562-b290-dc013d9fe7bf)

# SERVER OUTPUT :


![server](https://github.com/Skanthasishanth/EX-6/assets/118298456/7c9f475c-2da0-4b2b-aacc-c99aabe90dcb)


# RESULT:
Thus, the python program for simulating ping command was successfully executed.
