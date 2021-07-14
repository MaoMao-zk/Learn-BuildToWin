# 个人技术与流程

### PSP（Personal Software Process, 个人软件开发流程）

#### PSP 2.1
* Planning
    * Estimate [1]
* Development
    * Analysis [2.1]
    * Design Spec [2.1]
    * Design Review [2]
    * Coding Standard [0.1]
    * Design
    * Coding
    * Code Review [2]
    * Test
* Record Time Spent
* Test Report [1]
* Size Measurement [0.1]
* Postmortem
* Process Improvement Plan [0.1]

### 个人开发需要重视的一些点
#### 单元测试
如何能让自己负责的模块功能定义尽量明确，内部的改变不会影响其他模块，模块的质量能得到稳定的、量化的保证？**单元测试**是一个很有效的解决方案。

* 好的单元测试标准
    * 在最基本的功能/参数上验证程序的正确性
    * 由最熟悉代码的人来写
    * 测试过后，机器状态保持不变（运行环境）
    * 执行速度快
    * 产生可重复，一致的结果（避免随机）
    * 独立性
    * 覆盖所有代码路径
    * 集成在自动化测试框架中
    * 和产品代码一起保存和维护

#### 回归测试
保证修改代码后不会发生倒退、退步。最好也是自动化的。

#### 效能分析
使用分析工具帮助我们分析性能瓶颈，而不是盲目的去修改

## 实践：实现WC
```
预估时间：(coding + test case)
基本功能：4h + 2h
扩展功能：6h + 3h
高级功能：放弃
```
TODO：
