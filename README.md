# NutzBoot 可靠的企业级微服务框架


```
 _   _ ______                                      ___   
| \ | || ___ \  ______ ______ ______ ______ ______| \ \  
|  \| || |_/ / |______|______|______|______|______| |\ \ 
| . ` || ___ \  ______ ______ ______ ______ ______| | > >
| |\  || |_/ / |______|______|______|______|______| |/ / 
\_| \_/\____/                                     |_/_/  
  
:: Nutz Boot ::
```

* 主页: [NB的官网](https://nutz.io)
* 关于Nutz: [Nutz](https://github.com/nutzam/nutz)
* 项目生成器: [NB Maker](https://get.nutz.io)
* 推荐项目: [NutzWk](https://github.com/Wizzercn/NutzWk)
* 推荐项目: [NutzSite](https://github.com/HaimmingYu/NutzSite)
* 版本历史: [NB进化史](ChangeLog.md)
* 文档: [NB的文档](https://gitee.com/nutz/nutzboot/tree/dev/doc)
* 文档2: [NB的文档2](http://nutzam.com/core/boot/overview.html)
* 社区: [NutzCN](https://nutz.cn) 推荐
* Idea插件 [NutzCodeInsight](https://github.com/threefish/NutzCodeInsight) 开发利器
* QQ群: 68428921(已满) 24457628(2群) 58444676(老吹水群)

[![Build Status](https://travis-ci.org/nutzam/nutzboot.png?branch=dev)](https://travis-ci.org/nutzam/nutzboot)
[![CircleCI](https://circleci.com/gh/nutzam/nutzboot/tree/dev.svg?style=svg)](https://circleci.com/gh/nutzam/nutzboot/tree/dev)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.nutz/nutzboot-parent/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.nutz/nutzboot-parent/)
[![GitHub release](https://img.shields.io/github/release/nutzam/nutzboot.svg)](https://github.com/nutzam/nutzboot/releases)
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)
[![Skywalking Tracing](https://img.shields.io/badge/Skywalking%20Tracing-enable-brightgreen.svg)](https://github.com/OpenSkywalking/skywalking)

## 功能介绍

* 快速创建Nutz应用,提供[初始化工具Maker](https://get.nutz.io)
* 嵌入式web服务(jetty/tomcat/undertow),直接打包为runnable jar
* 基于starter的自动配置体系,只需要添加maven依赖,即可自动发现并加载
* 能满足80%以上常见需求的默认配置,无需过多的自定义
* 以开放的心态与国内开源团体合作,优先集成国产项目
* 活跃的社区及稳健的发布周期,推进项目一直前进
* 提供swagger api文件自动生成

## 快速预览一下NB的项目吧

pom.xml

```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>org.nutz</groupId>
            <artifactId>nutzboot-parent</artifactId>
            <version>${nutzboot.version}</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
<dependencies>
    <dependency>
        <groupId>org.nutz</groupId>
        <artifactId>nutzboot-starter-jetty</artifactId>
    </dependency>
    <dependency>
        <groupId>org.nutz</groupId>
        <artifactId>nutzboot-starter-nutz-mvc</artifactId>
    </dependency>
</dependencies>
```

src/main/java/io/nutz/demo/simple/MainLauncher.java

```java
package io.nutz.demo.simple;

import org.nutz.boot.NbApp;
import org.nutz.ioc.loader.annotation.*;
import org.nutz.mvc.annotation.*;

@IocBean
public class MainLauncher {

    @Ok("raw")
    @At("/time/now")
    public long now() {
        return System.currentTimeMillis();
    }

