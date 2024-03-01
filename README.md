# proj298-Linux-Virtual-address-and-page-table-page-mapping
## Linux 内核页表共享中虚拟地址与页表页映射关系设计。

## 项目描述

内存页更新算法一直是操作系统的热门话题，在现代计算机内存的飞速增长，和更多的速度/大小分级下，页分配与回收， 页管理的算法，工作集的判断与处理都有继续探讨的必要。 Linux内核也在这个领域不断进化， 但是仍然有一些可以继续探索的机会。

页表共享是最近两年 Linux 社区讨论比较热门和实用的特性。在多进程形式的应用中，比如 PostgreSQL，需要共享大块连续的内存，并发数达到三四百，甚至上千，原有的内存共享方式耗费大量页表页，页表共享是其中的一种解决方法，当前 anolis 已经率先实现了一种页表共享方案。但是当前anolis页表共享方案中，直接使用 mm_struct 结构体管理共享页表，可复用多个内核中函数，但结构冗余，有很大简化空间。


## 预期目标

- 采用其他数据结构替换 mm_struct，保证结构简单和稳定性；
- 页表共享功能正常使用，无明显宕机问题；

## 特征

- 构建类似shadow mm_struct结构体，管理共享页表；

## 已有参考资料

- [龙蜥anolis页表共享实现](https://gitee.com/anolis/cloud-kernel/pulls/2550)

## 赛题分类

内核完善

## 参赛要求

- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生或研究生
- 允许学生参加大赛的多个不同题目，最终自己选择一个题目参与评奖
- 请遵循“2024全国大学生操作系统比赛”的章程和技术方案要求

## 难度

高等

## License

GPL-2.0 License

## 所属赛道

2024全国大学生操作系统比赛的“OS功能挑战”赛道

## 项目导师

- 姓名：王鹏
- 单位：阿里云
- github ID：[https://github.com/vipwangerxiao](https://github.com/vipwangerxiao)
- email：[zhiyun.wp@alibaba-inc.com](zhiyun.wp@alibaba-inc.com)

- 姓名：王荣巍
- 单位：阿里云
- github ID：[https://github.com/wangrongwei](https://github.com/wangrongwei)
- email：[rongwei.wrw@alibaba-inc.com](rongwei.wrw@alibaba-inc.com)
