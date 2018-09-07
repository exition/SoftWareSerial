# SoftWareSerial

STM32 IO口模拟串口。
## 实现思路
IO口模拟串口的思路也比较简单，一切按照串口协议进行操作即可。

对于发送，计算好不同波特率对应的延时时间进行数据发送。

对于接收，稍微复杂。通过外部中断检测接收管脚的下降沿，检测到起始信号后开启定时器，定时器按照波特率设定好时间，每隔一段时间进入定时器中断接收数据，完成一个字节后关闭定时器。

## 测试Demo说明 

* TXD : PC13    

* RXD : PB14    

* 波特率：9600 ，1-8-N    

## Demo功能
接收11个数据，然后把接收到的数据发送出去。