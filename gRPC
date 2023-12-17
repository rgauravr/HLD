Video : https://www.youtube.com/watch?v=iv9ylBYgACE&ab_channel=TechPrimers
Article: https://grpc.io/docs/what-is-grpc/introduction/

gRPC is an open-source API architecture and system that uses the Remote Procedure Call (RPC) model. It's a way to send data across networks. gRPC can be used to communicate between services in a microservice architecture.
It uses protocol buffer to transfer the data from client to server or vice versa.

Overview
--------
In gRPC, a client application can directly call a method on a server application on a different machine as if it were a local object, making it easier for you to create distributed applications and services. As in many RPC systems, gRPC is based around the idea of defining a service, specifying the methods that can be called remotely with their parameters and return types. On the server side, the server implements this interface and runs a gRPC server to handle client calls. On the client side, the client has a stub (referred to as just a client in some languages) that provides the same methods as the server.
gRPC clients and servers can run and talk to each other in a variety of environments - from servers inside Google to your own desktop - and can be written in any of gRPC’s supported languages. So, for example, you can easily create a gRPC server in Java with clients in Go, Python, or Ruby. In addition, the latest Google APIs will have gRPC versions of their interfaces, letting you easily build Google functionality into your applications

Working with Protocol Buffers
-----------------------------
By default, gRPC uses Protocol Buffers, Google’s mature open source mechanism for serializing structured data (although it can be used with other data formats such as JSON).
he first step when working with protocol buffers is to define the structure for the data you want to serialize in a proto file: this is an ordinary text file with a .proto extension. Protocol buffer data is structured as messages, where each message is a small logical record of information containing a series of name-value pairs called fields. Here’s a simple example:

message Person {
  string name = 1;
  int32 id = 2;
  bool has_ponycopter = 3;
}