    public static void main(String[] args) throws Exception {
        new NbApp().run();
    }
}
```

[![asciicast](https://asciinema.org/a/40Brr8ZNsHx1ILfjhJ7zppJ3v.png)](https://asciinema.org/a/40Brr8ZNsHx1ILfjhJ7zppJ3v)

请访问 [https://get.nutz.io](https://get.nutz.io) 获取属于您的基础代码

### Demo

* [内置demo](https://github.com/nutzam/nutzboot/tree/dev/nutzboot-demo),每个starter均配套一个demo
* **[NutzWk-NB分支](https://github.com/Wizzercn/NutzWk) 企业级微服务开发平台,非常靠谱 by 大鲨鱼**
* **[NutzSite](https://github.com/HaimmingYu/NutzSite) Java快速开发框架**
* [MqttWk](https://github.com/Wizzercn/MqttWk) 每秒处理10w+消息的全开源Mqtt服务端 by 大鲨鱼
* [WizzerCN](https://github.com/Wizzercn/Demo/tree/master/nutzboot-wizzer-cn) 一个简易且功能完整的网站源码 by 大鲨鱼
* [Todo-backend](https://github.com/nutzam/todo-backend-nutzboot),一个类就能通过TodoBackend的测试 by wendal
* [urls](https://gitee.com/howe/urls) Java版短地址服务 by howe
* [LuliChat](https://github.com/TopCoderMyDream/LuliChat/tree/nutzboot) 一个Nutz为后台支撑,T-io为通讯支持,LayIM为前台UI交互的纯国产框架开发的一个即时通讯项目 by 蛋蛋
* [NutzBoot项目生成器](https://gitee.com/nutz/nutzboot-project-maker) https://get.nutz.cn 的源码 by wendal
* [NutzBoot集成PageOffice](https://gitee.com/nutz/nutzboot-demo-pageoffice) PageOffice是私有云Office解决方案 by wendal
* [IP地址查询服务](https://gitee.com/nutz/ipd4nutzboot) http://ip.nutz.cn 的源码 by wendal
* [NutzCN-Nutzboot](https://github.com/wendal/nutz-book-project/tree/v5.x) NutzCN社区的源码,5.x分支,NutzBoot版
* [NutzBoot-Demo-Dao](https://github.com/nutzam/nutzboot/tree/dev/nutzboot-demo/nutzboot-demo-simple/nutzboot-demo-simple-dao) 演示Jetty+Dao的增删改查
## Contributors

* [蛋蛋](https://github.com/TopCoderMyDream)(提交了第一个Banner及打印逻辑)及starter-tio和starter-j2cache
* [胖五](https://github.com/pangwu86)(nutz.io主笔)
* [qinerg](https://github.com/qinerg)(率先提交undertow)
* [benjobs](https://github.com/wolfboys)(提交了tomcat)
* [温泉](https://github.com/ywjno)(提交thymeleaf和eureka静态status页面)
* [科技](https://github.com/Rekoe)(探路者,正在踩坑,正在做后台模板)
* [潇潇](https://github.com/howe)(探路者,生产环境填坑中)
* [道坤](https://github.com/albinhdk)(探路者,提交ssdb)
* [HeTaro](https://gitee.com/HeTaro)(探路者,正在踩坑)
* [zozoh](https://github.com/zozoh)(路过...)
* [wendal](https://github.com)(到处挖坑)
* [瞎折腾](https://gitee.com/lx19990999)(完善demo-maker)
* [天空](https://github.com/tiankongkm)(提交zkclient)
* [haoqoo](https://github.com/haoqoo)(提交velocity)
* [鱼夫](https://gitee.com/yustory)(正在踩NB+U家三剑客的坑)
* [幸福的旁边](https://github.com/happyday517)(提交caffeine方法缓存)
* [文涛](https://gitee.com/wentao0291) (新增支持加载外部配置文件，新增多数据库连接支持)
* [zjSniper](https://gitee.com/zjSniper) (优化starter-tio的逻辑)
* [tasdingoo](https://github.com/tasdingoo)(issue@github 122)
* [csl_slchia](https://gitee.com/csl_slchia)(issue@gitee II92L)
* [大鲨鱼](https://github.com/Wizzercn)(提交starter-wkcache/elasticsearch/sentinel等,扩展NB功能)
* [threefish](https://github.com/threefish)(Nutz Intellij idea插件,提交starter-email/sqlXmlTpl)
* 还有您的名字哦,告知我们吧

## 采用NutzBoot的公司

请访问链接 [采用公司](https://github.com/nutzam/nutzboot/issues/62)

## 文档

* [NutzBoot简介](doc/overview.md)
* [NutzBoot目录约定](doc/struct.md)
* [NB与Nutz.Mvc对比](doc/diff_nb_mvc.md)
* [转换为NB项目](doc/convert2nb.md)
* [Maven Plugin](https://github.com/nutzam/nutzboot-maven-plugin)
* [配置信息总表](doc/configure.md) 不定期更新,可通过nutzboot:propdoc生成
* [Jetty配置详解](doc/jetty_usage.md)
* [添加Web过滤器](doc/add_web_filter.md)

## 开发进度

期待您的加入, 下述 by `xxx` 为通常是集成该功能的首次提交者,不一定对应软件的作者

- 基础框架
    - [x] 基础框架的文档
    - [x] nutzboot-core 核心框架的实现
- 嵌入式web容器
    - [x] **starter-[jetty](https://www.eclipse.org/jetty/)**
    - [x] starter-[undertow](http://undertow.io/) by [@qinerg](https://github.com/qinerg)
    - [x] starter-[tomcat](http://tomcat.apache.org/) by [@benjobs](https://github.com/wolfboys) 
- 分布式组件
	- RPC(Remote Procedure Call)
	    - [x] literpc 简洁高效RPC,由NutzCloud提供
		- [x] **starter-[dubbo](http://dubbo.apache.org) 阿里出品的高性能RPC平台**
		- [x] starter-[zbus](http://zbus.io) 国产知名RPC平台
		- [x] starter-[feign](https://github.com/OpenFeign/feign) makes writing java http clients easier, by [haoqoo](https://github.com/haoqoo) and [wendal](https://github.com/wendal)
		- [x] [ribbon](https://github.com/Netflix/ribbon) ,集成在feign中,配合erueka-client实现负载均衡
		- [x] [servicecomb](http://servicecomb.apache.org) Apache ServiceComb
    - [x] starter-zkclient zookeeper的封装
    - [x] **starter-[sentinel-dubbo](https://github.com/alibaba/Sentinel)** 阿里出品的分布式系统的流量防卫兵,集成dubbo by [大鲨鱼](https://github.com/Wizzercn)
    - [x] starter-[sentinel-annotation](https://github.com/alibaba/Sentinel) 阿里出品的分布式系统的流量防卫兵,基于原生注解
    - [x] starter-[hystrix](https://github.com/Netflix/Hystrix) 熔断器及其dashboard
    - 服务注册
        - [x] loach-server '泥鳅'服务端,由NutzCloud提供
        - [x] loach-client '泥鳅'客户端,由NutzCloud提供
        - [x] starter-[eureka-server](https://github.com/Netflix/eureka) 服务治理的服务器端
        - [x] starter-[eureka-client](https://github.com/Netflix/eureka) 服务治理的客户端
    - 配置中心
        - [x] [NB Config Server](https://gitee.com/nutz/nutzcloud-config-server) 配置中心的服务端
        - [x] starter-config-client NB Config Client 配置中心的客户端
        - [x] starter-[apollo-client](https://github.com/ctripcorp/apollo) 携程框架部门研发的分布式配置中心的客户端
        - [x] starter-[nacos-config](https://github.com/alibaba/nacos) 阿里出品的配置服务
    - API网关
        - [x] gateway-server NC API网关服务器
        - [ ] zuul
- 数据库类相关
    - 关系型数据库
        - 数据源
            - [x] **starter-jdbc, 普通连接池,默认使用druid,带监控功能**
            - [x] starter-[sharding-jdbc](https://github.com/shardingjdbc/sharding-jdbc) 分库分表
        - ORM
            - [x] **starter-[nutz-dao](https://github.com/nutzam/nutz) Nutz官方Dao**
            - [x] starter-[beetlsql](http://ibeetl.com/guide/#beetlsql) 基于Beetl的SQL框架
            - [x] starter-[sqlXmlTpl](http://github.com/threefish) 解决Java拼接SQL(采用xml管理sql)
    - 非关系型数据库
        - [x] **starter-[redis](https://redis.io) 特点就是快,吃内存!**
        - [x] starter-mongodb NoSQL的重要一支
        - [x] starter-ssdb by [道坤](https://github.com/albinhdk)
        - [x] starter-elasticsearch by [大鲨鱼](https://github.com/Wizzercn)
        - [x] starter-[redisson](https://github.com/redisson/redisson) 基于Redis的Java对象/集合/同步锁的分布式实现
        - [ ] memcached
- Mvc
    - [x] **starter-nutz-mvc Nutz自带的Mvc框架**
    - [x] starter-[tio-mvc](https://gitee.com/tywo45/t-io) 基于tio的Mvc框架
    - [ ] [jersey](https://jersey.github.io/)
- 非servlet容器
	- [x] starter-[tio](https://gitee.com/tywo45/t-io) 国产高性能网络开发包 by [蛋蛋](https://github.com/TopCoderMyDream)
	- [x] starter-[tio-websocket](https://gitee.com/tywo45/t-io) 国产高性能网络开发包 by [科技](https://github.com/Rekoe)
- 安全鉴权
    - [x] **[Shiro](http://shiro.apache.org) 应用权限的标配**
- 分布式Session
    - [x] [Shiro+LCache](https://github.com/nutzam/nutzmore/tree/master/nutz-plugins-cache)基于shiro/jedis/插件的分布式可持久化的session缓存
- 分布式事务
    - [x] [tcc-transaction](https://github.com/changmingxie/tcc-transaction/tree/dev-1.2.x)基于tcc-transaction的nutz容器支持
    - [x] [seata](https://github.com/seata/seata) 阿里开源的分布式事务引擎,原名fescar
- 计划任务
    - [x] **starter-[quartz](http://www.quartz-scheduler.org)** 大家都知道
    - [x] starter-xxl-job [国产分布式任务调度平台](https://github.com/xuxueli/xxl-job/pull/253)
    - [ ] starter-scheduledx 阿里云分布式任务
- 模板引擎
    - [x] [jst](https://gitee.com/nutz/jst) Nutz出品的模板引擎
    - [x] **starter-[beetl](http://ibeetl.com/) 闲大赋出品的高效模板引擎**
    - [x] starter-jetx [jetbrick-template](https://github.com/subchen/jetbrick-template-2x)
    - [x] starter-velocity by [haoqoo](https://github.com/haoqoo)
    - [x] starter-thymeleaf by [温泉](https://github.com/ywjno)
    - [x] starter-freemarker by [蛋蛋](https://github.com/TopCoderMyDream)
- 消息队列
    - [x] starter-disque redis作者的另一作品
    - [x] **starter-rabbitmq 好用的队列服务**
    - [ ] rocketmq
    - [ ] activemq
- 邮件发送
    - [x] starter-mail 基于commons-email by [threefish](https://github.com/threefish)
- 工作流
    - [x] starter-[uflo](https://github.com/youseries/uflo) 中式工作流引擎
    - [x] starter-[activiti](https://www.activiti.org/)
- 规则引擎
    - [x] starter-[urule](https://github.com/youseries/urule) 中式规则引擎
    - [ ] drools
- 报表系统
    - [x] starter-ureport 中式报表
    - [ ] jreport
- 日志系统
    - [x] starter-logback-exts by [大鲨鱼](https://github.com/Wizzercn)
- 文件系统
    - [x] starter-ftp by [大鲨鱼](https://github.com/Wizzercn)
    - [x] starter-fastdfs by [大鲨鱼](https://github.com/Wizzercn)
- 开放平台
    - 微信公众号开放平台
        - [x] starter-[nutzwx](https://github.com/nutzam/nutzwx) Weixin Api By Nutz
        - [ ] [weixin-java-tools](https://gitee.com/binary/weixin-java-tools)
- 物联网(IoT)
	- [x] starter-[mqtt-client](https://github.com/eclipse/paho.mqtt.java) 消息队列遥测传输, IoT 通信的标准
- 云平台
    - [ ] [阿里云](https://aliyun.com)
    - [ ] [腾讯云](https://qcloud.com)
- 缓存相关
    - [x] starter-[wkcache](https://github.com/nutzam/nutzmore/tree/master/nutz-plugins-wkcache) 方法缓存  by [大鲨鱼](https://github.com/Wizzercn)
    - [x] starter-[caffeine](https://github.com/ben-manes/caffeine) 方法缓存  by [幸福的旁边](https://github.com/happyday517)
    - [x] starter-j2cache 开源中国缓存框架 by [蛋蛋的忧伤](https://github.com/TopCoderMyDream)
- API文档生成器
	- [x] starter-[swagger](https://swagger.io) Most Popular API Framework
- docker相关
    - [ ] docker compose配置
    - [ ] docker file
- WebService
    - [x] starter-cxf WebService的事实标准
- 区块链
    - [x] starter-[web3j](https://github.com/web3j/web3j) 以太坊轻量级客户端API
- 单元测试
    - [x] starter-test-junit4 基于Junit4的单元测试支持库
- 其他
    - [x] starter-ngrok-client 内网穿透,轻松获取外网地址
    - [x] nutzboot-starter-prevent-duplicate-submit 一个可以防止表单重复提交的解决方案 by [threefish](https://github.com/threefish)
## 第三方starter或项目

期待您的到来,报个issue告知一下吧 ^_^

## 公共服务

* Ngrok内网穿透服务: 
	* 访问 https://nutz.cn 并登录, 查看个人主页,获取使用帮助及登录用的token
* 外网ip探查服务
	* 浏览器访问 http://ip.nutz.cn/ 可看网页版帮助
	* 在服务器执行 `curl ip.nutz.cn` 可返回其外网ip

## 授权协议

与Nutz一样, NutzBoot遵循[Apache协议](LICENSE),完全开源,文档齐全,永远免费(商用也是)
