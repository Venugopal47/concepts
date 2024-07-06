# Caching

## What is Caching

Caching -- pronounced "cashing" -- is the process of storing data in a cache, which is a temporary storage area that facilitates faster access to data with the goal of improving application and system performance.

A common example of caching is a web browser that stores page content on a local disk for a designated period of time. When the user first visits the website, the content is downloaded from the web server and saved to a local directory. If the user revisits the website, the content comes from the local cache rather than the server. In this way, page content loads much faster into the browser than it would if it were downloaded from the web server. This saves the user time, reduces network traffic and minimizes the load on the web server.

The idea behind caching is to temporarily copy data to a location that enables an application or component to access the data faster than if retrieving it from its primary source.

![image](https://github.com/Venugopal47/concepts/assets/97158707/1b29f41e-2b34-4251-b21d-979d254aeda5)

## Key Concepts Of Caching

### 1. Cache

A cache is a temporary storage area that holds a subset of data that is likely to be needed again. It can be implemented in memory (RAM), on disk, or even in a distributed manner across multiple nodes.

### 2. Cache Hit

When a requested piece of data is found in the cache, it is considered a cache hit. This results in faster retrieval since the data is already in memory or closer to the requester.

### 3. Cache Miss

If the requested data is not found in the cache, it's called a cache miss. This requires fetching the data from the original source (e.g., a database or a remote server), which is slower compared to a cache hit.

### 4. Eviction Policy

Caches have mechanisms to manage their size and contents. Eviction policies determine which items are removed from the cache when it reaches its capacity limit.

### 5. Cache Invalidation

Ensuring that the cached data remains consistent with the original data source is crucial. Cache invalidation involves updating or removing cached items when the source data changes to maintain data integrity.

## Benefits of Caching

* Improved Performance: Caching reduces the latency associated with fetching data from slower storage systems or computing resources.
* Scalability: Caching helps distribute the load on backend systems by serving frequently requested data from a cache, thus reducing the number of requests that hit the primary data   source.
* Cost Efficiency: By reducing the need for frequent access to expensive resources (like databases or APIs), caching can lower operational costs.

## Types of Caching

https://youtu.be/IA8au8Qr3lo

### 1. In-Memory Caching

Applications often use a system's main memory to cache data stored on disk. For example, a database management system (DBMS) might use caching for read-heavy workloads or complex query.

### 2. Virtual memory caching

 A computer's memory management unit (MMU) often includes a Translation Lookup Buffer (TLB) to cache recent translations between virtual and physical addresses.

### 3. Server-side caching

Web applications often cache data that comes from other systems. For example, a web application might cache data it retrieves regularly from a back-end database.

### 4. CDN caching

Content delivery networks (CDNs) store cached data in multiple proxy servers that are geographically distributed to serve content to users in closer proximity to where they reside, helping to improve a web application's performance.

![image](https://github.com/Venugopal47/concepts/assets/97158707/d6f2d367-2559-4bcf-89df-816dfe7e4a53)


### 5. Storage controller caching

A storage controller might include a local cache to help streamline input/output (I/O) operations. A controller cache can improve operations between the controller and application, as well as between the controller and disk.

### 6. DNS caching

Domain Name System (DNS) servers often cache DNS lookup data to help resolve host names to Internet Protocol (IP) addresses more quickly.

![image](https://github.com/Venugopal47/concepts/assets/97158707/67df06a0-4d52-410f-88d1-b4f25aacd5b9)


### 7. CPU caching

Most central processing units (CPUs) include high-speed caches, such as L1 and L2, that sit between the computer's main memory and the processor, providing the CPU with faster access to program instruction sets than the main memory can deliver.

## Conclusion

Each caching approach has its strengths and is suited for different scenarios based on the specific performance and scaling challenges of project. Integrating caching effectively requires careful consideration of data access patterns, consistency requirements, and overall system architecture.

## References

<https://www.techtarget.com/whatis/definition/caching>
