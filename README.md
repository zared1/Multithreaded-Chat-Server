# Multithreaded Chat Server

This is a simple Python TCP chat server that handles multiple clients using threads. Each client connection is managed in a separate thread, allowing the server to handle multiple clients simultaneously. The server also allows sending messages from the server console to connected clients.

## Features

* Handles multiple clients using threading
* Receives and prints messages from clients
* Server console can send messages to all connected clients (requires maintaining a client list)
* Uses TCP sockets (`socket.SOCK_STREAM`)

## How to Run

1. Clone or download the repository.
2. Run the server script:

```bash
python server.py
```

3. Connect with a TCP client like `nc` (netcat):

```bash
nc localhost 10000
```

4. Type messages in the client to send them to the server.
5. Type messages in the server console to send messages to all connected clients (requires implementing `connected_clients` list).

## Notes

* Each client connection is handled in a separate thread using `threading.Thread`.
* Currently, the server receives only one message per client connection. You can extend it to continuously receive messages by looping inside `handle_client`.
* The `connected_clients` list is referenced in the console message sending loop but is not implemented. You need to maintain a list of active client sockets for server messages to be broadcast correctly.
* This project provides a base to build a fully functional multithreaded chat server, including private messaging, broadcasting, and client management.
