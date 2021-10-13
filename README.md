**Design Patterns**

- **Singleton**
- **Prototype**

1. **What is Singleton ?**

The Singleton Pattern is one of the best-known patterns in software engineering.

1. How does **Singleton** happen ?
1. What is **Lazy Singleton**?
1. What are **Lazy Loading** and **Eager Loading**? 

1. **What is Prototype ?**

Prototype is a creational design pattern that allows cloning objects, even 	      	complex ones, without coupling to their specific classes.

1. How does **Prototype** happen ?
1. What are **Shallow Copy** and **Deep Copy**?

**Httpes** 

- Http / 1.1
- Http / 2
- Http / 3

- **How is Http / 1.1 working ?**
  - Http / 1.1 uses **TCP** to communicate between computers.
  - TCP provides the connection. 
    - Computer A is sends one TCP Sync message to the computer B. 
    - Computer B sends a TCP Sync + Ack message that it has received computer A's request.
    - Computer A sends TCP Ack message to computer B.
    - Computer B receives an Ack "TCP connection is Established".
    - And provides the TCP connection.
  - Http / 1.1 uses **TLS** as Security protocol.
    - The user requests a secure connection from the internet server
    - The internet server sends the **public key** along with the **certificate** to the user
    - The internet browser used by the user checks whether the certificate sent by the server comes from a **trusted certificate authority** and whether the certificate is valid
    - The internet browser the user is using generates a random **symmetric encryption key**. Then, using the public key of the internet server, it encrypts this symmetric encryption key and sends it to the internet server it is trying to connect to
    - The Internet server obtains the symmetric key by decrypting this message, which is encrypted with its own public key, with its **private key**
    - The internet server then sends the data it will send to the user using this **symmetric key** it has obtained
    - The user securely views the web page by **decrypting** the data from the web server with the same **symmetric key**.
- **How is Http /2 working ?**
  - Compromise mechanism that allows clients and servers to choose HTTP1.1, 2.0 and potentially non-HTTP protocols.
  - Maintaining a high level of compatibility with HTTP 1.1 (eg **request methods**, **status codes**, **uniform resource identifiers - URI** and **other header fields** - **compatibility with header field**)
  - Reducing latency to increase page load speed in web browsers by considering the following: 
    - Data compression of HTTP headers
    - Server push technologies
    - Pipeline of Demands
    - Resolving head-of-line blocking in HTTP 1
    - Multiplexing multiple requests on a single TCP (Transmission Control Protocol) connection
  - Supporting common HTTP instances such as desktop web browsers, mobile web browsers, web APIs (Application programming interface), web servers of various scales, firewalls and content delivery networks (CDN)


- **What are the differences between Http / 1.1 and Http / 2 ?**
  - HTTP/2; request methods, status codes, and uniform resource identifiers - leaving most of the high-level syntax of HTTP 1.1, such as the URI, intact. The element that has been changed is the way the data is framed and moved between the server and the client.
  - High-throughput websites minimize the number of requests required to render an entire page by minifying resources such as images and text scripts. But the minifying method is neither as convenient nor efficient as it should, and it can still request separate HTTP connection to reach the page and minified resources. HTTP/2 allows impulsive content to respond to the server with data for more queries than the client is requesting. This allows the server to provide data that a web browser will need to render a web page, without waiting for the browser to examine the initial response and without the overhead of an extra request cycle.
  - Additional performance improvements in the first draft of HTTP/2 (it was a copy of SPDY) come from HTTP 1 (even if the HTTP Pipeline was used) header compression and multiplexing requests and responses to avoid header line blocking in requests' priorities.

- **How is Http / 3 working ?**
  - HTTP semantics are consistent across versions: the same request methods, status codes, and message fields are typically applicable to all versions. The differences are in the mapping of these semantics to underlying transports. Both HTTP/1.1 and HTTP/2 use TCP as their transport. 
  - HTTP/3 uses QUIC, a transport layer network protocol which uses user space congestion control over the User Datagram Protocol (UDP). 
  - The switch to QUIC aims to fix a major problem of HTTP/2 called "head-of-line blocking": because the parallel nature of HTTP/2's multiplexing is not visible to TCP's loss recovery mechanisms, a lost or reordered packet causes all active transactions to experience a stall regardless of whether that transaction was impacted by the lost packet. Because QUIC provides native multiplexing, lost packets only impact the streams where data has been lost.

- **What are the differences between Http / 2 and Http / 3 ?**
  - Unlike HTTP/2, HTTP/3 is built on UDP rather than TCP.
  - Thanks to the integrated TLS 1.3 encryption, HTTP/3 forgoes an additional request for encryption at TLS level (handshakes), thus avoiding unnecessary security queries.
  - Unlike HTTP/2, HTTP/3 only supports encrypted connections due to its integrated TSL 1.3 encryption.
