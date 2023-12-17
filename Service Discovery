Concept: https://www.youtube.com/watch?v=3UDJvF0CMkQ&t=59s&ab_channel=sudoCODE
Article: https://www.nginx.com/blog/service-discovery-in-a-microservices-architecture/

Service discovery is the process of automatically detecting devices and services on a computer network. It helps to reduce the amount of manual configuration required from users and administrators

Why Use Service Discovery?
-------------------------
Service instances have dynamically assigned network locations. Moreover, the set of service instances changes dynamically because of autoscaling, failures, and upgrades. Consequently, your client code needs to use a more elaborate service discovery mechanism.

Discovery pattern
-----------------
There are two main service discovery patterns: client‑side discovery and server‑side discovery. Let’s first look at client side discovery.

The Client‑Side Discovery Pattern
---------------------------------

When using client‑side discovery, the client is responsible for determining the network locations of available service instances and load balancing requests across them. The client queries a service registry, which is a database of available service instances. The client then uses a load‑balancing algorithm to select one of the available service instances and makes a request.
The network location of a service instance is registered with the service registry when it starts up. It is removed from the service registry when the instance terminates. The service instance’s registration is typically refreshed periodically using a heartbeat mechanism.
eg
Netflix OSS provides a great example of the client‑side discovery pattern

The Server‑Side Discovery Pattern
---------------------------------

The client makes a request to a service via a load balancer. The load balancer queries the service registry and routes each request to an available service instance. As with client‑side discovery, service instances are registered and deregistered with the service registry.

The AWS Elastic Load Balancer (ELB) is an example of a server-side discovery router. An ELB is commonly used to load balance external traffic from the Internet. However, you can also use an ELB to load balance traffic that is internal to a virtual private cloud (VPC). A client makes requests (HTTP or TCP) via the ELB using its DNS name. The ELB load balances the traffic among a set of registered Elastic Compute Cloud (EC2) instances or EC2 Container Service (ECS) containers. There isn’t a separate service registry. Instead, EC2 instances and ECS containers are registered with the ELB itself.

The Service Registry
--------------------
The service registry is a key part of service discovery. It is a database containing the network locations of service instances. A service registry needs to be highly available and up to date. Clients can cache network locations obtained from the service registry. However, that information eventually becomes out of date and clients become unable to discover service instances. Consequently, a service registry consists of a cluster of servers that use a replication protocol to maintain consistency.

Netflix Eureka is good example of a service registry.

There are a couple of different ways to handle the registration and deregistration. One option is for service instances to register themselves, the self‑registration pattern. The other option is for some other system component to manage the registration of service instances, the third‑party registration pattern.

The Self‑Registration Pattern
-----------------------------

When using the self‑registration pattern, a service instance is responsible for registering and deregistering itself with the service registry. Also, if required, a service instance sends heartbeat requests to prevent its registration from expiring.
A good example of this approach is the Netflix OSS Eureka client.

The Third‑Party Registration Pattern
------------------------------------

When using the third-party registration pattern, service instances aren’t responsible for registering themselves with the service registry. Instead, another system component known as the service registrar handles the registration. The service registrar tracks changes to the set of running instances by either polling the deployment environment or subscribing to events. When it notices a newly available service instance it registers the instance with the service registry. The service registrar also deregisters terminated service instances.

example of a service registrar is NetflixOSS Prana
