# Quantstamp: 智能合约安全协议

~~本来想要直接翻译白皮书，后来发现工作量也不小，写个大概吧。去掉技术细节的晦涩部分，保留方便理解整个系统的部分~~

**Quantstamp是第一个智能合约安全审计协议。** 我们用可以确保智能合约安全性的技术来拓展以太坊。我们的团队是由一群软件测试专家组成，总共超过500个谷歌学者引用。

## 问题
区块链网络是安全的，但是智能合约并不安全。2016年6月，黑客从DAO项目中盗取了价值5500万美元的币，原因是智能合约中的一个缺陷。2017年7月，有黑客从加密公司盗取了价值超过3000万美元的代币，只因为Parity钱包的智能合约代码中的一个单词错误。这些安全问题损坏了对智能合约的信任，进一步也阻碍了以太坊网络被更广泛地使用。

当前人们对审计智能合作做的很不充分。从事安全咨询的公司需要人工专家去审核智能合约。这种处理方式昂贵且容易出错。并且依赖于一个公司，需要相信公司中没有任何坏角色。一个依赖于多种不同角色共识的分布式系统显著地更为安全。

人工审计的处理方式，无法应对智能合约的爆炸式增长。2017年6月到10月，智能合约的数量，从50万增长到了200万。我们可以预期1年内会增长为1000万。这对审计工作会有指数级的增长。如今我们没有足够的安全专家来审计所有的智能合约，并且这个短缺未来会更为严峻。

智能合约失败的潜在代价也会增长。仅仅2017年10月，约有32亿美元(1100万ETH)在智能合约中锁定这。而锁定在智能合约中的美元会随着以太坊和智能合约使用的增长而指数级增长。智能合约中漏洞的潜在带带也会相应增长。

## Quantstamp协议
Quantstamp协议通过创建可伸缩低成本的系统审计所有以太坊网络的网络的智能合约，来解决智能合约的安全问题。随着时间的推移，我们希望每一个以太坊智能合约都使用Quantstamp协议来执行安全审计，安全是最基本的。  

协议包含两部分：
- 一个自动且可升级的软件验证系统，用于检查Solidity程序。分布式SAT解析器会需要大量的算力，但随着时间推移，会捕获到更为复杂的攻击。
- 一个自动的赏金支付系统，用于奖励查找合约缺陷的人工参与者。这个系统的目的，是桥接起通往全自动化目标的隔阂。

Quantstamp协议依赖于参与者们的分布式网络，来减轻坏角色的作用，提供所需的算力，还有提供管治。每一个参与者都使用Quantstamp协议（QSP）令牌来支付，接收，或者提高验证服务。下面是不同类型的参与者。

- **贡献者** 为Solidity验证程序贡献软件，然后获得QSP令牌。所有贡献的带慕都会开源，这样社区可以对效率有所信任。绝大部分的贡献者将会是安全专家。贡献是通过管治机制来投票的。
- **验证器** 运行Quantstamp验证节点并获得QSP令牌。验证着只是贡献计算资源，不需要是安全专家。
- **缺陷寻找者** 提交智能合约缺陷，获得QSP令牌作为赏金。
- **合约创建者** 支付QSP令牌验证以验证智能合约。由于智能合约的数量在爆炸式增长，我们预计合约穿件这的需求也会相应增长。
- **合约使用者** 可以查看智能合约的安全审计结果。
- **投票者** 官职系统是协议的一个核心特性。验证被设计为模块化的并且可以基于令牌持有者的投票来升级。管治机制减少了升级分叉的可能性，也会随着时间推移，去中心化创建团队的影响。

## 动机
我们团队成员的职业都在帮助开发者生产更可靠的代码，具备软件验证学科上，多年的科学研究和实战经验。


## 智能合约改进
### 我们如何改进智能合约架构
### 我们如何改进开发者流程
### Quantstamp示例

