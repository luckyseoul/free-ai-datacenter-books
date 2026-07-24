## 10.2 仓库规模的安全性

　　云用户依赖WSC提供商对用户和客户数据的负责任管理能力。因此，大多数提供商投入大量资源构建复杂且分层的安全体系。其覆盖范围之广与规模之大相称，严肃的WSC基础设施需要专业的信息安全专家。

### 10.2.1 数据中心安全：建筑与系统

　　在物理层面，安全措施包括保护数据中心场地以防止设备被物理篡改或盗窃。WSC提供商采用生物识别、单人锁、金属探测、摄像头、计算机视觉、车辆屏障、基于激光的入侵检测系统等技术手段来检测或阻止未经授权的进入。此外，他们还会限制获准进入数据中心楼层的人员[54]

　　。谷歌的数据中心定义了六层独立的访问权限[55]

　　。例如，为确保进入敏感区域的每个人均经过身份验证和授权，圆形单人门设计可防止未经授权者尾随进入（图10.7）。

![图10.7 防止尾随的圆形单人门](../../build/images/chapter_10/chapter_10_fig_7_Circular_single_person_door_to_prevent_tailgating.png)

图10.7 防止尾随的圆形单人门

　　为确保高水平的物理安全，最佳实践要求定期测试运行性能。此类测试可以是桌面演练（观察对模拟事件的响应），也可以是对抗性（"红队"）演练，由经验丰富的第三方通过支付费用尝试以任何必要手段（当然不包括暴力）进入数据中心。

　　此外，提供商需要保护设施的控制系统，以防止电子攻击导致设备停用或损坏。数据中心园区包含数千个嵌入式控制器，每个控制器对设备的正常运行至关重要：变压器、电气开关设备和断路器、备用发电机、冷却塔、泵、风扇等。此外，楼宇管理系统（BMS）允许操作员监控和控制整个建筑的运行。

　　BMS及其连接的控制器通常位于与互联网"空气隔离"的独立网络中，从而降低外部攻击者入侵的可能性。但仅靠空气隔离并不能保证安全：著名的伊朗纳坦兹设施曾被通过U盘带入的震网病毒攻击，该病毒感染了BMS并篡改离心机的控制参数，最终导致设备损毁[56]

　　。

　　不幸的是，当前工业控制系统（包括WSC中使用的系统）在安全实践方面明显落后于行业标准。许多问题可通过采用当前最佳实践轻松预防：持续可靠地应用安全补丁；负责任地管理身份验证和授权；实施适当的网络分段。尽管近期事件和客户需求已提升行业对安全的关注度，但截至目前，此类系统的整体安全态势仍显薄弱。

### 10.2.2 服务器安全

　　WSC中的大多数服务器是为此目的定制的，并高度重视安全性。例如，谷歌设计集群中的服务器主板和大部分网络设备。这包括审查组件供应商并精心选择组件，以及与供应商合作审计和验证组件提供的安全属性。谷歌还设计定制芯片，包括硬件安全芯片（称为Titan，详见下一节），部署在服务器、设备和外设上。这些芯片使我们能够在硬件层面识别和验证合法的谷歌设备，并作为启动安全和凭证配置的硬件信任根。Titan硬件芯片的变体也用于Pixel设备和Titan安全密钥。

　　数据中心中的每台服务器都有唯一身份标识。该标识可绑定到硬件信任根和启动软件。此标识用于验证与机器底层管理服务的API调用。该标识还用于服务器间相互认证和传输加密。例如，谷歌的应用层传输安全（ALTS）[57]

　　系统保障远程过程调用（RPC）通信，类似于开源mTLS[58]

　　但具有更好的可扩展性。机器标识可集中撤销以应对安全事件。此外，其证书和密钥会定期轮换，旧证书会被撤销。

　　自动化系统提供以下保证：

- 确保服务器运行最新版本的软件栈（包括安全补丁）
- 检测和诊断硬件及软件问题
- 通过验证启动和隐式证明确保机器和外设的完整性
- 确保只有运行预期软件和固件的机器才能访问允许其在生产网络中通信的凭证
- 在机器不再需要时将其移除或重新分配

