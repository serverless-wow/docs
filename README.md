# Serverless WOW

Serverless WOW 项目是一款开源的 Serverless 架构性能评测软件。

## 测试用例

- 指标
  - HTTP 函数，端到端平均延时，平均 QPS，函数每秒吞吐量
  - 函数请求实际处理时间，函数之间相互调用损耗时间
  - 函数冷启动时间,自定义容器冷启动时间
  - 函数在 VPC 里调用对应厂商的数据库，链接平均时间
- 条件
  - 串行连续 300 次请求
  - 冒烟测试，从 0 到并行 300 并发量，每次+10
- 维度

  - 云厂商
  - 运行时
  - 代码包规格
  - 函数类型
  - 触发方式
  - 是否是 web 框架

- 例子
  - 不同云厂商，不同运行时，hello-world
    - Python
      - Python2
      - Python3
    - Node.js
      - Node.js 10
      - Node.js 12
      - Node.js 14
    - PHP
      - PHP 7
    - Java
      - Java 8
      - Java 11
    - Custom Runtime
    - Custom Container
  - 不同云厂商，不同运行时，同运行时不同代码包规格
    - 1M
    - 10M
    - 20M
    - 100M
    - 200M
  - 不同云厂商，不同运行时，传统 Web 框架
    - Nodejs
      - koa
      - Express.js
      - Nuxt.js
      - nestjs
      - nextjs
    - python
      - Django
      - Flask
    - php
      - Laravel
    - java
    - SpringBoot
- 其他
  - 不同云厂商，不同运行时，实例带宽
  - 不同云厂商，不同运行时，CPU 性能
  - 不同云厂商，不同运行时，内存读写速度
  - 相同镜像/Code, 云托管与预留实例云函数之间相互比较
