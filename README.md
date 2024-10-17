# 5a_Create_Socket_for_HTTP_for_webpage_upload_and_download
## AIM :
To write a PYTHON program for socket for HTTP for web page upload and download
## Algorithm

1.Start the program.
<BR>
2.Get the frame size from the user
<BR>
3.To create the frame based on the user request.
<BR>
4.To send frames to server from the client side.
<BR>
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
<BR>
6.Stop the program
<BR>
## Program
```
DEVOLOPED BY : SREE NIVEDITAA SARAVANAN
REGISTER NUMBER : 212223230213
```
```
import socket

def handle_request(request):
    # Process the HTTP request and generate an appropriate response
    response = "HTTP/1.1 200 OK\nContent-Type: text/html\n\n<h1>Hello, World!</h1>"
    return response

def main():
    host = ''  # Listen on all available interfaces
    port = 8080  # Port number for HTTP server

    server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    server_socket.bind((host, port))
    server_socket.listen(5)  # Listen for incoming connections

    print("HTTP server listening on port", port)

    while True:
        client_socket, client_address = server_socket.accept()  # Accept a new connection
        print("Client connected:", client_address)

        request_data = client_socket.recv(1024).decode()  # Receive request data from the client
        print("Received request:\n", request_data)

        response = handle_request(request_data)  # Handle the request
        client_socket.sendall(response.encode())  # Send the response back to the client

        client_socket.close()  # Close the connection

if _name_ == "_main_":
    main()

# 
# copy and paste to any browser http://localhost:8080
```
## OUTPUT

![Screenshot 2024-10-17 110101](https://github.com/user-attachments/assets/2a2ca0f9-0d96-4d5e-919e-15e83149ef93)

![{063DA6F3-139E-4895-B178-22BA0BF51682}](https://github.com/user-attachments/assets/0763c1cd-2fc7-4e4a-b0ca-8c8fb76ccb00)

## Result
Thus the socket for HTTP for web page upload and download created and Executed