　　部署在此基础设施上的服务使用加密进行服务间通信；建立服务身份、完整性和隔离机制；在身份原语基础上实现访问控制机制；最终严格控制和审计对终端用户或客户数据的访问。

　　诸如验证终端用户身份等个别挑战，本身就会引发丰富多样的安全与隐私问题。在面对大规模密码重复使用和不良密码实践的情况下，验证用户身份并防止登录或账户恢复滥用，通常需要专门的专家团队。

　　静态数据必须始终加密，通常需要服务导向和设备导向系统配合使用，各自拥有独立密钥和管理域。存储服务面临一种认知失调：既要满足数据持久性需求，又要能够确凿地断言数据已被删除或销毁。存储服务带宽密集，需要额外计算资源以确保网络流量得到适当加密。

　　内部网络安全必须与适合的基础设施协同管理，以保护互联网规模通信。驱动工作负载迁移基础设施的可靠性约束，同样要求网络安全部署协议能够适应工作负载与其底层机器解耦的模型。一个例子是Google应用层传输安全（ALTS）[57]

　　。SSL/TLS的日益普及，以及应对持续存在的DDoS攻击的需要，要求对密码计算和流量管理进行专门规划和工程设计。

　　要充分发挥最佳实践基础设施安全的全部效益，还需要显著且持续的操作安全投入。入侵检测、内部人员风险、员工设备与凭证保护，以及强制执行安全软件开发的最佳实践，都需要非同寻常的投入。

　　随着信息安全开始真正成为仓库规模计算机（WSC）基础设施中的一等公民，一些历史行业规范正在被重新评估。例如，WSC可能难以将关键基础设施部分委托给不透明或黑盒第三方组件。将机器恢复到已知状态（包括固件层级）以重新分配工作负载的能力，正变得不可或缺。

### 10.2.3 信任根

　　要信任一个系统，必须信任该系统上运行的软件是正确的软件。验证软件版本需要对下层软件层建立传递信任。例如，如果操作系统已被篡改，它可以谎报应用程序完整性，破坏应用程序自我校验的任何尝试。同样，恶意底层固件可以篡改内存或附加设备，从而破坏操作系统本身。

　　为了提供明确可信的起点，现代服务器使用硅基信任根（RoT）。硅基RoT通过验证关键系统组件使用授权且可验证代码安全启动，有助于确保硬件基础设施及其运行的软件保持预期的可信状态。硅基RoT可通过以下方式提供多项安全优势：

- 确保服务器或设备以正确的固件启动，且未感染底层恶意软件。
- 提供加密唯一的机器身份，使操作员能够验证服务器或设备的真实性。
- 以防篡改方式保护密钥等机密信息，即使对具有物理访问权限的人员（例如服务器运输期间）也是如此。
- 提供权威的、防篡改审计记录及其他运行时安全服务。

　　硅基RoT可用于服务器主板、网卡、客户端设备（如笔记本电脑、手机）、消费级路由器、物联网设备等。例如，Google依赖定制的RoT芯片Titan[59]

　　，以确保其数据中心的机器及其外设（如加速器）从已知可信状态启动并使用验证代码。

　　当使用RoT的设备通电时，RoT是第一个启动的处理器，早于CPU或其他任何设备。这使得RoT能够验证启动过程中所有软件的签名。此验证发生在RoT启动主处理器并将其指向首个启动镜像的第一条指令之前。随后的启动链元素在执行前会验证更高层级的组件。例如，操作系统镜像可能未存储在本地机器上，因此引导加载程序会从存储或网络加载它，并在启动前验证其加密签名。

　　RoT在固件镜像更新过程中同样发挥关键作用。在基于RoT的系统中，任何设备（甚至运行操作系统的CPU）都无法更新固件镜像。因此，即使操作系统被攻破，攻击者试图通过修改固件留下后门以维持重启后的访问权限，也会被阻止或检测到。这种写保护通常由硬件确保：固件EPROM的写引脚连接到RoT，且仅连接到RoT。

