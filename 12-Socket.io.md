# Readings: Socket.io

1. ### Socket.io

Socket.IO is a library that enables real-time, bidirectional and event-based communication between the browser and the server. It consists of:

a Node.js server: Source | API
a Javascript client library for the browser (which can be also run from Node.js)

Computer network protocol WebSocket A diagram describing a connection using WebSocket International standard RFC 6455 Developed by IETF Industry Computer science Connector type TCP Website Official website WebSocket is a computer communications protocol, providing full-duplex communication channels over a single TCP connection.

To achieve compatibility, the WebSocket handshake uses the HTTP Upgrade header[1] to change from the HTTP protocol to the WebSocket protocol.

onclose = function ( event ) { onSocketClose ( event ); }; // Fired when a connection with a WebSocket has been closed because of an error, socket .

It is better to use tokens or similar protection mechanisms to authenticate the WebSocket connection when sensitive (private) data is being transferred over the WebSocket. A live example of vulnerability was seen in 2020 in the form of Cable Haunt.

While the WebSocket protocol itself is unaware of proxy servers and firewalls, it features an HTTP-compatible handshake, thus allowing HTTP servers to share their default HTTP and HTTPS ports (80 and 443 respectively) with a WebSocket gateway or server.

#### benefits of Socket.IO

Writing a real-time application with popular web applications stacks like LAMP (PHP) has traditionally been very hard. It involves polling the server for changes, keeping track of timestamps, and it is a lot slower than it should be.

Sockets have traditionally been the solution around which most real-time systems are architected, providing a bi-directional communication channel between a client and a server. This means that the server can push messages to clients. Whenever an event occurs, the idea is that the server will get it and push it to the concerned connected clients.

Socket.IO is quite popular, it is used by Microsoft Office, Yammer, Zendesk, Trello,. and numerous other organizations to build robust real-time systems. It one of the most powerful JavaScript frameworks on GitHub, and most depended-upon NPM (Node Package Manager) module. Socket.IO also has a huge community, which means finding help is quite easy.

WebSocket is a computer communications protocol, providing full-duplex communication channels over a single TCP connection.

WebSocket is distinct from HTTP. Both protocols are located at layer 7 in the OSI model and depend on TCP at layer 4. Although they are different, RFC 6455 states that WebSocket "is designed to work over HTTP ports 443 and 80 as well as to support HTTP proxies and intermediaries", thus making it compatible with HTTP. To achieve compatibility, the WebSocket handshake uses the HTTP Upgrade header to change from the HTTP protocol to the WebSocket protocol.

#### How does that work?

## Review, Research, and Discussion

4- Can an application be both a socket server and a socket connection?

You can use the same socket for whatever you want, as long as your protocol handles it.

1. #### What is the benefit of transforming data into packets?

enable new innovations, services, and business opportunities, they are also the most cost-effective, efficient, and scalable networks for content delivery.

2. #### UDP is often refereed to as a connectionless protocol. Why is this?

   because it is analogous to sending a letter where you don’t acknowledge receipt.

3. #### Can a socket server application have multiple socket connections?

Multiple connections on the same server can share the same server-side IP/Port pair as long as they are associated with different client-side IP/Port pairs,

4. #### Can a socket connection application be connected to multiple socket servers?

No we cannot.

5. #### Can an application be both a socket server and a socket connection?

## Yes you can but it needs to be handled by your protocol.

## Vocabulary & Terms

| Term                     | Defenition                                                                                                                                                                                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Observer Pattern         | sometimes refered to a publisher-subscriber pattern, where many instances are notified and affected by the change of one event.                                                                                           |
| Listener                 | a procedure in JavaScript that waits for an event to occur.                                                                                                                                                               |
| Event Handler            | invoking a specific piece of code when a particular action happens                                                                                                                                                        |
| Event Driven programming | Everything starts by following an event. The event could be the DOM is loaded, or an asynchronous request that finishes fetching, or a user clicking an element or scrolling the page, or the user types on the keyboard. |
| Event Loop               | responsible for executing the code, collecting and processing events, and executing queued sub-tasks                                                                                                                      |
| Event Queue              | responsible for sending new functions to the stack for processing.                                                                                                                                                        |
| Call Stack               | a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions                                                                    |
| Emit                     | creation of an event                                                                                                                                                                                                      |
| Raise                    | defining an exception                                                                                                                                                                                                     |
| Trigger                  | The trigger() method triggers the specified event and the default behavior of an event (like form submission) for the selected elements.                                                                                  |
| database                 | a javascript SQL database. It allows you to create a relational database and query it entirely in the browser.                                                                                                            |

---
