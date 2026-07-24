## 12.5 Bigtable：一种结构化数据的分布式存储系统

　　Bigtable：一种结构化数据的分布式存储系统，Fay Chang, Jeffrey Dean, Sanjay Ghemawat, Wilson C. Hsieh, Deborah A. Wallach, Mike Burrows, Tushar Chandra, Andrew Fikes, Robert E. Gruber, 第7届USENIX操作系统设计与实现研讨会（OSDI），{USENIX}（2006），第205-218页 [5]

　　。作为GFS和MapReduce的补充，Bigtable是超大规模数据库的初始解决方案，也是NoSQL运动的开端——该运动通过牺牲强事务一致性来换取水平扩展能力。Bigtable将其数据分布存储在数千台商用服务器上，提供稀疏、分布式、持久化的多维排序映射数据模型。数据通过行键、列键和时间戳进行索引。Bigtable使用GFS作为底层存储，提供高可扩展性、可用性和性能。其在提供低延迟读写操作和对海量数据集的高效扫描方面的优势，对后续NoSQL设计产生了深远影响。

　　我们选择这篇论文的原因：它开启了至今仍在蓬勃发展的NoSQL运动（例如MongoDB、Redis、Firestore、DynamoDB）。然而在过去十年中，Google在许多应用场景中已用Spanner取代BigTable，因为后者提供了具有可比性能的完全事务性存储。
