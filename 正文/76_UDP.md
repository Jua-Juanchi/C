# 网络基础 - UDP (用户数据报协议)

## 1.1 什么是UDP

### 1.1.1 UDP的作用和特点

```md
    UDP（用户数据报协议）是一种在计算机网络中使用的传输层协议，与TCP相比具有不同的特点。UDP主要用于快速传输数据，特点如下：

    无连接：UDP是无连接的协议，不需要建立连接和断开连接的握手过程，这使得数据传输更加迅速。

    简单性：UDP的协议头相对较小，使得数据包的开销较小，适合用于实时传输和广播等场景。

    不可靠性：UDP不提供数据可靠性和完整性的保障，数据包可能会丢失、乱序或重复，因此需要应用层自行处理错误和重传。
```

## 1.2 UDP的基本功能

### 1.2.1 数据传输

```md
    UDP的基本功能是将数据从一个端点传输到另一个端点，它将数据分割成小的数据包并添加源端口和目标端口信息，然后将这些数据包通过网络传输。UDP不关心数据包的顺序和可靠性。
```

## 1.3 UDP的特点和不可靠性

### 1.3.1 无连接

```md
    UDP是一种无连接的协议，它不需要像TCP那样进行连接的建立和断开，因此通信的开销较低。这使得UDP适用于需要快速数据传输的场景，如音频和视频流。
```

### 1.3.2 不可靠性

```md
    UDP的不可靠性表现在以下方面：

    丢包：UDP数据包在传输过程中可能会丢失，不提供重传机制。

    乱序：数据包可能以不同的顺序到达目标端，应用层需要自行处理数据包的顺序问题。

    重复：UDP数据包可能会被重复传输，接收端需要处理重复数据包。
```

## 1.4 C语言中的UDP编程

### 1.4.1 创建套接字

```md
    在C语言中，可以使用Socket API来创建UDP套接字，套接字是网络通信的端点，用于数据传输。UDP套接字可以通过socket函数创建。
```

### 1.4.2 数据传输

```md
    数据传输可以使用sendto函数来发送UDP数据包，需要指定目标地址和端口。接收数据则使用recvfrom函数，接收方会获得数据包的源地址和端口信息。
```

### 1.4.3 接收数据

```md
    UDP的接收是非阻塞的，如果没有数据可接收，recvfrom函数会立即返回，应用层需要自行处理接收到的数据包，包括解析数据和处理不可靠性问题。

    总之，UDP是一种快速但不可靠的协议，适用于需要实时数据传输和广播的场景，但应用层需要额外的处理来处理数据的可靠性和完整性。
    在C语言中，可以使用Socket API来进行UDP编程。
```
