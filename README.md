Serverless WOW 项目是一款开源的 Serverless 架构性能评测项目，通过该项目，Case 贡献者可以按照规范，贡献测评 Case 到 [Serverless WOW test cases repo](https://github.com/serverless-wow/test-cases)，用户可以通过 [Serverless WOW 官网](https://www.serverless-wow.com)查看不同 Case 产生的数据报告，或者定制化订阅性能评测结果。

# 优势和价值

Serverless WOW 项目的五大优势：

![图片alt](https://serverless-article-picture.oss-cn-hangzhou.aliyuncs.com/1645340483014_20220220070130009977.png)

- **多云性能评测**：Serverless WOW 项目，通过不同的 Case 提供了包括 AWS、Azure、阿里云、腾讯云等诸多云平台在内的，多维度评测数据；
- **评测结果可订阅**：用户不仅可以随时通过官网查看各 Case 的数据报告，还可以通过选定不同 Case 定制化数据报表，并进行订阅，让数据报告实时掌握；
- **开源开放人人参与**：基于 GitHub Repo 进行进行 Case 模块的建设，任何人都可以通过提 PR，提交不同类型的 Case，以定制化获得数据报告；
- **定时生成专业报告**：每周生成一份数据报告，每月生成数据报告统计和分析，让数据报告更为长久和具有可参考性；
- **自定义报告维度**：可以根据已有的 Case ，定制化目标的数据报告，并订阅到自己的邮箱，以获得最为有价值的，实时数据报告；

随着时间的发展，Serverless架构已经被越来越多的人所关注，也逐渐的在各行各业得以应用，Serverless架构的各维度数据指标，也逐渐的被更多人所所需要，无论是调研使用，还是学习、科研使用，Serverless WOW项目，系统通过开源开放建设，可以为广大开发者、科研机构、组织提供更具有参考价值的数据指标，对平台的发展，行业的进步，透明化、可持续化，有一定的推动力。

# 架构原理

在整个项目中，有三个重要角色：

- **项目开发/维护者**：即 Serverless WOW 项目的开发团队，是由社区开发者共同组成；
- **Cases 贡献者**：按照 Serverless WOW 所提供的 Test Case 规范，贡献 Case 到 test cases repo 中的用户；
- **数据订阅者/用户**：通过 Serverless WOW 项目官网，查看数据/订阅数据到邮箱的用户；

其中**Cases 贡献者**以及**数据订阅者/用户**，在 Serverless WOW 项目下的工作流程与原理，以及项目的基础架构如下图所示：

![图片alt](https://serverless-article-picture.oss-cn-hangzhou.aliyuncs.com/1645344895824_20220220081457772467.png)

**Cases 贡献者**的使用流程主要是：

1. 按照 Serverless WOW 所提供的 Test Case 规范，通过提 PR，将 Case 提交到 test cases repo 中；
2. Serverless WOW 社区负责 Case 的审核（审核主要包括 Case 的安全性，稳定性以及合理性）；
3. 审核通过的 Case 可以被合并到 test cases repo 中；并触发的自动构建和发布，将 Case 部署到各个平台中；
4. 部署后的信息，上报到 Serverless WOW 后端，并持久化到数据库中（主要是 Case 的基本信息，以及 Endpoint 信息等）；

**Serverless WOW 后端服务**的工作流程：

1. 通过定时任务，触发评测逻辑，并获得评测结果；
2. 评测结果存储到对象存储，索引信息存储到数据库；
3. 针对部分订阅用户，将数据推送到订阅邮箱中；

**数据订阅者/用户**的使用流程主要是：

1. 通过 Serverless WOW 官网，进行基础的 Case 数据查看；
2. 用户可以定制化不同的 Case 数据，进行查看，并将定制化的数据信息，订阅到自己的邮箱，以便实时掌握测试数据；

Serverless WOW 项目前端将会通过 Vue.js 进行搭建，并部署到对象存储中，后端服务将会通过 Django 进行搭建，并部署到 FaaS 平台，定时任务将会采用 FaaS 平台的定时触发器进行触发；关于 Case 从仓库部署到不同的云平台，将会采用 Serverless Devs 的不同云厂商 Component 进行发布。

# Roadmap

项目随着时间的发展，在不同的时间段，会有不同的 Roadmap。当前 Serverless WOW 的 Roadmap 阶段是“Serverless WOW 项目正式启动”的[云启计划](https://github.com/orgs/serverless-wow/projects/1)。

历史 Roadmap：

- [云启计划](https://github.com/orgs/serverless-wow/projects/1)

# 项目贡献

我们非常希望您可以和我们一起贡献这个项目。贡献内容包括不限于代码的维护、Case 的贡献、文档的完善等，更多详情可以参考[ 🏆 贡献指南](./CONTRIBUTING.md)。

与此同时，我们也非常感谢所有👬 参与贡献的小伙伴（包括不限于 [Serverless WOW 贡献者](https://github.com/Serverless-WOW/website/graphs/contributors)、[Serverless WOW 文档贡献者](https://github.com/Serverless-WOW/docs/graphs/contributors)，以及 [Serverless WOW Test Cases 贡献者](https://github.com/Serverless-WOW/test-cases/graphs/contributors)）为 Serverless Devs 项目贡献的努力和汗水。

当然，Serverless WOW 项目由于是针对 Serverless 架构进行评测的项目，所以也会产生一定的费用，如果您想在资金上对我们进行支持，也非常感谢和欢迎，所有的资金资助可以通过支付宝转账到 `13500993691` ，Serverless WOW 项目将会每周定期更新费用支持赞助的[相关账单](./bill.md)

# 开源许可

Serverless WOW 遵循 [MIT License](./LICENSE) 开源许可。

项目在开发和上线的过程中，还会依赖部分外部依赖，这些外部依赖的所有文件都是本软件使用的外部维护库，具有自己的许可证；我们建议您阅读它们，因为它们的条款可能与[MIT License](./LICENSE)的条款不同。

## 额外声明

由于本项目是社区驱动，所有的 Case 均有社区贡献者贡献，本项目不承担评测 Case 以及结果的权威性责任，如果某些云厂商或者某些组织、个人，觉得某些 Case 侵害了他们的权利，可以通过 Issue 或者提 PR 申请删除某些 Case。

# 交流社区

您如果有关于错误的反馈或者未来的期待，您可以在 [Issues](https://github.com/serverless-wo w/docs/issues) 中进行反馈和交流。
