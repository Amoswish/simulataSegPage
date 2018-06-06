# 段页式虚拟存储管理

---

## 目的
1.	加深理解段页式虚拟存储管理的概念和原理。
2.	掌握段页式存储管理中存储分配（和回收）方法；
3.	深入了解段页式虚拟存储管理中地址重定位（即地址映射）方法。
4.	深入理解段页式虚拟存储管理中缺段、缺页中断处理方法。

---

##	内容
编写程序完成段页式虚拟存储管理存储分配、地址重定位和缺页中断处理。
1. 为一个进程的内存申请（多少个段，每个段多大）分配内存，当一个进程（完成）结束时回收内存；
2. 对一个给定逻辑地址，判断其是否缺段、缺页，若不缺段、不缺页，则映射出其物理地址；
3. 若缺段则进行缺段中断处理，若缺页则进行缺页中断处理。

假定内存64K，内存块（页框）大小为1K，进程逻辑地址空间最多4个段，每个段最大16K，进程驻留集大小为8页。假设进程运行前未预先装入任何地址空间，页面淘汰策略采用局部（驻留集内）置换策略。

每次存储分配/回收时，输出内存自由块分布情况、相关进程的段表和页表信息—最好使用图形界面（可视化）。
## 提示
1.	内存状态描述 
    -	分块（页框）说明表内容：编号、状态
    -	组织方式：线性表，位图？
    -	设置初始内存分配状态：随机设定若干块为已分配。
2.	段表、页表设计及其关系
3.	逻辑地址的表示
4.	缺段、缺页中断处理中的页面淘汰
- 	分别采用FIFO和LRU页面淘汰策略,选择要淘汰的页
##	测试输出
- 	输出当前内存分配情况（有多少可用块、哪些块可用？）；
-	手工输入进程的内存总需求（多少段，每个段多大）；
-	手工输入某进程的内存申请（哪几个段、各段多大？），输出系统为其分配内存后的段表和页表内容。
-	模拟内存访问指令的地址映射：比如手工输入一个逻辑地址，系统提示是否缺段、缺页，若不缺段、不缺页，则输出其物理地址；
-	若缺段或缺页，则输出被装入的块号（分别采用FIFO和LRU页面淘汰策略），输出缺段或缺页中断处理后的段表和页表信息。

