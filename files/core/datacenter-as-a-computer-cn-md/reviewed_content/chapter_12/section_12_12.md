## 12.12 B4：Experience with a Globally Deployed Software Defined WAN

　　B4：Experience with a Globally Deployed Software Defined WAN，Sushant Jain, Alok Kumar, Subhasree Mandal, Joon Ong 等，Proceedings of the ACM SIGCOMM Conference, Hong Kong, China (2013), pp. 3–14 [12]

　　《B4》论文详细描述了Google在设计、部署和运营私有软件定义广域网（SDN WAN）以连接其全球数据中心方面的实践经验。该系统将控制平面与数据平面分离，通过集中式流量工程控制器管理物理网络中的带宽分配和路由。B4采用定制交换机硬件和OpenFlow协议，证明了SDN在管理大规模复杂广域网方面的有效性，相比传统广域网架构具有更高的效率、灵活性和成本效益。

　　我们选择这篇论文的原因：在许多方面，B4对于大型网络而言正如Borg对于大型服务器池：这是在不崩溃的情况下管理数万个设备的唯一途径。
