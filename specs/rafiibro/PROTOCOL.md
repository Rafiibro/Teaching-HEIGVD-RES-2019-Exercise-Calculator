## What transport protocol do we use?

We are going to use TCP protocol.

## How does the client find the server (addresses and ports)?

The client connects to the address/port given by the server. 

Ports are fixed, we are going to use port 8080.

## Who speaks first?

The client speaks first, he asks for a connection.

## What is the sequence of messages exchanged by the client and the server?

The client asks connection to the server.

The server accepts the connection.

The server waits for a request

if client send one operation : 

    The client sends the request (gives two parameters with number and one operand)

    The client puts himself on waiting mode

    the server receives the request

    The server sends the answer

    The client receive the answer

    The client exists waiting mode
    
    reset to the server waits for another request
    
else if client send end

    The server closes the server socket

    The client closes the client socket



## What happens when a message is received from the other party? 

he put himself on blocking mode

## What is the syntax of the messages? How we generate and parse them?

Client messages : 

    Message have to contain, two numbers and one operand, each operator is send by his symbol.

    each parameter is seperated by a " " and the string finish with a "\n"

    the server can calculate " + - * / "
    
        The client can send an "END" request, and wait for the answer before deconnecting

Server messages : 

    the server send a string with the answer, the answer is finished with a "\n"

    The client can send an "END" request, if the server receive it, he send "OK".

## Who closes the connection and when?

The Client stops the connection when he receive "OK"
