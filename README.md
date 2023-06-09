# 入门篇

- [南大pascal实验室静态分析课程](https://tai-e.pascal-lab.net/lectures.html)
- 一个小哥写的博客，可以作为静态程序分析的入门
  - [（一）初识软件分析](https://www.blog-blockchain.xyz/pl/understanding-program-analysis/)
  - [（二）数据流分析基础](https://www.blog-blockchain.xyz/pl/data-flow-analysis/)
  - [（三）Datalog和程序分析](https://www.blog-blockchain.xyz/pl/LP-souffle/)
  - [（四）静态单赋值和稀疏分析](https://www.blog-blockchain.xyz/pl/ssa-and-sparse-analysis/)
  - [（五）过程间分析](https://www.blog-blockchain.xyz/pl/Interprocedural-DFA/)
  - [（六）指向分析](https://www.blog-blockchain.xyz/pl/points-to-analysis/)
  - [（七）抽象解释](https://www.blog-blockchain.xyz/pl/abstract-interpretation/)
  - [（八）SMT和符号执行](https://www.blog-blockchain.xyz/pl/SMT-and-symbolic-excution/)
  - [（九）体验静态分析工具](https://www.blog-blockchain.xyz/pl/static-analysis-tools/)
- [自动化漏洞挖掘：静态程序分析入门【上】](https://mp.weixin.qq.com/s?__biz=MzUyOTkwNTQ5Mg%3D%3D&mid=2247487087&idx=1&sn=4ce42ac78f232a7d3fce13d6ed06c44e&chksm=fa58ac54cd2f254205e557f4cc9f5857d2a384bc89a36b15bf87212d50f52c2d51a8cef3c34f&scene=21&ref=www.ctfiot.com#wechat_redirect)
- [自动化漏洞挖掘：静态程序分析入门【下】](https://mp.weixin.qq.com/s?__biz=MzUyOTkwNTQ5Mg==&mid=2247487251&idx=1&sn=abef948993e7a1a3ddd7afc91d670429&chksm=fa58ad28cd2f243e96207bcf0f347e8e76b5cf808dd5002e0398eb16d176abeb178728599585&cur_album_id=2678810689347715073&scene=189#wechat_redirect)

# 工具篇

- [静态源代码安全扫描工具测评基准 V2.0](http://www.owasp.org.cn/OWASP-CHINA/owasp-project/secure%20coding%202016/%E9%9D%99%E6%80%81%E6%BA%90%E4%BB%A3%E7%A0%81%E5%AE%89%E5%85%A8%E6%89%AB%E6%8F%8F%E5%B7%A5%E5%85%B7%E6%B5%8B%E8%AF%84%E5%9F%BA%E5%87%86V2.0.pdf)

## soot

### 项目简介

soot 是 Java 优化框架。它提供了四个用于分析和转换 Java 字节码的中间表示：
- BAF：易于操纵的字节码的简化表示。 
- Jimple：一个适合优化的打字3个地址中间表示。 
- Shimple：Jimple的SSA变体。 
- grimp：jimple的汇总版本，适用于代码和代码检查。

### 项目地址

项目地址：[https://github.com/soot-oss/soot](https://github.com/soot-oss/soot)

### 相关资料

- [Soot Tutorials](https://github.com/soot-oss/soot/wiki/Tutorials)
- [Soot, a Tool for Analyzing and Transforming Java Bytecode](https://www.sable.mcgill.ca/soot/tutorial/pldi03/tutorial.pdf)
- [A beginner’s guide to static program analysis using Soot](https://noidsirius.medium.com/a-beginners-guide-to-static-program-analysis-using-soot-5aee14a878d)
- [Soot使用笔记](https://www.cnblogs.com/xine/p/14511818.html)
- [Soot使用记录](https://jckling.github.io/2022/02/23/Other/Soot%20%E4%BD%BF%E7%94%A8%E8%AE%B0%E5%BD%95/)
- [Android Taint Flow Analysis for App Sets](http://www.cs.tau.ac.il/~msagiv/courses/pa15-16/Static%20Analysis%20of%20Java%20and%20Soot.pdf)


## tabby

### 项目简介

TABBY 是一款针对 Java 语言的静态代码分析工具，相关工作已被接收发表在 The 53rd Annual IEEE/IFIP International Conference on Dependable Systems and Networks (DSN 2023)，会议论文录用名单详见DSN2023。
TABBY使用静态分析框架 Soot 作为语义提取工具，将JAR/WAR/CLASS文件转化为代码属性图。 并使用 Neo4j 图数据库来存储生成的代码属性图CPG。

### 项目地址

项目地址：[https://github.com/wh1t3p1g/tabby](https://github.com/wh1t3p1g/tabby)

### 相关资料

- [基于代码属性图的自动化漏洞挖掘实践](https://blog.0kami.cn/blog/2023/%E5%9F%BA%E4%BA%8E%E4%BB%A3%E7%A0%81%E5%B1%9E%E6%80%A7%E5%9B%BE%E7%9A%84%E8%87%AA%E5%8A%A8%E5%8C%96%E6%BC%8F%E6%B4%9E%E6%8C%96%E6%8E%98%E5%AE%9E%E8%B7%B5/)
- [如何高效的挖掘Java反序列化利用链？](https://blog.0kami.cn/blog/2021/how_to_find_gadget_chains/)
- [如何高效地捡漏反序列化利用链？](https://blog.0kami.cn/blog/2021/how_to_find_gadget_chains_2/)

## ByteCodeDL

### 项目简介

ByteCodeDL这个名字是从CodeQL演化的，ByteCode对应Code，DL对应QL，是一款声明式静态分析工具，主要是为了弥补CodeQL无法直接分析字节码的遗憾。

本项目主要有两个目的：
- 教学目的，帮助大家入门静态分析，本项目将演示如何通过datalog实现一些静态分析算法，比起命令式静态分析，这种方式要简洁很多，学习了基本原理之后，也可以自己DIY规则。
- 提高挖洞效率，安全研究人员一般拿不到源码，大多数情况只能分析Jar包，然后通过IDEA看反编译之后的代码，效率比较低，希望ByteCodeDL提供的搜索功能、调用图分析功能、污点分析功能，能够提高安全研究人员的挖洞效率。

### 项目地址

项目地址：[https://github.com/BytecodeDL/ByteCodeDL](https://github.com/BytecodeDL/ByteCodeDL)

## JavaParser

### 项目简介

支持将java代码转化为AST语法树。

### 项目地址

项目地址：[https://github.com/javaparser/javaparser](https://github.com/javaparser/javaparser)

### 相关资料

- [JavaParser: per generare, modificare e analizzare codice Java](https://tomassetti.me/wp-content/uploads/2017/12/JavaParser-JUG-Milano.pdf) *JavaParser介绍的PPT，可以做一个入门学习*
- [JavaParser: Visited](https://leanpub.com/javaparservisited) *官方出版的文档，可以免费下载*

## 按语言分

### Python

- [Python程序分析工具调研](https://jckling.github.io/2021/12/30/Security/Python%20%E7%A8%8B%E5%BA%8F%E5%88%86%E6%9E%90%E5%B7%A5%E5%85%B7%E8%B0%83%E7%A0%94/)
- [柏林洪堡大学 | 基于深度学习的Python代码漏洞检测 （IST 2022）](https://mp.weixin.qq.com/s/dxpvnt_dHPc92pw4J5bZww)
