# 简介
openAI开源免费项目，包括 SDK 独立接入、API 接口接入、MQ 消息接入，以及使用提供好的服务类接入等。其中Chat_sdk_java是对接国内大模型ChatGLM,Chat_API_java是连接前端和Chat_sdk_java的部分，Chat_wed是网站前端。
## Chat_sdk_java
  这部分在架构上设计独立的 SDK，在实现上采用了 Session 会话模型进行处理，以及通过工厂处理服务。在细节对上，采用了 OKHttp3 框架完成模型对接，这样的方式更好扩展，代码也更易于维护。
## chat_API_java
采用 DDD 架构 API，以及便于不同领域模块的独立设计，一个领域就是一个功能域。在功能域中提供模型、仓储、事件、服务。这样可以更好扩展。
鉴于生成式服务的文本生成可能会有不可靠信息，所以对这部分内容添加了敏感词的过滤。并可根据不同场景选择不同范围的敏感词处理。
对接微信扫码支付，完成从商品库、下单支付、异步发货、掉单补偿等核心流程实现。让用户可以在线购买对话额度。
## Chat_wed
使用 Next.js 构建的 React、Typescript 语言，构建的前端工程。同时使用了 React Route 路由子页面的开发技术，以及相应的信息传递。跨域接口的对接以及本地 json 数据加载。
使用本地浏览器内存，存储 Token、配置、对话等信息。
  