　　RoT不信任本地CPU，因此没有可供本地进程更新固件的API。相反，RoT通过安全通道与服务器外的控制系统通信，该系统负责分发更新。因此，攻击者必须攻破这个小型中央控制系统才能破坏服务器固件，而无法通过攻破舰队中的一个或多个常规服务器来实现。

　　认识到在硅芯片中建立信任的重要性，信任根（RoT）在设计和制造过程中受到广泛关注。例如，Google的Titan芯片包含针对物理篡改（无论是制造过程中还是运行期间）、供应链攻击（在发货箱中插入“假冒”Titan芯片）以及软件篡改的防御机制。例如，Titan芯片的初始软件镜像通过一次性机制在安全设施中进行物理安装，并通过密码学方式进行认证。完成初始镜像后，芯片上的熔丝会被物理破坏，从而无法进行后续的物理安装，即所有未来更新都需要Google独有的私钥。

　　为了进一步增强对Google云基础设施完整性的信任，OpenTitan RoT开源了一个由Google及其合作伙伴开发的高质量完整硅芯片信任根实现[60]

　　。其目标是将可靠硅芯片信任根的优势推广至整个行业。Google还参与了Caliptra开源信任根项目[61]

　　。与OpenTitan这种独立芯片不同，Caliptra由IP和固件组成，用于集成在更大芯片中的信任根模块。Caliptra针对数据中心级SoC（如CPU、GPU、DPU和TPU）。它包含在SoC中实现测量信任根（RTM）模块所需的技术规范、硅逻辑、ROM和固件。Caliptra集成使SoC具备身份认证、可测量启动和验证功能。离散外部信任根与可更新存储结合应用处理器内部的信任根逻辑，使设计者能够在整机层面提升物理防篡改能力，显著增加攻击者的成本。

### 10.2.4 加密

　　加密技术早已用于保护重要数据，但其广泛应用是相对较新的现象。例如，2010年Gmail成为首个默认使用SSL的电子邮件服务，2014年成为首个强制使用SSL的服务。部分归功于硬件对加密的改进支持，这一广泛应用得以实现。事实上，SSL/TLS连接的建立和维护的计算开销曾是最大的采用障碍。

　　静态数据加密保护存储在任意存储系统中的数据。通常，数据会在存储堆栈的不同层级使用不同密钥进行多次加密。例如，硬盘驱动器可能使用内置密钥和加密引擎在数据写入前进行加密。因此，即使硬盘被盗，除非密钥也被盗取，否则其上的数据无法被读取。然而，由于嵌入式软件不可审计且可能包含漏洞，存储软件层也会对所有数据进行加密，可能为每个存储卷或每个存储用户使用不同的密钥[62]

　　。Google在数据写入数据库存储系统或硬件硬盘前即进行加密。加密是所有存储系统固有的特性，而非事后添加。

　　Google所有存储系统均采用相似的加密架构，尽管具体实现细节因系统而异。数据被分割为子文件块进行存储，每个块大小可达数GB。每个块在存储层级使用独立的数据加密密钥（DEK）进行加密。即使两个块属于同一客户或存储在同一设备上，它们也不会共享相同的DEK。

　　若数据块被更新，会使用新密钥进行加密，而非复用现有密钥。这种基于不同密钥的数据分区方式将潜在数据加密密钥泄露的风险限制在单个数据块范围内。

　　每个数据块具有唯一标识符。访问控制列表（ACL）确保只有具有授权角色的Google服务才能解密特定块，且这些授权仅在特定时间点有效。这种访问限制有助于防止未经授权的数据访问，增强数据安全性和隐私性。

　　每个数据块在存储系统中分布存储，并以加密形式复制用于备份和灾难恢复。攻击者若想访问客户数据，必须掌握并能够访问两样东西：所有对应目标数据的存储块，以及所有对应块的加密密钥。

　　下图展示了客户数据上传后如何被分割为加密块进行存储（图10.8）。

![图10.8 Google存储中的静态数据加密](../../build/images/chapter_10/chapter_10_fig_8_Data_encryption_at_rest_in_Google_storage.png)

