# YS Packet Generator

This is a packet generator Python package.

## Installation

```
pip install ys-packet-generator
```


## Usage

There should be two sides: 
- Client side - which generates the packets
- Server side - which receive the packets

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--_oO-g2yr--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/22l5f9ehc4dq5y6rbmss.png"  width="500">


### On the client side

Send UDP packets - unlimited loop

Each packet's data is an increasing index that repeats every 32bit
```
@param: ip (str) - destination IP address
        port (int) - destination port
        bandwidth (int) - the bandwidth to allocate
        packet_size (int) - size of each packet
        debug (bool) - use prints or not
@returns: None
```
```
from ys-packet-generator import generator as pg
...
pg.send(...)
```

### On the server side
Receive UDP packets from the generator - unlimited loop
Each packet is an increasing index that repeats every 32bit
```
@param: ip (str) - local IP address
        port (int) - local port
        buffer_size (int) - buffer size to reveive packets
        full_debug (bool) - print all debug prints
        debug (bool) - print only missed packet's index
@returns: None
```
```
from ys-packet-generator import server 
...
server.receive(...)
```

<!-- This is a simple example package. You can use
[Github-flavored Markdown](https://guides.github.com/features/mastering-markdown/)
to write your content. -->