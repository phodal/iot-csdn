基于 JavaScript 语言的快速物联网开发架构
---

> 凡是能用JavaScript写出来的，最终都会用JavaScript写出来。            ---Atwood定律

物联网来源于 Internet of Things 一词，即世间万物的互联网。顾名思义，物联网的意思就是物物相连的互联网。而物联网架构与现有的互联网架构相比，也充满了诸多的相似之处。

我们甚至还可以认为，**物联网只是对互联网的扩展**。与传统的 CS 架构相比，它多了一个“数据采集层”，我们称之为传感器层、硬件层等等。数据的产出不再只是用户，还来自于各式各样的联网设备。物联网不再局限于使用 HTTP 协议来传输数据，它还会使用 CoAP（受限制的应用协议）、MQTT（消息队列遥测传输）协议。

基础：物联网的四个层级
---

当前的物联网应用，所要做的就是**控制**和**数据处理**。指令，由用户到终端一层一层往下下达，直到硬件端由设备去执行。而数据，便是一层一层往上上报，直至被可视化。

因此，与互联网的架构相比，起点与终点不一样了：指令的终点与数据的起点，变成了硬件层，而非最后的用户层。

![互联网架构](images/cs.png)

数据由客户端 A 发送到服务端，客户端 B 再从服务端获取 A 的数据，如此便算是完成一个回路。而物联网架构则稍微麻烦了一些，多了一个层级，便多了一个步骤。

![典型的物联网架构](images/struct.png)

硬件层上的微控制器采集通过直连的方式，采集各式各样的数据，温度、湿度等等。而受限于微控制器的成本、环境条件等原因，它可能无法直接连接到互联网。因此，它需要连接到一些额外的联网设备才能实现。

而这一些联网设备，会负责处理来自各个硬件设备的数据，便将这些数据上传到服务器。同时，它会提供一个无线（如蓝牙、红外、ZigBee）接口作为数据的入口。因此，这一个层级需要有更好的数据处理能力，并且它应该要可以**快速开发**。因为这一些设备，主要作的是协调工作，我习惯于将之称为『协调层』。

### 基于纯 JavaScript 的物联网架构

![基于纯 JavaScript 的物联网架构](images/iot-archicture.jpg)

服务层
---

![物联网服务层](images/iot-server.jpg)

### 传统开发模式

![Lan 物联网架构](images/lan-archicture.jpeg)


#### 使用云服务

单一的云服务无法提供这么多复杂的功能

### ServerLess 

> Serverless 是一种基于互联网的技术架构理念，应用逻辑并非全部在服务端实现，而是采用FAAS（Function as a Service）架构，通过功能组合来实现应用程序逻辑。

1. 对设备进行鉴权
2. 转换、存储设备的数据
3. 广播通知其他监听此设备数据的服务
4. 后台查询数据
5. 分析数据（AI）
6. 可视化数据

#### 通用的 ServerLess 架构 

![Serverless 物联网参考架构](images/internet-of-things-iot-hackday-23-638.jpg)

#### AWS IoT Things

![AWS IoT Things 参考架构](images/aws-iot-things.png)

应用层
---

![物联网应用](images/iot-app.jpg)

当有大量的图表显示时，Ionic 不失为一个不错的框架，并且可以和 Angular 2 配合使用

React Native 可以提供更好的性能

但是如果只能蓝牙的交互，可以考虑 PWA 或者微信小程序

未来的浏览器，Web Devices API，如 Bluetooth、NFC、USB

以及微信小程序，访问 GPS、罗盘、加速度计

硬件层
---

![物联网硬件层](images/iot-hardware.jpg)

显然，就当前而言 Arduino 是最合适的原型开发硬件，除此还有 ESP8266

多数使用 JavaScript 的设备都具有网络功能，他们可以直接连接到互联网。

Tessel

Espruino

Ruff，配置

未来，IoT.js 会是一个更好的选择

![IoT.js 架构](./images/iotjs-arch.png)

协调层
---

![物联网协调层](images/iot-coord.jpg)

Raspberry Pi

Johnny-Five 

OpenWRT 路由器作为网关

物联网的趋势
---

 - 微服务化
 - DevOps
 - 容器化
 - ServerLess
