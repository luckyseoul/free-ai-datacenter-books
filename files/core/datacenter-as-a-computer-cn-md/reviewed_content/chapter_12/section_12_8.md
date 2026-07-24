## 12.8 Dremel：Web规模数据集的交互式分析

　　Dremel：Web规模数据集的交互式分析，Sergey Melnik, Andrey Gubarev, Jing Jing Long, Geoffrey Romer, Shiva Shivakumar, Matt Tolton, Theo Vassilakis，《第36届国际非常大规模数据库会议论文集》(2010)，第330-339页 [8]

　　Dremel实现了对超大规模只读嵌套数据集的交互式即席查询。其高吞吐量并行查询执行引擎可为单个查询调用数千台服务器。列式存储通过仅读取部分行并跳过未使用记录字段，实现了更优的压缩率并显著降低I/O负载。其查询引擎采用大规模并行树状架构，可在秒级时间内完成对PB级数据的类SQL查询。对于许多分析任务，与MapReduce相比，Dremel将编程工作量和执行时间减少了多个数量级。

　　我们选择这篇论文的原因：Dremel是当前主流数据湖仓产品BigQuery的前身，迅速取代了MapReduce在众多应用场景中的地位。若想理解横向扩展能力，请阅读这篇论文。