图10.8 Google存储中的静态数据加密

　　Google使用AES算法对静态数据进行加密。存储层级的所有数据默认使用AES-256加密的DEK进行加密。AES被广泛采用，因为美国国家标准与技术研究院（NIST）推荐AES-256和AES-128用于长期存储，且AES常被纳入客户合规性要求。

　　传输中加密保护网络传输中的数据[63]

　　。例如，加密可防止通信在客户站点与云服务商之间或两个服务之间传输时被截获。这种保护通过传输前加密数据、认证端点、接收后解密并验证数据完整性来实现。例如，传输层安全（TLS）常用于传输安全的数据加密，而安全/多用途互联网邮件扩展（S/MIME）则用于电子邮件加密。

　　与静态加密类似，数据可能在多个层级被多次加密。例如，路由器可能使用链路专用密钥[64]

　　加密所有出站数据包，而使用该链路的网络连接可能采用TLS加密整个连接，该连接用于发送加密电子邮件。尽管理论上多层级加密并非理想方案，但它们实现了适当的分层架构、纵深防御，并且（通过普遍存在的硬件加速）成本相对低廉。

　　加密技术，以及广义上的安全领域，是一个值得专门撰写整本书的迷人主题。例如，即使仅讨论传输过程中的加密，也涉及比此处描述更多的系统。有兴趣的读者可参考Google Cloud加密的高层次概述作为示例[63]

　　。关于构建安全可靠系统的深入建议，我们推荐同名著作[3]

　　。

### 10.2.5 机密计算

　　机密虚拟机可通过加密处理中的数据来保护云中数据的机密性。在机密计算中，所有数据在离开芯片封装时都会被加密，包括DRAM中的数据，因此即使攻击者拥有对运行服务器的完全物理访问权限，也无法破坏机密性。必须直接攻击CPU内部才能实现。机密虚拟机利用来自AMD、Intel、ARM等新一代CPU的安全特性。通过机密计算，客户可以确信其数据在云中处理时仍能保持私密和加密状态。

　　机密虚拟机实例提供两项关键优势。首先，隔离性：加密密钥由专用芯片内硬件生成并存储其中，即使是虚拟机监控程序也无法访问。因此，机器上最特权的服务（虚拟机监控程序）也无法访问明文数据。其次，认证性：客户可以验证虚拟机的身份和状态，确保关键组件未被篡改（防止"中间人"攻击）。这种硬件隔离和认证机制被称为可信执行环境（TEE）[65]

　　。智能手机也包含TEE，例如用于生物特征认证。

　　各厂商实现机密计算功能的方式不同。2016年，AMD安全加密虚拟化（SEV [66]

　　）是首个实现方案，通过AMD安全处理器提供基于硬件的内存加密，并通过外部TPM实现启动时认证。CPU内部的高性能加密模块负责解密或加密芯片缓存与主内存之间的数据交换。SEV机密虚拟机与标准虚拟机之间的性能差异通常很小。

　　尽管SEV具有高性能优势，但它无法防范某些复杂攻击，例如恶意虚拟机监控程序通过加密数据重放和内存重映射破坏机密环境。AMD安全加密虚拟化-安全嵌套分页（SEV-SNP [67]

　　）在SEV基础上扩展，增加了基于硬件的完整性保护。SEV-SNP完整性保护的基本原则是：如果虚拟机能够读取某个私有（加密）内存页，它必须始终读取该页最后一次写入的值。这种额外保护带来的代价是更高的开销，尤其是对I/O密集型应用。

　　Intel信任域扩展（TDX [68]

　　）是另一种基于硬件的TEE。TDX在虚拟机内创建隔离的信任域，并使用硬件扩展管理加密内存。TDX可防范多种利用对DRAM物理访问的攻击，包括捕获、修改、重定位、拼接和内存别名攻击。然而，它无法防范重放攻击。ARM的CCA [69]

　　通过称为Realms的硬件隔离安全环境保护数据和代码，使工作负载免受操作系统或虚拟机监控程序等特权软件的攻击。与SEV-SNP类似，CCA设计用于防范内存重放攻击。

