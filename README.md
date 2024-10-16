#  SOCKET_MODES


##  Overview

Socket Communication Performance Benchmark 



##  Getting Started

###  Usage with docker


1. Pull server and client
```sh
 docker pull 9novikov/socket_server
```
```sh
 docker pull 9novikov/socket_client
```

2. Run containers

Run server
```sh
docker run --network host -v [your_directory]:/server/volume 9novikov/socket_server ./server -mode [server_mode] -num_packets [number] -packet_size [size]
```

Run client
```sh
docker run --network host -v [your_directory]:/client/volume 9novikov/socket_client ./client -mode [client_mode] -num_packets [number] -packet_size [size]
```

Note: Replace [your_directory] with the path to the directory you want to share, [server_mode] with one of the 8 server modes, [client_mode] with one of the 2 client modes, [number] with the number of packets, and [size] with the packet size.

Server Modes:

- inet_sync_blocking
- inet_sync_nonblocking
- inet_async_blocking
- inet_async_nonblocking
- unix_sync_blocking
- unix_sync_nonblocking
- unix_async_blocking
- unix_async_nonblocking

Client Modes:

- inet
- unix

Example:
```sh
docker run --network host -v /path/to/directory:/server/volume 9novikov/socket_server ./server -mode inet_sync_blocking -num_packets 10000 -packet_size 100
docker run --network host -v /path/to/directory:/client/volume 9novikov/socket_client ./client -mode inet -num_packets 10000 -packet_size 100
```

## Benchmarks
https://docs.google.com/document/d/1ThdwfCbWYLF0z1t-MQ3mQWd4kwlROvh0ThqrN9elEm0/edit?usp=sharing
