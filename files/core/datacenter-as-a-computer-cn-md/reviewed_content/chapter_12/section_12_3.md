## 12.3 Google 文件系统

　　Google File System, Sanjay Ghemawat, Howard Gobioff, Shun-Tak Leung, Proceedings of the 19th ACM Symposium on Operating Systems Principles, ACM, Bolton Landing, NY (2003), pp. 20-43 [3]

　　Google 文件系统（GFS）是 Google 设计的第一个实际存储系统，也是首个为大规模数据密集型应用定制的横向可扩展文件系统。在 GFS 出现之前，唯一可用的高容量存储系统需要将昂贵的高性能磁盘与 RAID 控制器安装在机架中。相比之下，GFS 将分布在数千台机器上的大量磁盘整合为一个文件系统。文件被分割为独立的数据块，每个数据块存储在多个磁盘上以避免数据丢失并提高读取吞吐量。一个主节点管理元数据。GFS 提供了类 POSIX 的 API，但放宽了一致性语义以简化系统并提升目标应用的性能。GFS 使 Google 能够显著扩大其搜索索引规模超越其他搜索引擎，并为其存储密集型未来应用如 Gmail 和 YouTube 做好准备。

　　我们选择这篇论文的原因：如何设计一个能够管理数万块不可靠磁盘并提供超高吞吐量的文件系统？又如何在 18 个月内实现它？通过在关键环节做出明智的简化选择而不牺牲太多性能。
