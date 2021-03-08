## RefPaper Readme

### 总览

- [2011Ananda]Rigorous component-based system design using the BIP framework
- [2016Karthikeyan Bhargavan]Formal verification of smart contracts Short paper
- [2016LCO]Making Smart Contracts Smarter-oyente
- [2017Hirai Y]Defining the Ethereum Virtual Machine for Interactive Theorem Provers
- [2017Nicola Atzei]A survey of attacks on Ethereum smart contracts
- [2017Sergey I]A concurrent perspective on smart contracts
- [2018Nehai Z]Model-checking of smart contracts
- [2018S Kalra]ZEUS-Analyzing Safety of Smart Contracts
- [2018Tesnim Abdellatif]Formal verification of smart contracts based on users and blockchain behaviors models
- [2018Tsankov P]Securify Practical security analysis of smart contracts
- [2018Yang Z]Formal process virtual machine for smart contracts verification
- [2018Zhang Y]Smart contract-based access control for the internet of things
- [2019Albert E]SAFEVM-a safety verifier for Ethereum smart contracts
- [2019Kolluri A]Exploiting the laws of order in smart contracts
- [2019Mark Mossberg]Manticore A User-Friendly Symbolic ExecutionFramework for Binaries and Smart Contracts
- [2019Mavridou A]VeriSolid- Correct-by-Design Smart Contracts for Ethereum
- [2019Nehai Z]Deductive proof of ethereum smart contracts using why3
- [2020A Permenev]VerX-Safety Verification of Smart Contracts
- [2020Ghaleb A]How effective are smart contract analysis tools? evaluating smart contract static analysis tools using bug injection
- [2020Gustavo Grieco]Echidna effective, usable, and fast fuzzing for smart contracts
- [2020J Ye]Clairvoyance-cross-contract static analysis for detecting practical reentrancy vulnerabilities in smart contracts.
- [2020Lexi Brent]Ethainter-A Smart Contract Security Analyzer for Composite Vulnerabilities
- [2020Li A]Securing Smart Contract with Runtime Validation
- [2020Liu Y]ModCon-A Model-Based Testing Platform for Smart Contracts
- [2020Liu Y]Towards Automated Verification of Smart Contract Fairness
- [2020Sarra Alqahtani]Formal Verification of Functional Requirements for Smart Contract Compositions in Supply Chain Management Systems
- [2020Security]ETHBMC-A Bounded Model Checker for Smart Contracts
- [2020SM Beillahi]Behavioral Simulation for Smart Contracts
- [2020Wüstholz V]Harvey-A Greybox Fuzzer for Smart Contracts

## Survey

- [2017Nicola Atzei]A survey of attacks on Ethereum smart contracts
- [2020Ghaleb A]How effective are smart contract analysis tools? evaluating smart contract static analysis tools using bug injection(**new**)
  - 关于静态工具的survey
- 

##  Testing

- [2020Gustavo Grieco]Echidna effective, usable, and fast fuzzing for smart contracts ( new )
- [2020Wüstholz V]Harvey-A Greybox Fuzzer for Smart Contracts ( new )
- [2020Liu Y]ModCon-A Model-Based Testing Platform for Smart Contracts(**new**)
- [2019Kolluri A]Exploiting the laws of order in smart contracts( **new ** )
  - 使用动态测试方法，在基于以太坊字节码的基础上，构造输入并尝试遍历所有的事件顺序，查找是否有违背特定模型的事件顺序
  - 将合约事件的符号化执行和事件顺序的随机模糊测试结合在一起，以指数的方式减少了搜索空间

## Static

- [2016LCO]Making Smart Contracts Smarter-oyente
- [2019Mark Mossberg]Manticore A User-Friendly Symbolic ExecutionFramework for Binaries and Smart Contracts
- [2020J Ye]Clairvoyance-cross-contract static analysis for detecting practical reentrancy vulnerabilities in smart contracts.(**new**)
- [2020Lexi Brent]Ethainter-A Smart Contract Security Analyzer for Composite Vulnerabilities(**new**)
- [2018Tsankov P]Securify Practical security analysis of smart contracts
  - 需要两个输入，包括合约的EVM字节码和一组由特殊设计的特定域语言制定的安全模式。Securify提供了两种安全模式：合规性和违规性，分别代表合约是否满足或违背特定安全属性
  - 对合约进行分析，以推断出语义事实，包括数据和控制流依赖性，Securify可以通过这些语义事实掌握合约的所有行为。接着Securify会检查输入提供的安全模式。对于任何违反模式的行为匹配，Securify都会输出匹配该模式的指令
