# Readings: Message Queues

A message queue is a form of asynchronous service-to-service communication used in serverless and microservices architectures. Messages are stored on the queue until they are processed and deleted. Each message is processed only once, by a single consumer. Message queues can be used to decouple heavyweight processing, to buffer or batch work, and to smooth spiky workloads.

In modern cloud architecture, applications are decoupled into smaller, independent building blocks that are easier to develop, deploy and maintain. Message queues provide communication and coordination for these distributed applications. Message queues can significantly simplify coding of decoupled applications, while improving performance, reliability and scalability.

Message queues allow different parts of a system to communicate and process operations asynchronously. A message queue provides a lightweight buffer which temporarily stores messages, and endpoints that allow software components to connect to the queue in order to send and receive messages. The messages are usually small, and can be things like requests, replies, error messages, or just plain information. To send a message, a component called a producer adds a message to the queue. The message is stored on the queue until another component called a consumer retrieves the message and does something with it.

Many producers and consumers can use the queue, but each message is processed only once, by a single consumer. For this reason, this messaging pattern is often called one-to-one, or point-to-point, communications. When a message needs to be processed by more than one consumer, message queues can be combined with Pub/Sub messaging in a **_fanout_** design pattern.

### The Fanout design pattern

Fan-out is a messaging pattern where messages are broadcast in a one-to-many arrangement. A basic example of this pattern can be seen in the functionality of a Publish/Subscribe messaging system, as Pub/Sub implies the ability to route messages from a single sender to multiple receivers.

In message-oriented middleware solutions, fan-out is a messaging pattern used to model an information exchange that implies the delivery (or spreading) of a message to one or multiple destinations possibly in parallel, and not halting the process that executes the messaging to wait for any response to that message.

# Review, Research, and Discussion

1. ### What does it mean that web sockets are bidirectional? Why is this useful?

   Whereas HTTP relies on a client request to receive a response from the server for every exchange,
   WebSockets allow for full-duplex bidirectional communication. This enables the server to send real-time updates
   asynchronously, without requiring the client to submit a request each time. this allows devices to send and receive continuous streams of data to and from any point on the network.

2. ### Does socket.io use HTTP? Why?

   No they don't, Websockets use the TCP (transmission control protocol). the reason behind this is that HTTP requires the client to send a request every time the client needs an update.

3. ### What happens when a client emits an event?

   The server will start listening to the event. When a client emmits an event, The event gets passed to the server through websockets. Its a tcp connection from the browser to the server. The connection is full duplex meaning the server can send real time data to the client and vise versa.

4. ### What happens when a server emits an event?

   When a server emits an event, all connected clients will be notified.

5. ### What happens if a client “misses” an event?

   the messages will be ignored.

6. ### How can we mitigate this?

## Term

| Term       | Defenition                                                                                                                                                                                                                                                                                                              |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Socket     | Sockets allow communication between two different processes on the same or different machines. To be more precise, it's a way to talk to other computers                                                                                                                                                                |
| Web Socket | WebSocket is bidirectional, a full-duplex protocol that is used in the same scenario of client-server communication                                                                                                                                                                                                     |
| Socket.io  | JavaScript library for realtime web applications. It enables realtime, bi-directional communication between web clients and servers.                                                                                                                                                                                    |
| Client     | In computing, a client is a piece of computer hardware or software that accesses a service made available by a server as part of the client–server model of computer networks.                                                                                                                                          |
| Server     | The server is often on another computer system, in which case the client accesses the service by way of a network.                                                                                                                                                                                                      |
| OSI Model  | The Open Systems Interconnection model is a conceptual model that characterises and standardises the communication functions of a telecommunication or computing system without regard to its underlying internal structure and technology.                                                                             |
| TCP Model  | TCP/IP Reference Model is a four-layered suite of communication protocols. It was developed by the DoD (Department of Defence) in the 1960s. It is named after the two main protocols that are used in the model, namely, TCP and IP. TCP stands for Transmission Control Protocol and IP stands for Internet Protocol. |
| TCP        | Transmission Control Protocol (TCP) is a standard that defines how to establish and maintain a network conversation by which applications can exchange data. TCP works with the Internet Protocol (IP), which defines how computers send packets of data to each other.                                                 |
| UDP        | User Datagram Protocol (UDP) is a communications protocol that is primarily used to establish low-latency and loss-tolerating connections between applications on the internet. UDP speeds up transmissions by enabling the transfer of data before an agreement is provided by the receiving party.                    |
| Packets    | In networking, a packet is a small segment of a larger message. Data sent over computer networks\*, such as the Internet, is divided into packets. These packets are then recombined by the computer or device that receives them.                                                                                      |

## Resources

[Message Queues](https://aws.amazon.com/message-queue/#:~:text=A%20message%20queue%20is%20a,once%2C%20by%20a%20single%20consumer.)
[Fan-out design pattern](<https://en.wikipedia.org/wiki/Fan-out_(software)>)
