Concepts:
https://www.youtube.com/watch?v=RIcNswROzCc&list=PLTCrU9sGyburBw9wNOHebv9SjlE4Elv5a&index=19&ab_channel=sudoCODE

What is replication?
Data Replication is the process of storing data in more than one site or node. It is simply copying data from a database from one server to another server.

Advantage of replication/Why replication is needed?
*Availability
*Fault toleration issue
*Scalable
*High throughput

Types of algorithms for implementing Database Replication?
*Single Leader Replication
*Multi-Leader Replication
*Leaderless Replication

Single Leader Replication
-------------------------
So in leader based architecture, client (application server) requests are sent to leader DB first and after that leader sends the data changes to all of its followers as a part of the replication log.
Whenever a client wants to read data from the database then it can query either leader or any of the follower (Yes there is generally more than just one follower to make the system highly available). However, writes to the database is only accepted on the leader by the client.
Now whenever a follower dies our application will not get impacted as there is not just a single node of data. Our application can read from other followers as well and hence this makes our system highly Read Scalable

Types of replication?

Synchronous replication 
-----------------------
When changes are made to the primary database, they are immediately replicated to the replica databases before the write operation is deemed complete. This is known as synchronous replication. In other words, before the write operation is acknowledged by the primary database, the replica databases must confirm that they have received and processed the changes.  As soon as data is copied from the source database to the target database in this mode, the write operation is not deemed complete until the target database confirms that the data was received. As a result, the source database must wait for the target database’s confirmation, which ensures that the data is consistent between the source and target databases but can slow down write operations. In master-slave replication, where data consistency is crucial, synchronous replication is frequently used.

Since all changes made to the primary database are immediately reflected in the replica databases, synchronous replication ensures that there is strong consistency between the primary and replica databases. By doing this, the chance of data loss or inconsistency is decreased and the data is ensured to be consistent across all databases.

Asynchronous replication
------------------------
Changes made to the primary database do not always replicate to the replica databases in asynchronous replication, which is a type of database replication.

The changes are instead queued for later replication to the replicas. Without waiting for the target database to acknowledge receipt of the data, data is copied from the source database to the target database at a later time in this mode. Although it might lead to data inconsistency between the source and target databases, this can speed up write operations. In master-master replication, where data consistency can be attained through conflict resolution mechanisms, asynchronous replication is frequently used.

The write operation on the primary database and the update on the replica databases happen at different times in asynchronous replication. Since the data on the replica databases might not update right away to reflect changes made to the primary database, this delay could lead to momentary inconsistencies between the primary and replica databases.
As write operations can be completed quickly without waiting for confirmation from the replica databases, asynchronous replication can also benefit performance. Additionally, the write operation can still be finished on the primary database, ensuring that the system is still available if one or more replica databases are down.

Semi-synchronous replication
----------------------------
Database replication that combines aspects of synchronous and asynchronous replication is known as semi-synchronous replication. In semi-synchronous replication, modifications made to the primary database are promptly replicated to at least one replica database while other replicas may be updated asynchronously.

In this mode, which combines synchronous and asynchronous replication, the source database sends data to the target database after waiting for a predetermined amount of time or until a predetermined amount of data has accumulated. With this mode, data consistency between the source and target databases is balanced with write operation performance.

Note: Here the write operation on the primary is not deemed finished until at least one replica database certifies that the changes have been received and processed. In addition to offering better performance than fully synchronous replication, this ensures that the primary and replica databases share some degree of strong consistency