- [2020Security]ETHBMC-A Bounded Model Checker for Smart Contracts
  - ETHBMC是基于符号化执行，可以对智能合约检查符合预定义的模型，当预定义的模型被违背时，ETHBMC可以自动生成具体的合约调用输入值

# Theorem Proof

- [2016Karthikeyan Bhargavan]Formal verification of smart contracts Short paper
  - 将使用Solidity编写的智能合约或者智能合约编译后的字节码转换为功能性变成语言F*，同时后端使用SMT求解器来静态验证性质
  - 仅对特小范围内合约进行来验证，且全程需要手工转换
- [2017Hirai Y]Defining the Ethereum Virtual Machine for Interactive Theorem Provers
  - 使用Lem语言定义了以太坊虚拟机
  - 使用定理证明其Isabelle/HOL证明了几个智能合约的安全性和不变式
  - 在小程序上验证所需的时间很长
- [2019Nehai Z]Deductive proof of ethereum smart contracts using why3
  - 将现有的合约转换为Why3编码的程序，然后验证其是否存在功能性错误或运行时错误，最后将Why3编码的程序编译为EVM字节码
  - 用能源市场的案例说明了方法的可行性
- [2018Yang Z]Formal process virtual machine for smart contracts verification

## Model Checking

- [2018Nehai Z]Model-checking of smart contracts

  - 将智能合约建模成NuSMV模型，待验证的性质使用CTL描述。模型分为三层，内核层捕获以太坊区块链的行为，应用程序层针对的是智能合约本身的建模，环境层确定智能合约的执行框架
  - 使用NuSMV工具来进行验证
  - 仅对一能源案例进行来验证，且均为手工建模

- [2018S Kalra]ZEUS-Analyzing Safety of Smart Contracts ( **new** )
  
  - ZEUS将智能合约及需要验证的策略作为输入，首选对智能合约做静态分析，将需要验证的策略使用assert作为断言插入到合约代码中。然后ZEUS将插入断言后的合约代码转换为LLVM代码，最后利用符号模型检测工具CHCs来判断断言是否被违背
  
- [2018Tesnim Abdellatif]Formal verification of smart contracts based on users and blockchain behaviors models

- [2019Albert E]SAFEVM-a safety verifier for Ethereum smart contracts(**new **)
  
  - 将Solidity源码或其编译后的字节码作为输入，使用注释的方式定义需要验证的属性
  - 使用Oyente工具生成控制流图CFG，再使用EthIR从CFG中将EVM字节码反编译为基于规则的表示模型,最后将RBR模型及CFG转换为C语言程序，使用VeryMax、CPAchecker及SeaHorn等验证器来进行验证。
  - 该工作目前尚处于原型阶段。
  
- [2019Mavridou A]VeriSolid- Correct-by-Design Smart Contracts for Ethereum

  - 首先使用迁移系统来建立智能合约模型，使用计算树逻辑来表达需要验证的性质如安全性、活性和无死锁性质等
  - 使用模型检测工具nuXmv验证模型是否满足待验证的性质，若性质满足，VeriSolid可将迁移系统模型转换为Solidity编写的智能合约

- [2020A Permenev]VerX-Safety Verification of Smart Contracts(**new**)
  
  - Verx的输入包括一个或者多个合约C及待验证的性质，首先在基于区块链全局状态下构建中间合约C`及性质, 然后利用符号化执行来递归验证是否满足，若验证成功则表明C满足性质。若不满足，VERX结合谓词抽象及符号化执行，生成C的不动点，然后验证性质是否满足该不动点，若不满足，则会有一个反例生成，若满足，则表明C满足性质
  
- [2020Liu Y]Towards Automated Verification of Smart Contract Fairness(**new**)
  
  - 只能对特定类的合约进行验证
  - 只能验证特定属性
  - 未对安全漏洞进行考虑
  
- [2020Sarra Alqahtani]Formal Verification of Functional Requirements for Smart Contract Compositions in Supply Chain Management Systems

- [2020SM Beillahi]Behavioral Simulation for Smart Contracts(**new**)
  
  - 将多个智能合约构建成多个有限状态机,然后使用BIP模型来构建多合约之间的交互，最后将BIP模型转换为NuSMV模型，使用模型检测工具NuSMV验证使用LTL描述的性质
  
  