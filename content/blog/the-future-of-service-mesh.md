---
title: "服务网格的未来Part 2：Istio 1.0之后何去何从？"
date: 2018-11-01T20:10:14+08:00
draft: false
banner: "https://ws1.sinaimg.cn/large/006tNbRwly1fwstnltjbgj31ji15ox6q.jpg"
author: "Stephen McPolin & Venil Noronha"
authorlink: "https://blogs.vmware.com/opensource/author/opensourceteam/"
translator: "陈冬"
translatorlink: "https://github.com/shaobai"
reviewer: "宋净超"
reviewerlink: "https://jimmysong.io"
originallink: "https://blogs.vmware.com/opensource/2018/10/23/service-mesh-whats-next"
summary: "本文通过分析服务网格的优势，阐述了其未来的发展情况。"
tags: ["servcie mesh"]
categories: ["translation"]
keywords: ["service mesh","服务网格"]
---

在我们的服务网格系列的第一部分中，我们认为服务网格是微服务架构发展的必然结果。随着 Istio 1.0 的发布，服务网格经过了一个重要的里程碑，在这个时间节点上需要考虑下一步该如何进行。

当然，在 VMware中，我们相信非常值得花时间来支持开源的服务网格架构。我们已经成为 Istio 和 Envoy 的贡献成员。我们在改善网络方面投入了大量的精力，并在其他领域定期作出贡献。

我们也考虑到事实上，几乎每个 Istio 的演示目前都是基于一个单一的示例。保加利亚的一位 VMware 同事目前正在构建一个全新的 Istio 演示示例，用于演示如何在封闭字幕等服务之间管理视频质量，并演示 Istio 在微服务环境中的动态路由的能力。

因为我们认为服务网格是有价值的，它将长期发展，所以我们一直在寻求将 VMware 自己的世界级系统管理工具集成到服务网格框架中。我们最近创建了一个适配器，将 Istio metrics 导出到 VMware 的 Wavefront 监测和分析工具中。如果我们能够将微服务中的更多信息合并到我们的系统管理工具中，我们相信这些工具能够更好的管理系统。

![](https://ws2.sinaimg.cn/large/006tNbRwgy1fwp4etrgwvj30sg0iz782.jpg)

从我们的角度来看，这样的工作是为了扩大微服务生态系统。然而，服务网格平台本身还不够完善。例如，Istio 是一个复杂的软件，出问题时很难调试。当它运行正常时，可以帮助你管理微服务。当它不能正常工作时，又很难弄清楚它为什么不能工作。 这一点在社区中已经广受诟病，我们一直在花时间和精力思考如何克服这种复杂性，但目前我们还没有解决这个问题。

服务网格平台也是刚开始处理多集群情况。如果你将软件部署在一个集群上，像 Istio 和 Envoy 这样的服务通常能够很好的管理它们。但是你希望将单集群扩展到多集群，并让服务在集群边界上进行通信（从安全的角度来看是一个好想法），那这可能是一个挑战。再次，Istio 社区理解这一点，我们正在逐步改进，进行多集群友好的设计。

最后，我们正在关注一个新的倡议，来自 Google 的 Knative。从根本上说，这是基于 Kubernetes 和 Istio 在 Google 的“函数即服务”的概念中构建的。看起来在不久的将来，它将向 Istio 提出更多的要求，但是目前还不清楚这些要求从何而来。例如，“事件”对于 Istio 来说是一个完全陌生的概念，但是对于处理临时数据还是必要的。Knative 为此增加了一些工具，这将对 Istio 产生压力。

现在，我们正在关注Knative，推出大约一个半月了，并且还有很多问题没有解决，此时我们在决定如何应对之前正在寻找更新。因此，这两点都会受到持续关注。但是可以肯定的是，服务网格的脚步将更加坚实。