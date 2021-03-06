# MQTTMessage

## 1. MQTT是什么？
MQTT全称消息队列遥测传输 (Message Queuing Telemetry Transport)。其主要提供了订阅/发布两种消息模式，更为简约、轻量，易于使用，特别适合于受限环境（带宽低、网络延迟高、网络通信不稳定）的消息分发，属于物联网（Internet of Thing）的一个标准传输协议。

## 2. MQTT的服务质量
MQTT支持三种消息发布服务质量(QoS)：

至多一次(QoS==0)
消息发布完全依赖底层 TCP/IP 网络。会发生消息丢失或重复。这一级别可用于如下情况，环境传感器数据，丢失一次读记录无所谓，因为不久后还会有第二次发送。
至少一次(QoS==1)
确保消息到达，但消息重复可能会发生。
只有一次(QoS==2)
确保消息到达一次。这一级别可用于如下情况，在计费系统中，消息重复或丢失会导致不正确的结果。小型传输，开销很小（固定长度的头部是 2 字节），协议交换最小化，以降低网络流量。

## 3. MQTT服务器

emqtt，并发最高，但cpu占用较高，稳定性高，但是消息发送较慢。
moqtuitto，发送消息快，稳定性高，cpu占用很少，并发比较高。其它的稳定性不太高。

我个人使用的是moqtuitto作为MQTT服务器，还可以使用Eclipse paho作为客户端进行测试。

## 4. MQTT实现方式
实现MQTT协议需要客户端和服务器端通讯完成，在通讯过程中，MQTT协议中有三种身份：发布者（Publish）、代理（Broker）（服务器）、订阅者（Subscribe）。其中，消息的发布者和订阅者都是客户端，消息代理是服务器，消息发布者可以同时是订阅者。

MQTT传输的消息分为：主题（Topic）和负载（payload）两部分：

（1）Topic，可以理解为消息的类型，订阅者订阅（Subscribe）后，就会收到该主题的消息内容（payload）；
（2）payload，可以理解为消息的内容，是指订阅者具体要使用的内容。

## 5. 项目结构

### 5.1 mqttreceiver 消息接受者

### 5.2 mqttsender 消息发布者

发布MQTT消息

http://localhost:9090/sendMqttMessage?message=KO-Virus&topic=virus



