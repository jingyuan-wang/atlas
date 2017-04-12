### 斐波那契数列

首先，Story的点数跟人天和工作量没有直接的一一对应关系，5个点的Story只是比3个点的Story相比较需要更多的工作量。其次，之所以
采用非线性增长（指数增长）的斐波那契数列，原因有二：

1.  软件复杂度本身就是非线性的
1.  越大说明越不准（而不是越难，或者工作量越大），驱动BA进行新的拆分

通常的做法是，找到基准卡 -- 所有Dev，QA都对改卡的大小没有异议，然后定这个卡的点数为1。然后拿出其他卡来和这张卡比较，如果更难，那么可以
记为2。然后找下一张卡，如果比点数为2的还复杂，那可以记为3，依次类推。当然，一轮估点可能会有偏差，Dev们可以估好几轮。

另外，斐波那契数列并不是唯一的方式，常用的还有T恤尺寸（S，M，L，XL，XXL），交通工具（滑板车，自行车，小汽车，卡车，火车）等等方式。这些方式可以
让使用者彻底与可能产生人天联想的数字脱离开关系。

所以新的作业（的一部分）是，翻译这篇文章

- [Why Progressive Estimation Scale Is So Efficient For Teams](http://www.yakyma.com/2012/05/why-progressive-estimation-scale-is-so.html)

翻译结果写成markdown文件就好了。

### 关于实例化需求（Specification By Example）

>    **AC1:**
>
>    - Given：登陆p-link首页
>    - When：点击"自定义模式"
>    - Then：打开自定义设置的侧边栏
>
>    **AC2:**
>    - Given：在首页自定义侧边栏
>    - When：勾选新项目
>    - Then：对应项目出现在左侧
>
>    **AC3:**
>    - Given：在首页自定义侧边栏
>    - When：解除勾选某项目
>    - Then：对应项目消失在左侧


如果我来写`AC`，可能是这样的：

#### AC1

- Given：首页上有三张卡片： **我的项目**、**项目预算**、**项目管理**
- When：点击"自定义模式"
- Then：侧边栏中的 **我的项目**、**项目预算**、**项目管理** 的checkbox处于选中状态
- And：侧边栏中的其他可选项目处于未选中状态

#### AC2

- Given：首页上有三张卡片： **我的项目**、**项目预算**、**项目管理**
- When：点击"自定义模式"
- Then：去掉对 **我的项目** 的选中状态
- Then：首页上剩余两张卡片：**项目预算**、**项目管理**

#### AC3

- Given：首页上有三张卡片： **我的项目**、**项目预算**、**项目管理**
- When：点击"自定义模式"
- Then：选中 **待办工时** 项目
- Then：首页上上出现四张卡片：**我的项目**、**项目预算**、**项目管理** 和 **待办工时**

区别在于，你在列举AC的时候，要通过业务语言来举出具体的例子。避免使用诸如`某选项`，`一个选项`这样的generic的描述。这也是`Specification By Example`的本意。

实例化需求的作用比任何单独的BA技能都更重要，请好好学习一下。

所以作业的另外一部分来了，翻译这篇文章：

- [Anatomy of a good acceptance test](https://gojko.net/2010/06/16/anatomy-of-a-good-acceptance-test/)

### Story拆分

我之前在华为给客户培训Story拆分的时候，[翻译过一篇文章](https://github.com/abruzzi/consulting/issues/1)，[原文在此](http://agileforall.com/patterns-for-splitting-user-stories/)
基本上你看完就大概知道如何做比较合理的Story拆分了。

不过也有一些没有覆盖的点：

- 在一个新的团队中，在第一个迭代的时候，如何估算
- Spike如何度量及估算工作量

有了这个文章做指导，请以PLink的一个需求为例，划分Story。不要被现在已有的划分方式干扰，假设你从客户那里拿到了最原始的需求，你自己如何来做拆分。


### 参考资料

- [3 Powerful Estimation Techniques for Agile Teams](https://www.sitepoint.com/3-powerful-estimation-techniques-for-agile-teams/)
- [邱俊涛之前翻译+整理的Story拆分模式](https://github.com/abruzzi/consulting/issues/1)
- [邱俊涛之前写的一篇博客](http://icodeit.org/2015/01/page-object-with-site-prism/)（技术细节可以跳过，看后半部分就好了）
