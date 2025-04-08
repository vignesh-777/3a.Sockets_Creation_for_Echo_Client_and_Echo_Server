# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM

#### Echo Server (server.py)
```py
import socket

# Create TCP socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind to localhost and port
server_socket.bind(('localhost', 12345))
server_socket.listen(1)
print("Server is waiting for connection...")

conn, addr = server_socket.accept()
print("Connected by", addr)

# Receive and echo back
while True:
    data = conn.recv(1024)
    if not data:
        break
    print("Received:", data.decode())
    conn.sendall(data)

conn.close()

```

#### Echo Client (client.py)
```py
import socket

# Create TCP socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to the server
client_socket.connect(('localhost', 12345))

# Send message
message = input("Enter a message to send: ")
client_socket.sendall(message.encode())

# Receive echoed message
data = client_socket.recv(1024)
print("Echoed from server:", data.decode())

client_socket.close()

```
## OUPUT

#### server.py
![Screenshot 2025-04-08 110252](https://github.com/user-attachments/assets/13c3058e-90de-44b8-bc70-c749df3d3559)

#### client.py

![Screenshot 2025-04-08 110258](https://github.com/user-attachments/assets/3e78bcd4-1f75-4bb5-8ebf-47b31bf18367)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
