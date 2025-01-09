<ol>
<li> sys/socket.h: Contains socket-related functions, such as socket(), bind(), and listen().</li>
<li> netdb.h: Provides definitions for handling network-related information.</li>
<li>serversocket = socket(AF_INET, SOCK_STREAM, 0);
       This creates a socket for the server. Here:

    AF_INET specifies the address family (IPv4).
    SOCK_STREAM specifies that the server will use the TCP protocol.</li>
<li> bzero() is a library function defined in <string.h>. It is used to set all the bytes of a given memory region to zero.</li>
<li>INADDR_ANY is a special constant in socket programming that represents any valid IP address on the local machine. using INADDR_ANY means the server will accept connections on any available network interface. </li>
  <li>The sockaddr_in structure is used to define an IPv4 address and port number for communication in a network. It’s commonly used when configuring sockets to either listen for incoming connections or connect to a server.
                                   
    struct sockaddr_in { 
    
                                hort sin_family; // Address family (AF_INET for IPv4)
    
                           unsigned short sin_port;  // Port number (in network byte order)
    
           struct in_addr sin_addr;  // IP address (in network byte order)
           
             char sin_zero[8];        // Padding to make structure size equal to sockaddr
        };

  </li>
</ol>
# Summary of TCP Connection Steps:

    Create a socket for the server (socket()).
    Initialize server's address (IP and port).
    Bind the server socket to the specified address (bind()).
    Listen for incoming client connections (listen()).
    Accept a client connection and create a new socket for communication (accept()).
    Read the client's message and send a response (read() and write()).
    Close the client and server sockets (close()).
