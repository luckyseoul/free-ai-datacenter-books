## 12.2 Web Search for a Planet：The Google Cluster Architecture

　　Web Search for a Planet：The Google Cluster Architecture, Luiz Andre Barroso, Jeffrey Dean, Urs Hölzle, IEEE Micro, 23 (2003), pp. 22-28 [2]　　到2003年，Google的架构已从1998年每秒最多处理两个查询的原型系统有了显著演进，原始原型的概念性设计已在实践中得到验证。由15000台商用PC组成的集群通过分片技术实现水平扩展和冗余。部分高频硬件故障已实现自动处理。由于Borg系统和Linux容器尚未诞生，服务器本身的管理仍较为人工化。最后但同样重要的是，该论文是首批将电力和能源视为关键系统属性的文献之一。

　　我们选择这篇论文的原因：这是对首个真实世界仓库规模计算机（WSC）堆栈的简明但详尽描述，其设计针对网络搜索进行了优化。
