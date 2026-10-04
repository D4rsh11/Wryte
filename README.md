# Wryte

![Go](./assets/golang.webp)

A distributed key-value store written in Go that uses consistent hashing to distribute data across multiple servers.

## Features

1. **Consistent Hashing**  
   Maps keys to specific nodes to keep data distribution stable and balanced across servers.

2. **Robin Hood Hashing**  
   Uses open addressing with Robin Hood hashing for efficient collision handling and lookup.

3. **Thread Pool**  
   A worker pool manages concurrent `GET`, `PUT`, and `DELETE` operations on the hashmap.

4. **Flexible Values**
   - **Key:** String
   - **Value:** JSON data

## Limitations

1. Nodes cannot currently be added or removed at runtime.
2. No replication — a value exists on only one node.

## Planned Improvements

1. **ZooKeeper Integration**  
   Use ZooKeeper for node discovery and managing node IPs/URLs.

2. **Replication**  
   Replicate data across nodes for fault tolerance.

3. **Dynamic Scaling**  
   Support adding and removing nodes while the system is running.

## How to Test

Clone the repository and run:

```bash
make run-all