## 技术
本实施安全审计的技术建立于对验证算法和区块链技术的前沿研究。其基础系由Quantstamp开发，并经过反复修改的验证器节点，其中包括应用常规方法的分析工作包。
### 校验协议
本安全审计的验证协议将奖励提供给对智能合约进行检查的计算资源的参与者。这些检查由验证器节点运行。该验证协议确保对智能合约的认证是“验证证明”的一部分。
通过引入一个基于以太坊的中介托管/治理智能合约，该系统可以确保计算费用的交易安全。如果接收到的智能合同未通过验证器的验证，托管人将控制交易直到验证完成。如果验证失败，令牌被自动返回发送者或持有至安全违规被修正。
Quantstamp节点是Ethereum网络的合作伙伴。以太坊处理网络和交易协议，而Quantstamp节点处理验证协议，以确保安全审核并将其添加到数据字段或交易。
#### 设计
本验证协议处理分布式计算和一致性。这个协议专注于网络中的节点如何执行自动化软件验证和奖赏奖励机制。
我们协议的核心主张价值在于其无需相互信任并组织坏角色操纵审计结果。它也可以通过QSP令牌的去中心化治理进行升级。这就是我们如何设计协议以实现这些目标。
协议治理
我们计划将Quantstamp协议作为具有治理系统的可升级协议，并且由QSP令牌持有者控制。该套治理系统控制更新验证智能合约和验证节点。验证智能合约被设计为模块化和可升级。如发展路线图所详述，在实现核心功能后，治理制度本身将被添加到智能合约。
一个时间锁定的多重签名被用于管理升级。在提出的途径中，交易可以由任何成员发起，交易被越多成员赞成，越能更早可以执行。一个成员可以投票反对升级，这意味着他会退出一项其他人通过的签名。已经全部成员通过的升级可以在1小时后执行。每5％成员不投票，所需时间翻倍；如果投票反对则增加四倍。
治理是一个关键的功能，因为验证着和贡献者需要升级协议。治理机制降低升级频率，允许协议兼顾贡献者升级和确保用户间的一致性。随着时间推移和贡献者加入社区，去中心化的治理特征允许社区参与并稀释创始团队的影响力。例如：验证者想通过投票改变工作量贡献方式，为了增加收入的潜力；用户想要通过投票引入高并发的算法，让协议更快执行。
加密经济激励
为了防止坏角色操纵系统，我们构建了一个激励机制，其策略在于让发起攻击代价昂贵，以防止流氓验证节点改变审计结果。验证者通过QSP令牌中的交易费激励，处理一部分计算。所提议的协议要求拜占庭容错2/3。如果没有达到2/3的共识，则不支付令牌。我们保留在测试和验证阶段改进此设计的权利。以下部分将更详细地说明容错设计。
对抗攻击与分布式计算
单一的坏成员不能操纵网络，因为其他演员由经济驱动防止攻击。 为了分配我们的计算，每个成员只收到一个整体验证问题的组成部分。对于分布式计算，我们目前在考虑使用t-masking quorum系统，其中两个quorum在至少2t +1服务器中交互。该quorum系统可以处理至少有t个节点的故障系统。由于没有一个演员能够访问整个验证过程，所以通过计算过程的分布进一步阻止了坏的演员。
囚徒困境
在游戏理论中，囚徒的困境是一个悖论，其中两个人以自己的利益为由选择了一种不会导致理想结果的行为。两者都选择牺牲另一方以使自己受益，但两者最终都比通过合作更糟。
假设发现错误的验证者可以选择不获取赏金，并利用它来获取未来的收益。然而，我们的经济激励措施驱使验证者追求赏金，而不是试图利用错误。验证者若想试图利用错误而不是报告错误，必须假设没有其他验证者会发现同一个错误和报告它，并修复错误。由于难以协调的验证者数量很大，很可能是其他验证者会发现这个错误，然后去获得赏金。因此，该机制设计下，验证者在个人利益驱使下将追求赏金。
### 安全审计引擎
### 架构图
#### Quantstamp校验智能合约
#### Quantstamp网络
#### Quantstamp报告
### 交换方式
#### 计算机辅助推理工具
##### SAT解析器
##### SMT解析器
#### 模型检查
#### 静态程序分析
#### 符号执行及Concolic testing
### 增量发布和订阅模型
### 缺陷查找器
### 安全泄露策略
### 分布并行SAT
#### 可满足性问题(SAT)
#### 并行SAT解析器
#### 并行SAT与共识
### 以太坊/Solidity的常见漏洞
## 财务计划
## 团队调研贡献
### Demo:定位Parity多方签名漏洞
## 常见问题与解答
问题：什么是 Quantstamp?
Quantstamp是一个提升以太坊系统安全性的安全验证协议。Quantstamp安全协议的优点在于其更智能、互信、高度自治，同时也提高了在去中心化网络计算复杂问题的能力。
问题：quantstamp团队想要做什么？
The Quantstamp team 将会改善如下问题：
1、Quantstamp的节点验证（大量修改后的以太坊客户端）
2、包含执行自动检查代码的安全数据库。
3、quantstamp还可以通过验证智能合约来处理社区内奖金支付，投票机制和
自治。安全数据库语言系统在将来将升级为支持多种语言的操作系统。
问题：人工进行安全审计和代码审查是否不可被取代？
人工进行软件编写能做到完全正确、没有错误是非常困难的 （这是每个经验丰富的开发人员最终会得出的结论）。我们团队的一位成员指出，在他以前工作的一家软件公司，程序错误的积压是数以百计的，常常项目经理为了完成一个具有20-30项功能软件不得不和代码错误进行两周疯狂斗争以取得成效甚微的进展。尽管代码仍有大量的错误，但是由于程序并没有停止工作其勉强能够完成客户所需，所以客户对产品还算满意。不幸的是，如果一旦你让程序员通过智能合同来访问货币系统，那么任何bug都可以是一个能使系统停止工作的事情。
为了改进软件，大多数开发人员认为他们只需要进行更多的代码审查和编写更多的单元测试，但这样增加测试开发软件的成本就增加了。尽管依赖单元测试和代码审查对于低风险应用程序来说是可以接受的，但对于编写关键系统的代码这样做是行不通的。和软件开发相反，计算机芯片制造商，飞机和汽车制造商等等实物开发则依靠自动化软件验证产品是否处于最佳状态。由于上述的原因，我们解决这个问题的方法将是利用这些年我们研究的复杂技术来取代人工进行安全审计和代码审查。
问题：我可以真的可以相信一台电脑能够比人类更好的发现代码的漏洞吗？
虽然单元测试和代码审查确实是我们长久以来用来提高软件质量的方法，但事实表明基于常态公式的验证的技术可以更好地发现人类检测不能找到的微小错误和关键错误。这是因为自动推算工具有以超过人类认知限制的方式模拟关键执行路径的能力。
从另一个角度来看这个问题我们可以思考一下到底近年来算法交易中发生了什么改变。多年来，人们一直相信人类在交易中表现得比电脑更好，但现在电脑的交易能力已经超越了人类。通过快速搜索“电脑占领华尔街”，您会发现许多关于这类现象的文章。
也许，这不足为奇，类似的情况也已经发生在了自动化的安全审计领域：也许我们开发的技术在开始时除了成本/速度的审查之外，无法超过有丰富经验的人，但是每更新一个版本，自动化解决方案就能够以透明的方式解决越多的安全问题，最终这种算法将超过人类解决问题的速度。
同时，该程序能向发现程序漏洞的聪明独立验证者（即白帽黑客）发放赏金。
问题：为什么要建立安全审计协议？为什么不组建安全咨询公司？
因为以太坊平台已经通过Plasma / Casper / PoS扩展应用解决了处理数以万计的智能合同审计的问题。而quantstamp将是第一个赋予以太安全审计的杀手级应用。
问题：为什么不使用Why3或类似工具进行正式验证？
因为对一般的智能合同开发人员来说Why3使用难度太大。而如果采用替代编程范例这类，例如函数式编程（OCaml，Haskell，Clojure）这些已经被大量炒作和承诺的应用也不太符合开发人员的习惯。因为我们经过仔细的调研发现实际的开发者还是更偏向于使用Java，C＃，C ++和Python。所以Quantstamp通过将客户端节点嵌入到以太坊网络中，将安全审计过程自动化，就减少开发人员去学习专门技术所带来的困难。

## 详细履历
## 附录A
## 附录B
## 附录C






