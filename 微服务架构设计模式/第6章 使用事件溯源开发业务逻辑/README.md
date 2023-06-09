## 6.1 使用事件溯源开发业务逻辑概述
事件溯源是构建业务逻辑和持久化聚合的另一种选择。
它将聚合以一系列事件的方式持久化保存。
每个事件代表聚合的一次状态变化。
应用程序通过重放事件来重新创建聚合的当前状态。

> 模式：事件溯源
>
> 使用一系列表示状态更改的领域事件来持久化聚合。

### 6.1.1 传统持久化技术的问题
传统的持久化技术将类映射到数据库表，将这些类的字段映射到数据表中的列，将这些类的实例映射到数据表中的行。

![image](https://github.com/lemonshen00/reading-record/assets/13763576/13a0fd7b-c0c9-4938-b033-498ed1965dd6)

传统的应用程序，将订单实例保存为ORDER和ORDER_LINE_ITEM表中的行。
它可以使用诸如JPA之类的ORM框架（Hiberate）实现。

这种方法效果很好，大多数企业使用这种方式保存数据，但它有几个弊端：
- 对象与关系的“阻抗失调”
- 缺乏聚合的历史
- 实施审计功能繁琐
- 事件发布凌驾于业务逻辑之上


#### 对象与关系的“阻抗失调”
关系型数据的表格结构，与领域模型及其复杂关系的图状结构，存在基本的概念不匹配问题。

#### 缺乏聚合的历史
传统持久化方式只存储聚合的当前状态，聚合更新后，其先前的状态将丢失。

#### 实时审计功能繁琐
许多应用程序必须维护审计日志，用于跟踪哪些用户更改了聚合。
实施审计的挑战在于，负责记录审计日志的代码可能与业务逻辑代码发生偏离，导致各种错误。

#### 事件发布凌驾于业务逻辑之上
传统的持久化通常不支持发布领域事件。
某些ORM框架如Hibernate可以在数据对象更改时调用应用程序提供的回调接口，
但是，我们无法把自动发布消息作为更新数据事务的一部分。

### 6.1.2 什么是事件溯源

事件溯源是一种以事件为中心的技术，用于实现业务逻辑和聚合的持久化。
聚合作为一系列事件存储在数据库中。
每个事件代表聚合的状态变化。

![image](https://github.com/lemonshen00/reading-record/assets/13763576/17a84346-ba49-412d-a663-8e202a7a47f0)

#### 事件代表状态的改变
使用事件溯源时，包括创建在内的每一个聚合状态变化，都必须发出一个事件，
在此之前，聚合只需要发出哪些外部接收方感兴趣的事件。

而且，事件中必须包含聚合执行状态变化所需的数据。

