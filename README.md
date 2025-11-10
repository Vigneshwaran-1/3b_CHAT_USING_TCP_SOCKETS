# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM

## At server
~~~
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()

while True:
    ClientMessage = c.recv(1024).decode()
    print("Client > ", ClientMessage)
    msg = input("Server > ")
    c.send(msg.encode())
~~~

## At client

~~~
import socket

s = socket.socket()
s.connect(('localhost', 8000))

try:
    while True:
        msg = input("Client > ")
        s.send(msg.encode())
        reply = s.recv(1024).decode()
        print("Server > ", reply)
        if msg.lower() == "exit":
            break
finally:
    s.close()
 ~~~
## OUPUT

## At server

<img width="604" height="197" alt="3 -b1" src="https://github.com/user-attachments/assets/6eaed64f-c5d6-40a4-8383-b77206148df2" />


## At client

<img width="609" height="167" alt="3 -b2" src="https://github.com/user-attachments/assets/a690b968-fc6c-441a-ba3a-b48544289193" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