　　除了这些CPU特性，云服务商还提供外部密钥管理（EKM），允许客户将加密密钥存储在云服务商空间之外的硬件安全设备中[70]

　　。通过相互认证身份，配备TEE的CPU可以直接从这些EKM获取密钥，而无需云服务商篡改或访问密钥。

### 10.2.6 CPU漏洞

　　除了验证固件和软件完整性的硅基信任根，服务器安全还依赖硬件本身的可靠性，特别是CPU指令的无缺陷运行。内存保护的正确实现尤为重要：所有操作系统都依赖虚拟内存隔离不同进程的地址空间，使得一个进程在未显式授权的情况下无法读取另一个进程的内存内容。缺乏内存保护将使在单个CPU上高效运行相互不信任的工作负载变得困难甚至不可能。

　　然而，由数十亿个电路组成的复杂芯片（如CPU）即便厂商尽最大努力，仍不可避免存在漏洞。此类漏洞通常在新芯片推出初期就被发现，并记录在"勘误表"文档中。大多数现代芯片包含以微码形式存在的片上软件，通常可以通过更新微码修复此类漏洞（这些更新本身由硅基信任根保护）。

Until 2017, such bugs were fairly rare and weren’t considered a top security concern. But in a watershed moment in June of 2017, researchers at Google’s Project Zero and in academia almost simultaneously found two bugs that were later described as "possibly the worst CPU flaws ever found", not just because of the severity of the two bugs themselves but because it was immediately apparent that they represented the first examples of a new class of CPU bugs and that there would be many more, and that they affected virtually every modern CPU [71]

　　.

The first few such bugs (Spectre [72]

　　, Meltdown [73]

　　, and Foreshadow [74]

　　) demonstrated the dangers of side channel attacks created by shared CPU resources. A side channel attack is an attack that doesn't directly attack the target functionality (e.g., memory protection) but instead uses a "side channel" that is correlated with the target to learn secret information about the target. For example, suppose a password validation function compares two strings, the password that's entered and the password that's stored. If that string comparison terminates early when it discovers a mismatch, and if we can measure the execution time of the password check with high enough precision, then we can guess the correct password via this timing side channel. To do so, we pick a random password starting with 'a' and then 'b' etc until we discover an execution that took longer than the others. That execution was one where the first iteration of the string comparison succeeded and the second one didn't, and thus we now know the password's first character.

In reality, things aren't that simple. However, all CPUs provide highly accurate timers (they're needed for performance tuning and other functions), and they also have many instances where physical CPU tables serve multiple processes. That combination creates side channels that can be exploited, especially in CPUs that additionally use speculative execution. These exploits are fairly complex so we won't describe them here, but the two original bugs have been documented extensively and give a good indication of both the complexity of discovering them, but also the complexity of mitigating them.

At the same time, the Spectre and Meltdown attacks illustrated the potential security advantages of WSCs and thus public clouds. In particular, Google knew of the security bug a full six months before it became public, and was able to make critical contributions to mitigations. More generally, WSC providers can be expected to maintain highly skilled teams to find and assess risks and develop or deploy mitigations. WSC providers employ coordinated management systems that can deploy CPU microcode, system software updates, or other patches in a rapid but controlled manner. Some (like Google Cloud) even support live migration of customer VMs to allow the underlying machines to be upgraded without disrupting customer workload execution. As a result, when Spectre and Meltdown became public, Google Cloud customers were already protected against them because the infrastructure had been patched without requiring customers to take action.

### 10.2.7 安全服务部署

　　如前所述，集群编排服务控制直接运行在WSC基础设施上的服务。本节描述Google部署服务时的附加安全措施；其他WSC提供商可能有类似措施。

　　基础设施不假设运行在其上的服务之间存在任何信任关系。这种信任模型称为零信任安全模型。零信任安全模型意味着默认情况下不信任任何设备或用户，无论它们位于网络内部还是外部。

