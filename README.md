# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
REG NO: 212222220021

NAME: MAITHREYAN D
## SERVER.PY
```
import socket

# Create a socket object
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Define the server address and port
host = '127.0.0.1'  # Localhost
port = 12345        # Port to listen on

# Bind the socket to the address and port
server_socket.bind((host, port))

# Listen for incoming connections (max 5 clients in the waiting queue)
server_socket.listen(5)
print(f"Server listening on {host}:{port}...")

while True:
    # Accept a connection from a client
    client_socket, client_address = server_socket.accept()
    print(f"Connection established with {client_address}")

    # Receive data from the client
    data = client_socket.recv(1024).decode('utf-8')
    print(f"Received data: {data}")

    # Send the data back to the client (echo)
    client_socket.send(data.encode('utf-8'))
    print(f"Sent data: {data}")

    # Close the client connection
    client_socket.close()
    print(f"Connection with {client_address} closed.\n")
```
## CLIENT.PY
```
import socket

# Create a socket object
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Define the server address and port
host = '127.0.0.1'  # Server's IP address
port = 12345        # Server's port

# Connect to the server
client_socket.connect((host, port))
print(f"Connected to server at {host}:{port}")

# Send data to the server
message = input("Enter a message to send to the server: ")
client_socket.send(message.encode('utf-8'))
print(f"Sent data: {message}")

# Receive the echoed data from the server
data = client_socket.recv(1024).decode('utf-8')
print(f"Received echoed data: {data}")

# Close the connection
client_socket.close()
print("Connection closed.")
```
## OUTPUT:
## SERVER.PY
![server py](https://github.com/user-attachments/assets/0c3ccf65-f0c4-4261-a8eb-192574fd77c9)
## CLIENT.PY
![client py](https://github.com/user-attachments/assets/50fe7880-8efd-4c2e-90af-2f663ea2ae6d)

## RESULT:
The program is executed successfully
