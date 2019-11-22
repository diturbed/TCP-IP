## TCP头部报文
* source port/destination port
* sequence number
字节流中每个字节的编号，用于TCP通信过程中确定数据通信的有序性
* acknowledgement number
确认序列号，N表示之前N-1为止的所有数据都已经确认收到
* TCP FLAG
   * ACK            
ACK=0表示接收端未应答，ACK=1表示接收端已经接收到数据
   * SYN
同步序列号，常用于确认端口存在，TCP握手发送的第一个数据包，SYN=1表示接收端已经准备好了
   * FIN
数据末尾，常用于端口扫描，通知接收端已经到数据末尾，可以关闭连接了

## 三次握手过程
* 初始状态
客户端处于closed状态，服务器端处于listen状态
* 第一次握手
客户端发送SYN=1和sequence num=x，发送后客户端处于SYN_Send状态
* 第二次握手
服务端接到SYN请求后，如果同意连接，会以自己的同步序列号SYN(服务端)=1和sequence num=y和ACK=1和确认序列号acknowledgement number=x+1报文作为应答，服务器设置为SYN_Recieve状态
* 第三次握手
客户端接收到ACK=1和SYN=1后，知道可以发送下一次数据了