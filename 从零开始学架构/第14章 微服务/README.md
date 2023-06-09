## 第14章 微服务

### 微服务的陷阱
1. 服务划分过细，服务间关系复杂
2. 服务数量太多，团队效率急剧下降
3. 调用链太长，性能下降
4. 调用链太长，问题定位困难
5. 没有自动化支撑，无法快速交付
6. 没有服务治理，微服务数量多了后管理混乱
  - 服务路由：假设某个微服务有 60 个节点，部署在 20 台机器上，那么其他依赖的微服务如何知道这个部署情况呢？ 
  - 服务故障隔离：假设上述例子中的 60 个节点有 5 个节点发生故障了，依赖的微服 务如何处理这种情况呢？ 。 
  - 服务注册和发现：同样是上述的例子，现在我们决定从 60 个节点扩容到 80 个节点， 或者将 60 个节点缩减为 40 个节点，新增或减少的节点如何让依赖的服务知道呢？

### 微服务的最佳实践
1. 服务粒度：3个人负责一个微服务（“两个披萨”理论（每个团队的人数不能多到两个披萨都不够吃的地步））
2. 拆分方法
  - 基于业务逻辑拆分（DDD）
  - 基于业务稳定性拆分：将系统中的业务模块按照稳定性进行排序，将己经成熟和改动不大的服务拆分为稳定服务
  - 基于基于可靠性拆分：将可靠性要求高的核心服务和可靠性要求低的非核心服务拆分开来
  - 基于性能拆分：将性能要求高或性能压力大的模块拆分出来
3. 基础设施
  - 自动化测试
  - 自动化部署：自动化部署系统包括版本管理、资源管理（例如，机器管理、虚拟机管理）、部署操作、回退操作等功能。
  - 接口框架：统一接口协议（如http） + 统一数据格式（如json）
  - 服务治理 = 服务注册和发现/服务路由/服务故障隔离/服务监控/服务跟踪

### 什么是service mesh
https://blog.51cto.com/u_15296180/3051398
