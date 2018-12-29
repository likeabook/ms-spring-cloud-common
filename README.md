# spring cloud的公共模块
eureka、config、admin(spring-boot-admin 非spring官方组件)、zuul。

## 组件之间的关系
### ms-spring-cloud-root
spring-cloud组件的parent，当前spring boot版本为 2.1.1.RELEASE，spring cloud 版本Greenwich.M1
### ms-eureka
注册中心，其他模块都注册到这里
### ms-config
配置中心，注册到ms-eureka上，依赖github https://github.com/likeabook/ms-spring-cloud-common.git 的config-resources目录
### ms-admin
微服务监控，注册到ms-eureka，引用ms-config的配置，对应config-resources/ms-admin目录下的配置
### ms-zuul
网关，注册到ms-eureka，引用ms-config的配置，对应config-resources/ms-zuul目录下的配置

#### 其他业务可参照ms-zuul模块进行开发

## 使用方法
### 启动
启动ms-eureka(EurekaApplication)  
启动ms-config(ConfigApplication)  
启动ms-admin(AdminApplication)  
启动ms-zuul(ZuulApplication)
### 验证
ms-eureka: http://localhost:8761  
ms-admin: http://localhost:8762 user:admin password:admin123

