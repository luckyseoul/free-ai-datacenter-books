## 12.4 MapReduce：大规模集群上的简化数据处理

MapReduce：Simplified Data Processing on Large Clusters, Jeffrey Dean, Sanjay Ghemawat, OSDI’04：Sixth Symposium on Operating System Design and Implementation, San Francisco, CA (2004), pp. 137-150 [4]
　　MapReduce与GFS形成互补：当GFS使跨多设备存储大量数据变得容易时，MapReduce使跨多台通用服务器处理大型数据集变得容易。用户指定"map"函数来处理键值对并生成中间对，以及"reduce"函数来合并与相同键关联的中间值。运行时系统透明地处理并行化、容错、数据分布和负载均衡。这种抽象使不具备分布式系统专业知识的程序员也能有效利用大型集群。论文展示了MapReduce在分布式排序、网络访问日志分析和倒排索引构建等多样化任务中的实用性，显著简化了大规模数据处理。

　　我们选择这篇论文的原因：Lisp发明了map-reduce模式，而MapReduce（后来以Hadoop开源）迅速成为大规模批处理的默认选择。
