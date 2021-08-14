# SpringBoot HelloWorld Demo



## build.gradle

```java
plugins {
	id 'org.springframework.boot' version '2.1.6.RELEASE'   // Spring Boot Gradle插件，+ 版本号
	id 'java'   // Java插件
}

apply plugin: 'io.spring.dependency-management' // Spring的版本依赖管理插件

group = 'top.wisely'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '1.8'

repositories {  // jar包下载仓库
	mavenCentral()
}

dependencies {  // 定义本应用的链接
	implementation 'org.springframework.boot:spring-boot-starter-web'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```


## QuickStartApplication

- @SpringBootApplication注解：入口main方法，直接运行应用
- @RestController：声明一个基于Restful的web控制器
- @GetMapping("hello-world")：声明一个应用端点

```java
@SpringBootApplication
@RestController
public class QuickStartApplication {

    @GetMapping("/hello-world")
    public String helloWorld() {
        return "Hello World!!!";
    }

    public static void main(String[] args) {
        SpringApplication.run(QuickStartApplication.class, args);
    }

}
```


## application.properties

提供了对Spring Boot的默认行为进行定制的能力，支持.properties和.yml格式，如修改容器的端口号。



