[1]: [Blockchains-a Systematic Multivocal Literature Review](http://arxiv.org/abs/1911.11770)

## 主题

1. 定义区块链技术
2. 详细说明区块链技术的体系结构，及其所做出的权衡取舍
3. 理解现有区块链技术的应用程序，及其存在的挑战

## 结构



1. 论文介绍：
   - 论文主题及大致研究思路
   - 论文结构简要概述
     - 从语义上区分 BCT，DLT 各种的独特架构
     - 使用 4+1 软件架构框架对 BCT 进行分析，来描述 BCT 体系结构的最新设计方案
     - 从应用场景的角度介绍了几个应用程序，说明了如何在不同的场景中利用 BCT，对 BCT 的当前应用进行分类和总结
     - 强调 BCT 的特性，并阐明了各个特性之间的权衡取舍
     - 以数据为依据，概述 BCT 当前存在的挑战
     - 采用缜密、系统的分析方法，分析了区块链技术各个概念之间的联系
     - 深入地介绍其它论文中获取到的重点内容和观点
   - 相关工作及对比评论
   - 论文结构详细介绍（以节为单位，见下文[2-12]）
2. 回顾 BCT 的背景和基础概念

   - 历史背景
     - 比特币的交易验证机制：哈希验证；带来的风险：花两次攻击（Double-spending）
     - 抵御花两次攻击的两个解决方法：所有节点保存全部交易记录，即在 P2P 网络中建立一个分布式的账本；所有节点需要对交易的历史和交易到达的顺序达成共识，才可向公共账本写入新的交易
     - 网络中存在恶意节点带来的问题：拜占庭将军问题，非恶意节点需要能够通过就分布式分类帐的一致性达成共识，来确定交易的有效性，从而将已被篡改的信息与正确的信息区分开。因此需要保证交易进行时，大部分节点达成共识。本质上，这要求系统可以容忍一定的恶意参与者，这也被称为拜占庭容错
     - 进一步介绍比特币的相关概念，包括时间戳、哈希验证、投票共识机制等，介绍女巫攻击，即如果不对公共账本的写入权限或者投票权限加以控制就会出现由于注册大量恶意账户来控制投票结果的情况
     - 因此，比特币采取工作量证明（PoW）共识协议来解决女巫攻击，基于算力大小，而不是账户或 IP 地址的数量。基于比拼算力的游戏来分配记账权和奖励，接着介绍了比特币的其它概念，包括：挖矿游戏，nonce，块头，puzzle，出块奖励，分叉问题及最长链原则等
     - 简略介绍比特币的其它共识协议及相关概念：PoS，DPoS，PoET，ZKP，PBET
     - 介绍了公链、私链以及联盟链的概念
     - 提出以太坊
3. 论文的研究方法介绍：多角度文献综述

   - 待解决问题：
     - 如何系统地定义区块链技术
     - 基于区块链技术的应用有哪些，如何对其分类
     - 区块链技术的特性有哪些，做了哪些权衡取舍
     - 区块链技术面临的挑战
     - 区块链技术的研究缺口
   - 数据准备：MLP 与 SLP 对比的好处，为什么使用 GL
   - 搜索策略：Kitchenham SL 评价三阶段：string、apply the string、filter and extract papers； Garousi et al. GL 评价三阶段：search、selection、assessment

   - 数据分析：解决前面提出的问题
   - 文献评估：K-α
   - 展示文献评估结果，包括：SL 和 GL 数目，GL 和 SL 每年的文献话题趋势，文献的话题网络图、每年的文献出版物话题趋势
4. 基于其它文献给出的 BCT 定义
5. 从多个角度给出 BCT 的体系结构说明：Kruchten 4+1 软件体系架构
   - 逻辑视图：通过描述架构的元素，来展示终端用户最终使用的区块链功能：公钥加密算法、安全哈希算法、交易验证机制、公链-私链-联盟链、创世节点、共识协议、分叉
   - 开发视图：描述如何将构建区块链划分为更小的可编程模块：交易启用、节点通信、地址代理、节点发现、交易处理、数据存储、共识协议等等
   - 进程视图：展示 IT 系统在运行时的行为，指定控制线程来执行逻辑视图中的类的操作，共识协议是区块链技术进程的核心；接着介绍了几种重要的共识协议：PBFT、PoW、PoET、PoS、DPoS、ZKP
   - 物理视图：讨论了区块链中的 P2P 网络在物理上的不同部署方式，可基于节点读写交易的权限、网络访问区块链的许可范围来划分网络的类别
   - 用例视图：介绍了区块链技术的主要应用场景：加密货币、智能合约、通用用途（五类）
6. 基于其他文献，评价使用了 BCT 的应用程序的设计方案：附录
7. BCT 的特性及特性之间进行的权衡取舍：去中心化-非仲裁、可编程=自动、透明-可审核、不可篡改-可验证
8. 当前 BCT 面临的挑战以及应用前景；挑战（时延、吞吐量、数据存储、数据隐私、管理、可用性）
9. 研究结果讨论：GT（地下理论） 研究方法结合 4+1 软件体系架构描述方法介绍区块链技术及其发展趋势及一些值得强调的事项和观点，并给出判断是否需要使用区块链技术的流程图，最后是 Q&A 环节
10. 基于研究结果，给未来研究的建议，即研究缺口
11. 此项研究的局限性及潜在的威胁
12. 总结全文

## 思路

本文在 BCT 的背景、概念、体系结构、特性、挑战占据很大篇幅，其中的重点在于使用 4+1 方法对区块链软件体系架构的描述、对技术面临挑战的介绍以及对重点事项和相关观点的讨论。

## 方法

使用多焦点、系统的研究方式，即 research literature 和 grey literature 相结合，介绍了 BCT 的背景、概念，定义、体系结构、特性及挑战，此部分主要基于 RL，而对于 GL 的使用则主要体现于对 GL 文献内容的数据分析之中，文中采取了称之为 GT 的数据分析方法。

## 要点

1. RL 和 GL 结合的 MLR 研究方法
2. BCT 背景知识，尝试给出 BCT 的精确定义
3. 4+1 的方法描述 BCT 的体系结构，其中的 use-case view 对应用的分类比较重要
4. BCT 特性及特性之间的权衡取舍
5. 基于 GT 方法的数据分析
6. BCT 面临的挑战

## 结论

背景：区块链技术定义、区块链技术现状概览、研究路线

4+1：设计区块链平台的方式、交易如何处理、P2P 网络架构设计

use-case types：加密货币、智能合约、通用应用(5)

8 个特性及其关系

6 个挑战

4 个缺口

## 对比

无

## 名词表：

| English                                          | 中文                      |
| ------------------------------------------------ | :------------------------ |
| blockchain technology(BCT)                       | 区块链技术                |
| applications and Challenges                      | 应用与挑战                |
| peer-to-peer(P2P) network                        | 点对点网络                |
| electronic cash                                  | 电子货币                  |
| online payments                                  | 在线支付                  |
| trusted financial institution                    | 可信金融机构              |
| Satoshi Nakamoto                                 | 中本聪                    |
| Bitcoin/bitcoin                                  | 比特币系统/比特币         |
| digital distributed ledger                       | 分布式数字账本            |
| transaction(tx)                                  | 交易                      |
| participant                                      | 参与者                    |
| trusted intermediary                             | 可信中介                  |
| performing transactions                          | 执行交易                  |
| trade-off                                        | 权衡                      |
| blockchain architecture                          | 区块链体系结构            |
| practitioners                                    | 从业者                    |
| cryptocurrency                                   | 加密货币                  |
| use-case                                         | 用例                      |
| smart contract                                   | 智能合约                  |
| supply-chain                                     | 供应链                    |
| Bitcoin network                                  | 比特币网络                |
| digitally sign/digital signature                 | 数字签名v/n               |
| Double-spending                                  | 双花/重复支付问题         |
| trusted third-party                              | 可行第三方                |
| copy of the ledger                               | 账本副本                  |
| Byzantine Generals Problem                       | 拜占庭将军问题            |
| Non-malicious/malicious nodes                    | 无恶意/恶意节点           |
| trustworthy consensus                            | 可信共识                  |
| Byzantine fault tolerance                        | 拜占庭容错                |
| Sybil attacks                                    | 女巫攻击                  |
| Proof-of-Work (PoW)/Nakamoto consensus p rotocol | 工作量证明/中本聪共识协议 |
| computational power                              | 算力                      |
| mathematical puzzle                              | 数学问题                  |
| nonce                                            | 随机数                    |
| blockheader                                      | 块头                      |
| mining                                           | 挖矿                      |
| miners                                           | 矿工                      |
| forks                                            | 分叉                      |
| The longest chain rule                           | 最长链原则                |
| block interval time                              | 出块间隔时间              |
| Proof-of-Stake (PoS)                             | 权益/持有量证明           |
| Delegated-Proof-of-Stake (DPoS)                  | 委托权益证明              |
| Proof-of-Elap sed-Time (PoET)                    | 过去时间证明              |
| Zero Knowledge Proofs (ZKP)                      | 零知识证明                |
| Practical Byzantine Fault Tolerance(PBFT)        | 实用拜占庭容错            |
| public blockchain network                        | 公链网络                  |
| permissionless                                   | 无需许可制                |
| private blockchain networks                      | 私链网络                  |
| permissioned                                     | 许可制                    |
| Consortium blockchain networks                   | 联盟链网络                |
| public key cryptography                          | 公钥加密算法              |
| hashing functions                                | 哈希函数                  |
| genesis block                                    | 创世块                    |
| decentralized applications (DApps)               | 分布式应用                |
| address propagation                              | 地址传播                  |
| peer discovery                                   | 对等实体发现              |
| propagating transactions                         | 交易传播                  |
| Ethereum                                         | 以太坊平台                |
| authenticated nodes                              | 已认证的节点              |
| trusted hardware                                 | 可信硬件                  |
| forgers                                          | 铸币工人                  |
| witnesses                                        | 见证人                    |
| round-robin                                      | 循环                      |
| latency                                          | 延时                      |
| anonymity                                        | 匿名性                    |
| confidentiality                                  | 机密性                    |
| efficiency                                       | 效率                      |
| throughput                                       | 吞吐量                    |
| GHOST(Greedy Heaviest Observed Subtree) protocol |                           |
| blocksize                                        | 区块大小                  |
| data storage                                     | 数据存储                  |
| data privacy                                     | 数据隐私                  |
| DAO(Decentralized Autonomous Organization)       | 去中心化自治组织          |
| dsability                                        | 可用性                    |
| decentralization                                 | 去中心化                  |
| disintermediation                                | 去中介化                  |
| programmability                                  | 可编程                    |
| automation                                       | 自动化                    |
| transparency                                     | 透明性                    |
| auditability                                     | 可审计                    |
| immutability                                     | 不可篡改                  |
| verifiability                                    | 可验证                    |
| merkle tree                                      | merkle 树                 |
| scalability                                      | 可扩展                    |
| accessibility                                    | 可访问                    |
| consensus in the wild                            |                           |
| executability                                    | 可执行                    |
| Internet-of-Things (IoT)                         | 物联网                    |

