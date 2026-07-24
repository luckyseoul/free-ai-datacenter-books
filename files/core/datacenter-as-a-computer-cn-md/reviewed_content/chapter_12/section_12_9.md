## 12.9 Dapper，一种大规模分布式系统追踪基础设施

　　Dapper，一种大规模分布式系统追踪基础设施，Benjamin H. Sigelman, Luiz André Barroso, Mike Burrows, Pat Stephenson, Manoj Plakal, Donald Beaver, Saul Jaspan, Chandan Shanbhag, Google Technical Report dapper-2010-1, Apr. 2010 (2010) [9]

　　Dapper追踪基础设施以低开销、应用级透明性和可扩展性观察集群规模的应用程序。它为开发者提供请求在大型微服务架构中传播过程的可见性。通过为请求分配全局唯一ID并传播上下文，Dapper能够重构跨不同服务的因果路径及时序。该系统采用自适应采样技术管理数据量，同时捕获具有代表性的追踪记录。如果没有Dapper（现已演进为开源项目OpenTelemetry），将难以理解为何服务今日运行缓慢，或为何某些请求明显慢于其他请求。

　　我们选择这篇论文的原因：Dapper是对一个表面看似简单实则极具挑战性问题的优雅解决方案。
