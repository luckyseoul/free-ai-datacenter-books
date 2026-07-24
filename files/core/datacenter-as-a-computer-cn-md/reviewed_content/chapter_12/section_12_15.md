## 12.15 Google 使用 Borg 进行大规模集群管理

　　Google 使用 Borg 进行大规模集群管理，Abhishek Verma, Luis Pedrosa, Madhukar R. Korupolu, David Oppenheimer, Eric Tune, John Wilkes, 欧洲计算机系统会议（EuroSys）论文集，ACM，法国波尔多（2015）pp. 18:1–18:17 [15]

　　Borg 是一个大规模集群管理器，负责在数万台机器上调度、部署、监控和管理应用程序。它同时处理长期运行的服务和批处理作业，通过资源回收和细粒度共享等技术，专注于高可靠性、可扩展性和高效资源利用率。Borg 使用逻辑上集中式的主调度器，并通过复制实现容错。分布式代理（Borglets）在每台机器上提供细粒度的资源管理。Borg 根据应用程序优先级和配额分配资源，支持声明式作业规范，并提供滚动更新和健康检查等功能。

　　我们选择这篇论文的原因：Borg 为 Kubernetes 奠定了基础。它向手动管理的服务器传递的信息很简单：你将被整合！
