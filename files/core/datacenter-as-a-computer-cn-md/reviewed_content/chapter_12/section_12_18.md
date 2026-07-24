## 12.18 微秒杀手的攻击

　　Attack of the killer microseconds, Luiz André Barroso, Mike Marty, David Patterson, Parthasarathy Ranganathan, Communications of the ACM, 60(4) (2017), pp. 48-54 [19]

　　仓库规模计算机（WSC）需要针对微秒级延迟进行优化，这受到更快的数据中心网络、新型存储层次结构和加速器的驱动。通过两个案例研究（如何浪费高速数据中心网络，以及如何浪费高速数据中心处理器），论文指出针对纳秒和毫秒级事件的系统优化方案在微秒级事件中表现不足。新技术可以在微秒延迟下实现高性能，但需要跨硬件、内核和应用层的协同设计。

　　我们选择这篇论文的原因：与之前讨论的能量比例性论文类似，这篇论文指出了WSC面临的一个简单却重要的挑战，并推动了WSC系统栈的大量后续优化工作。