　　由于基础设施设计为多租户架构，不同客户（消费者、企业及Google自身数据）的数据分布在共享基础设施上。该基础设施由数万台机器组成。除非在特定情况下（如客户使用Compute Engine的专用节点[75]

　　），基础设施不会将客户数据隔离到单台机器或一组机器上。

#### 10.2.7.1 服务身份、完整性与隔离

　　为实现服务间通信，应用程序使用加密认证和授权。认证和授权在抽象层和粒度上提供强访问控制，管理员和服务均可理解。

　　服务不依赖内部网络分段或防火墙作为主要安全机制。在网络各点的入站和出站过滤有助于防止IP欺骗。客户可配置额外安全机制，如VPC服务控制[76]

　　和Cloud Interconnect[77]

　　。

　　运行在基础设施上的每个服务都有关联的服务账户身份。服务会获得加密凭证，用于在发送或接收RPC时向其他服务证明其身份。这些身份用于安全策略中，确保客户端与目标服务器通信，并限制服务器允许特定客户端访问的方法和数据。

　　多种隔离和沙箱技术有助于保护服务免受同一台机器上其他服务的影响。这些技术包括Linux用户隔离、基于语言的沙箱（如Sandboxed API[78]

　　）、基于内核的沙箱、容器应用内核（如gVisor[79]

　　）以及硬件虚拟化。通常，我们对风险较高的工作负载采用更多层的隔离。风险较高的工作负载包括需要额外处理的用户提供的项目。例如，风险较高的工作负载包括在用户提供的数据上运行复杂文件转换器，或在App Engine或Compute Engine等产品中运行用户提供的代码。

　　为了增强安全性，敏感服务（如集群编排服务和某些关键管理服务）仅在专用机器上运行。为了实现更强的密码学隔离以保护正在使用中的数据，Google Cloud 支持针对虚拟机、Google Kubernetes Engine（GKE）节点等的机密计算服务 [80]

　　。

#### 10.2.7.2 服务间访问管理

　　服务可以使用基础设施提供的访问管理功能，明确指定哪些其他服务可以与其通信。例如，服务可以限制传入的 RPC 仅来自允许的服务列表。该服务可配置允许的服务身份列表，基础设施会自动强制执行此访问限制。强制执行包括审计日志、理由说明以及单方面访问限制（例如工程师请求）。

　　操作服务的工程师也会被分配独立身份。服务可根据其身份配置允许或拒绝访问。所有这些身份（机器、服务和员工）都位于基础设施维护的全局命名空间中。

　　为了管理这些身份，基础设施提供包含审批链、日志和通知的工作流系统。例如，安全策略可以强制执行多方授权。该系统采用双人规则，确保工程师单独操作时无法在未获得其他授权工程师批准的情况下执行敏感操作。该系统使安全访问管理流程能够扩展到基础设施上运行的数千个服务。

　　基础设施还为用户、组和成员管理提供标准服务，以便服务在必要时实现自定义的细粒度访问控制。

#### 10.2.7.3 服务间通信加密

　　基础设施为网络上的 RPC 数据提供机密性和完整性保护。所有 Google Cloud 虚拟网络流量均加密。所有基础设施服务间的通信均经过身份验证，且大多数服务间通信已加密，这增加了额外的安全层，即使网络被窃听或网络设备被攻破，也能帮助保护通信。服务间通信加密要求的例外仅适用于具有低延迟需求且不会离开数据中心多层物理安全架构中单一网络结构的流量。

　　基础设施自动高效地（借助硬件卸载）为数据中心间网络传输的基础设施 RPC 流量提供端到端加密。

### 10.2.8 扩展阅读

　　构建可靠且安全的系统极具挑战性，因为需要关注 WSC 的每个层级，从物理园区到云用户编写的应用程序代码。进一步阅读推荐 Google SRE 和安全专家撰写的《站点可靠性工程》[81] 和《构建安全可靠的系统》[3]

　　。

　　如果要从本章提炼一个共同主题，那就是规模可以同时促进可靠性和安全性。规模不会让它们变得更容易，但会迫使 WSC 提供商寻找原则性、可扩展的解决方案。
