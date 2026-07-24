## 12.19 Andromeda：Performance, Isolation, and Velocity at Scale in Cloud Network Virtualization

　　Andromeda：Performance, Isolation, and Velocity at Scale in Cloud Network Virtualization，Mike Dalton, David Schultz, Ahsan Arefin, Alex Docauer 等，15th USENIX Symposium on Networked Systems Design and Implementation, NSDI 2018, 第373–387页。[20]

　　Andromeda 描述了 Google Cloud Platform 的网络虚拟化架构。其 SDN（软件定义网络）设计为虚拟机提供高性能、安全的网络服务。Andromeda 将控制平面与分布式数据平面解耦，数据平面部分在主机上实现，部分卸载到硬件。该架构实现了网络服务（VPC、防火墙、负载均衡器）的快速部署，提供接近裸金属网络的性能，并确保租户间的强安全隔离。设计优先考虑产品迭代速度和运维灵活性，简化新网络功能的开发并高效扩展基础设施。

　　我们选择这篇论文的原因：网络虚拟化希望在硬件中实现，因为它涉及高速集群网络中的每个数据包。通过在硬件和软件之间精心分配功能，Andromeda 结合了两者的优点。说起来容易做起来难。
