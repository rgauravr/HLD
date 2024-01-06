
Concept: https://www.youtube.com/watch?v=YSW3UE5AFD4&t=60s&ab_channel=sudoCODE
         https://www.youtube.com/watch?v=qUydEBZmGvU&t=124s&ab_channel=ByteMonk

Practical execution using JAVA and spring  
  : https://www.youtube.com/watch?v=0LoqPg6h6wc&list=PLTyWtrsGknYdZlO7LAZFEElWkEk59Y2ak&index=49&ab_channel=TechPrimers
  
Rate limiting is a technique that controls the rate at which requests are made to a server, network, or other resource. It's used to ensure that resources are available to all users and to prevent excessive or abusive use

Different algorithm:

*Reduce Parallelism
-------------------
Queueing, or blocking requests, is the most basic way to control and manage parallelism. This method is not rate limiting per se but rather a way to control parallelism. It works by blocking or waiting for the previous request to finish before moving on to the next request. This is a great method to manage the number of concurrent requests.

The advantage of this technique is that, besides controlling parallelism, it’s also cheaper, as you don’t need a more sophisticated solution that implements rate limiting algorithms. However, this has a significant disadvantage: it doesn’t guarantee that all the requests will be serviced in a certain time period.

*Constant Rate Limiting (Throttling)
-----------------------------------
Constant rate limiting means that all requests are limited to the same number of allowed requests per unit of time. In other words, the system will allow the same number of requests every hour, every day, or every minute.
The main advantage of throttling is its simplicity: it’s straightforward to implement and easy to enforce. The main disadvantage is that while it can control the number of requests, it can’t control the amount of data transferred per request. For example, if you allow 100 requests per hour, which is 100KB, but one request transfers 2MB, you’ll get only one request per hour.

Generic Cell Rate Algorithm (GCRA)
---------------------------------
The Generic Cell Rate Algorithm (GCRA) is one of the most commonly used. It works by dividing time into cells of a certain size (usually one second). Each time a request is made, a new cell is created. If the number of requests in a cell exceeds the limit, all subsequent requests are blocked until the next cell.
GCRA is a fairly simple and effective algorithm, but it can be improved upon. One issue is that tuning the cell size to the desired limit can be challenging. If the cell size is too large, then there will be too much variability in the rate (some cells may be well below the limit while others are well above it). If the cell size is too small, the rate will be too low. Another issue is that GCRA only works on a per-second basis. This can be problematic if the rate limit is very low (such as one request per minute). In this case, a more sophisticated algorithm is needed.

Leaky Bucket
------------
The leaky bucket rate limiting algorithm is a system that uses a fixed-size bucket with a hole. The bucket can hold a specific number of tokens, and each token represents one request to your API. The tokens are added to the bucket by the user and are removed from the bucket by the server.
The token bucket is a great solution for straightforward rate limiting. The advantage of the leaky bucket rate limiting algorithm is that it’s easy to implement and maintain. However, it has a significant disadvantage: It doesn’t allow for adjustments for the length of time that it takes the user to make a request. The token bucket only allows for a fixed number of tokens per time.

Fixed Window
------------	
Fixed window rate limiting uses a fixed-size sliding window. The window represents a fixed period of time, usually one or two hours, which slides every time a request is made. The advantage of this rate-limiting algorithm is that it lets you control the amount of data transferred per request. The disadvantage of this rate-limiting algorithm is that it’s hard to understand and implement, the window needs to be of the right size, and it doesn’t guarantee that all the requests will be serviced in a certain period of time. The fixed window rate limiting algorithm is used to control the amount of data per request.

Sliding Log or Sliding Window
-----------------------------
The sliding log rate limiting algorithm uses the SLA table, which logs the user’s activities. The table contains the users’ IP addresses and the activities logged against them. The advantage of this rate-limiting algorithm is that it can control the number of requests per unit of time and the amount of data transferred per request. The disadvantage of the sliding log rate limiting algorithm is that it’s hard to implement and understand and makes it hard for a new user to determine how to use it. It also doesn’t guarantee that all requests will be serviced within a certain time.
