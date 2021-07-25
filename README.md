# Part I 10pts

ddl 7.26

**熟悉你的框架**

对于一个基本数据结构，我们一定会涉及以下四个部分：增、删、查、改，对于 B+ 树也不例外。为了减少大家的工作量，我们引入了一套非常优秀的框架，框架已经正确地实现了这些基本功能。不过，在增加新功能之前，我们希望你们尽可能熟悉这套框架的内容，包括但不限于接口的使用等。因此，第一个部分主要需要完成 main 函数中的测试，并利用 point query 实现最简单的 range query。

具体来说，框架的作者提出了一些测试数据，你们需要实现 main.cpp 文件，读取测试数据，调用相关接口完成计算，然后按照规定输出结果。另外，查询操作分为两大类：点查询（point query）与范围查询（range query），一种最简单的 range query 的实现即为很多个 point query，在这个部分可以使用这种 brute force 的策略实现 range query。

具体来说，你需要在 `main.cpp` 中通过以下测例：

第一行为四个整数 `n` `m` `p` `q`

后面 `n` 行每行为一个 `kv` 对，保证 `key` 不重复，需要插入 `map` 中

接下来有 `m` 个点查询，每行给定一个 `key`，若存在则输出对应的 `value`，否则输出 `NOT FOUND`

然后 `p` 行每行为一个 `kv` 对，需要在 `map` 中更新，保证每个 `key` 都曾被插入过

接下来有 `q` 个范围查询，每行给定 `lvalue` 与 `rvalue`，请输出在 `[lvalue, rvalue)` 中出现的 `key` 的个数

输入保证所有数据均为 `int` 类型

（测试样例待补充，不卡性能）

___

# Part II 50pts

ddl 8.1

**更加高效的范围查询**

在 Part II 中我们熟悉了 B+ 树的代码框架与基本接口使用，并用非常原始的方式实现了范围查询。这很简单，但也确实非常低效。如果在中间节点存储相关信息，是否可以避免很多深入遍历的过程？请思考如何在结点上维护额外的信息，从而大幅增加 range query 的效率。注意你可能需要仔细观察框架中增删改的操作，结点中的额外信息在很多部分都要额外维护。

我们会从正确性、性能和设计思路的方面进行评价。

请改进你的程序，使之通过以下测例：

第一行为两个整数 `n` `m`

后面 `n` 行每行为一个 `kv` 对，`key` 可能出现重复，若重复将覆盖

接下来有 `m` 个范围查询，每行给定 `lvalue` 与 `rvalue`，请输出在 `[lvalue, rvalue)` 中出现过 `key` 的个数

输入保证所有数据均为 `int` 类型

注：可以直接使用 Part I 中用到的 `btree_map` 接口，也可以使用 `btree_set`，对此不做要求

（测试样例待补充，加入性能要求）
