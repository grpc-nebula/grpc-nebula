## grpc-nebula: 基于gRPC开发的高性能微服务治理框架

## 1. 项目简介

微服务治理框架，基于开源项目 [grpc](https://github.com/grpc/grpc) 和 [grpc-java](https://github.com/grpc/grpc-java) 进行开发，新增如下特性：

- 服务自动注册与发现。采用zookeeper为注册中心，服务与注册中心之间保持长链接，具有心跳检测机制，能够周期性的检查服务的状态，确保服务可用性状态一致性，可处理服务进程意外终止、服务器宕机等场景。
- 服务调用负载均衡。对于多实例的服务的调用，提供对多个服务实例的负载均衡调度，实现负载按照预定的调度算法进行调度执行。
- 服务流量控制。通过设置请求数或连接数上限，动态实现对各服务接口的流控管理。
- 服务访问控制与黑白名单机制。提供多种形式的服务访问控制策略，能够根据设定的安全策略对调用者进行安全检查，支持黑白名单等安全机制。
- 服务调用异常处理。当一个服务有多个服务器实例时，如果客户端调用A服务器连续多次出错，框架会自动将了客户端的HTTP/2连接切换到提供相同服务的B服务器。

## 2. 项目背景

微服务治理框架是由东方证券和博云联合开发。

随着东方证券业务的多年发展，已有大量的业务及支撑系统上线运营对外提供服务，服务与服务之间开始呈现复杂的依赖关系，系统运维的复杂度急剧增加。特别是由于以往系统建设主要由各厂商开发等因素的影响，东方证券内部存在大量的异构业务系统，对外暴露的接口也呈现多种形式，进一步增加了系统开发、运维的难度。

东方证券内已经建设或正在建设的业务系统种类繁多，包括网上交易、APP、互联网中台、集中交易、账户系统、清算系统等，除此之外还有很多正在规划的业务系统。各业务系统一般由不同的项目团队或供应商开发，并交付给东方证券的系统运行部门统一运维，在这个过程中存在诸多问题。

针对以上需求，同时根据东方证券大中台能力中心整体建设规划，基于gRPC框架技术，新增服务治理特性，构建微服务治理平台，从而实现东方证券内部及外部服务的统一化管理，构建服务调用关系及拓扑结构，优化改进服务质量。

**开源的内容为[东方证券微服务治理平台](./东方证券微服务治理平台.md)的RPC框架部分。**

## 3. 框架源代码

- [微服务治理框架Java实现-grpc-nebula-java](https://github.com/grpc-nebula/grpc-nebula-java)
- [微服务治理框架C++实现-grpc-nebula-c](https://github.com/grpc-nebula/grpc-nebula-c)


## 4. 框架文档

- Java 语言版本
	- [微服务治理框架(Java版)开发环境搭建与配置](https://github.com/grpc-nebula/grpc-nebula-java/tree/master/docs/微服务治理框架(Java版)开发环境搭建与配置.md)
	- [微服务治理框架(Java版)开发手册](https://github.com/grpc-nebula/grpc-nebula-java/tree/master/docs/微服务治理框架(Java版)开发手册.md)
	- [微服务治理框架(Java版)详细设计](https://github.com/grpc-nebula/grpc-nebula-java/tree/master/docs/微服务治理框架(Java版)详细设计.md)
	

- C/C++ 语言版本
	- [微服务治理框架(C++版)开发环境搭建与配置](https://github.com/grpc-nebula/grpc-nebula-c/tree/master/docs/微服务治理框架(C++版)开发环境搭建与配置.md)
	- [微服务治理框架(C++版)开发手册](https://github.com/grpc-nebula/grpc-nebula-c/tree/master/docs/微服务治理框架(C++版)开发手册.md)
	- [微服务治理框架(C++版)详细设计](https://github.com/grpc-nebula/grpc-nebula-c/tree/master/docs/微服务治理框架(C++版)详细设计.md)


