# pa2
Programming Assignment 2

1. Why do you see a difference in webpage fetch times with small and large router buffers?

Smaller router buffer will have a shorter queue, the number of packets queued is less resulting in a shorter waiting time. In addition buffer too large limites TCP congestion control which rely on occasional packet lost.

2. Bufferbloat can occur in other places such as your network interface card (NIC). Check the output of ifconfig eth0 on your VirtualBox VM. What is the (maximum) transmit queue length on the network interface reported by ifconfig? For this queue size and a draining rate of 100 Mbps, what is the maximum time a packet might wait in the queue before it leaves the NIC?

txqueuelen: 1000
1000 packets * 1500 bytes * 8 bits / (100*10^6 b/s) = 0.12s

3. How does the RTT reported by ping vary with the queue size? Write a symbolic equation to describe the relation between the two (ignore computation overheads in ping that might affect the final result).

RTT is directly proportional to qsize
therefore, RTT = k * qsize

4. Identify and describe two ways to mitigate the bufferbloat problem.
The first way to address it is to reduce the queue size having a shorter router buffer.
The second way is to send packets at reduced rate from start. this could prevent from filling the buffer while reducing the network utility