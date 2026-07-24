## 2.3 服务器

　　数据中心消耗的大部分能源通常用于服务器——这是仓库规模计算机（WSC）的硬件基础构件。这些通用服务器安装在机架中，并通过本地“机架顶部”以太网交换机互连。这些机架级交换机使用100-200Gbps链路（截至2025年），进而通过多个上行链路连接到一个或多个集群级（或数据中心级）以太网交换机。

　　由于既不满足于公制系统也不满足于英制系统，机架设计者采用“机架单位”来衡量服务器高度。1U等于1.75英寸（44.45毫米），典型机架高度为42U。这些标准始于1922年，最初是AT&T（当时称美国电话电报公司）的内部设备标准，至今仍在沿用。

　　有时一个托盘或机箱内包含多个共享部分组件的服务器。例如，多个低功耗服务器可能共享一个昂贵的高速网卡。因此，它们通常在机箱内包含一个额外的网络聚合层级，多个处理节点通过PCIe等I/O总线连接到少量网络节点。

![Fig. 2.6 Building blocks for WSCs: server, TPU accelerator, disk tray](../../build/images/chapter_2/chapter_2_fig_6_Building_blocks_for_WSCs_server_TPU_accelerator_disk_tray.png)

图2.6 WSC的构建模块：服务器、TPU加速器、磁盘托盘

　　图2.6展示了Google服务器的构建模块，左侧为常规服务器托盘。WSC还包括额外的计算硬件构建模块，如GPU和定制加速器；中间图片显示的是TPU板卡。与服务器类似，这些组件通过定制或行业标准互连在机架（或多机架模块）层级连接，最终汇聚到数据中心网络。右侧是装有数十个磁盘的存储托盘。图2.7展示了这些构建模块如何组装成服务器机架行，既适用于通用服务器也适用于加速器。

![Fig. 2.7 Top: traditional compute servers; bottom: a TPU accelerator pod](../../build/images/chapter_2/chapter_2_fig_7_Top_traditional_compute_servers_bottom_a_TPU_accelerator_pod.png)

图2.7 顶部：传统计算服务器；底部：TPU加速器模块
