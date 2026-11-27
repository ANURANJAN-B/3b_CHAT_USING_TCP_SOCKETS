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


## server:
```
import socket

# Create server socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind IP address and port
s.bind(('localhost', 12345))

# Listen for client connection
s.listen(1)
print("Server waiting for connection...")

# Accept client connection
conn, addr = s.accept()
print("Client connected:", addr)

while True:
    # Receive message from client
    msg = conn.recv(1024).decode()
    print("Client:", msg)

    if msg.lower() == "exit":
        break

    # Send message to client
    reply = input("Server: ")
    conn.send(reply.encode())

    if reply.lower() == "exit":
        break

conn.close()
s.close()
```


```




import socket

# Create client socket
c = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to server
c.connect(('localhost', 12345))

print("Connected to server")

while True:
    # Send message to server
    msg = input("Client: ")
    c.send(msg.encode())

    if msg.lower() == "exit":
        break

    # Receive message from server
    reply = c.recv(1024).decode()
    print("Server:", reply)

    if reply.lower() == "exit":
        break

c.close()


```

## OUPUT

## server:

<img width="462" height="425" alt="Screenshot 2026-11-27 085345" src="https://github.com/user-attachments/assets/d342a781-7153-4878-8fb7-3c3bf62f4e81" />


## client:


<img width="550" height="488" alt="Screenshot 2026-11-27 085352" src="https://github.com/user-attachments/assets/2a022574-a38c-46ef-b4bc-0d8e2c6b518e" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
