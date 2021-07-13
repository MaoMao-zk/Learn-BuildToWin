# 概论

### 软件和程序
软件 = 程序 + 软件工程  
软件企业 = 软件 + 商业模式

### 软件的特殊性
1. 复杂性（Complexity）
    * 代码量大且增长快 vs. 工程师的智力和记忆力是一定的
1. 不可见性（Invissibility）
    * 代码不是软件本身，看不到代码是如何运行的
1. 易变性（Changeability）
    * 容易修改，期望软件在如下情况改变，但正确的修改软件并不容易
        * 让软件做新的事情
        * 让软件适应新的硬件
1. 服从性（Conformity）
    * 服从硬件要求
    * 服从用户的要求、行业系统的要求等
1. 非连续性（Discontinuty）
    * 输入上很小的变化，会引起输出上极大的变化

### 计算机科学 vs. 软件工程
计算机理论的进展会帮助软件工程（例如对程序正确性的分析）；  
软件工程的进展（更好的工具，更多的应用领域）会帮助计算机科学家更有效的进行实验和探索。

不同的项目：
* Build To Learn
* Build To Show
* Build To Serve
* Build To Win

### 软件工程的知识领域
TODO

### 软件工程的目标

本书的初步目标：
1. 研发出符合用户需求的软件
1. 通过一定的软件流程，在预计的时间内发布“足够好”的软件
1. 能证明所开发的软件是可以维护和继续发展的

## 练习与讨论
1. 自动生成小学四则运算题目的软件：
    ``` C++
    #include <stdlib.h>
    #include <string>

    std::string GenerateProperFraction(){
        std::string s;
        int a = rand()%100 + 1;
        s = std::to_string(a);
        s += "/";
        a += rand()%100 + 1;
        s += std::to_string(a);
        return s;
    }

    void GenerateQuestions(unsigned int count) {

        for(unsigned int i=0;i<count;i++) {
            std::string qustion = "";
            bool proper_fraction = rand()%2;
            if (proper_fraction) {
                qustion += GenerateProperFraction();
            } else {
                qustion += std::to_string(rand()%100 + 1);
            }

            int operator_value = rand()%4;
            switch (operator_value) {
                case 0:
                    qustion += " + ";
                    break;
                case 1:
                    qustion += " + ";
                    break;
                case 2:
                    qustion += " * ";
                    break;
                case 3:
                    qustion += " / ";
                    break;
            }

            if (proper_fraction) {
                qustion += GenerateProperFraction();
            } else {
                qustion += std::to_string(rand()%100 + 1);
            }

            printf("%s = \n", qustion.c_str());
        }

    }


    int main() {
        GenerateQuestions(10);
        return 0;
    }
    ```
2. TODO
3. TODO
4. 
```
软件有很多种：
ShrinkWrap（在包装盒子里面的软件）
Web APP（基于网页的软件）
Internal Software（企业或学校或某组织内部的软件）
Games（游戏）
Mobile Apps（手机应用）
Operating Systems（操作系统）
Tools（工具软件）
选取三种软件，请分析它们各自的特点。
1）这些软件的开发者是怎么说服你（陌生人）成为他们的用户的？他们的目标
都是盈利么？他们的目标都是赚取用户的现金么？还是别的？
2）这些软件是如何到你手里的（邮购，下载，互相拷贝……）
3）这些软件是如何处理bug的？又是如何更新新版本的？
4）同一类型的软件之间是如何竞争的？
列举你在使用上述软件时观察到的“特殊”现象，它们和硬件有什么不同？这些能
说明软件的某些本质特性么？
```

Web APP
* 能带来便利，他们的目标不一定是盈利的，大多数是提供给用户便利赚取流量费用、广告费用等。
* 通过搜索、广告、推荐等方式
* Server上直接release，用户访问到的永远是最新版
* 搜索的首位度、优质的用户体验和服务内容、快速获取客户

Operating Systems
* 垄断，大多数目标是盈利的，Windows直接赚取现金，不论是个人还是企业还是设备厂商；MacOS绑定自家的硬件进行售卖；Ubuntu等开源操作系统是不赚钱的
* 和设备一起，网上下载，或者DVD
* 通过推送新版本
* 拉取设备厂商、企业，进行垄断

Tools
* 提供有用的功能，大多数是盈利，通过售卖license等行为赚钱，也有一些开源的不盈利的为了让软件灵活的提供更丰富的功能，并提高自家的影响力，如VSCode
* 下载
* 推送新版本
* 更好的解决用户问题，培养用户习惯，能垄断就垄断

共同点：
* 获取更多的用户是必须的，当争取到大多数用户后往往形成垄断
不同点：
* Web APP一般并不赚钱，赚钱的是背后的服务，或者带来的流量产生的收益
* 操作系统往往和设备绑定售卖，因为操作系统和硬件设备的耦合
* Tools的商业模式较为简单，因为目的很明确，就是解决用户的实际问题


5. 上网调查一下目前流行的源程序版本管理软件和项目管理软件都有哪些，各有
什么优缺点？
    * Github vs. Gerrit
        * 功能：
            * 都是基于Git的管理软件
            * Github有更丰富的功能：issue、wiki、graph等
            * Gerrit没有pull request，代码review也更简单，更强大
        * Github的社交属性更强，适合提供给外部开发者贡献
        * Gerrit开发流程更简单、免费，部署方便，易于集成Jenkins等CI系统，适合内部开发
    * JIRA vs. PingCode
        * 都有任务管理、文档管理、项目流程等功能
        * PingCode更便宜，JIRA功能/插件更丰富
6. 软件工程是不是教那些不怎么会写程序的人开发软件？你怎么看？
    ```
    软件 = 程序 + 软件工程
    软件工程不是教不怎么会写程序的人开发软件
    是指导会写程序的人产出符合需求的软件、按时按计划完成软件、产出可持续维护的软件
    但一定程度上，软件工程（特别是软件设计）在把复杂需求拆解为很多小块功能后，不怎么会写程序的开发者也可以参与很庞大的软件开发中。
    ```
7. 略
8. 有人认为，“中文编程”，是解决中国程序员编程效率的一个秘密武器，请问它
是一个“银弹”么？
```
不是银弹，编程语言的关键字往往非常的少且简单，改变成中文反而会降低开发效率
```
9. 略