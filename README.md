# Spring Cloud Tencent

[![Build Status](https://github.com/Tencent/spring-cloud-tencent/actions/workflows/junit_test.yml/badge.svg)](https://github.com/Tencent/spring-cloud-tencent/actions/workflows/junit_test.yml)
[![Maven Central](https://img.shields.io/maven-central/v/com.tencent.cloud/spring-cloud-tencent?label=Maven%20Central)](https://search.maven.org/search?q=g:com.tencent.cloud%20AND%20a:spring-cloud-tencent)

English | [简体中文](./README-zh.md)

## Introduction

Spring Cloud Tencent contains components distributed micro-service applications need during developing phase, developers that built their key architectures based on Spring Cloud can use these components

Based on Spring Cloud Tencent, you only need a small configuration to launch Spring Cloud and micro-service's joint solutions.

## Key Features

* **Service Registration and Discovery**: Based on Spring Cloud's discovery and registration standard.
* **Service Routing and LoadBalancer**: Based on ribbon's API port, provide dynamic routing and load balancing use cases.
* **CircuitBreaker Node**: Support circuitbreaker auto-reset ability, ensure the reliability of distributed server
* **Rate Limiter**: Support rate limit of microservice and gateway, ensure the stability of backend, one can configure policies and traffic data from the control panel
* **Metadata Delivery**: Support metadata delivery between gateways and microservices.

## Components

**[Polaris](https://github.com/PolarisMesh/polaris)**：Polaris Spring Cloud operation centre, provide solutions to registration, dynamic routing, load balancing and circuitbreaker.

## How to build

* master's branch matches Spring Cloud Hoxton, support lowest at JDK 1.8.

Spring Cloud Tencent uses Maven to construct, the fastest way is to clone project to local files, then execute the following orders:

```bash
./mvnw install
```

When all the steps are finished, the project will be installed in local Maven repository.

## How to Use

### How to Introduce Dependency

Add the following configurations in dependencyManagement, then add the dependencies you need.
At the same time, you need to pay attention to the Spring Cloud version corresponding to Spring Cloud Tencent, and then the corresponding Spring Boot version.
For example, Spring Cloud Tencent's 1.0.1.Hoxton.SR9 corresponds to the Spring Cloud Hoxton version and requires Spring Boot 2.3.x.

````
    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>com.tencent.cloud</groupId>
                <artifactId>spring-cloud-tencent-dependencies</artifactId>
                <!--version number-->
                <version>${version}</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
````

 ### Starter Usage Doc
- [Spring Cloud Tencent Version Management](https://github.com/Tencent/spring-cloud-tencent/wiki/Spring-Cloud-Tencent-Version-Management)
- [Spring Cloud Tencent Discovery](https://github.com/Tencent/spring-cloud-tencent/wiki/Spring-Cloud-Tencent-Discovery-Usage-Documentation)
- [Spring Cloud Tencent Config](https://github.com/Tencent/spring-cloud-tencent/wiki/Spring-Cloud-Tencent-Config-Usage-Documentation)
- [Spring Cloud Tencent Rate Limit](https://github.com/Tencent/spring-cloud-tencent/wiki/Spring-Cloud-Tencent-Rate-Limit-Usage-Document)
- [Spring Cloud Tencent CircuitBreaker](https://github.com/Tencent/spring-cloud-tencent/wiki/Spring-Cloud-Tencent-Circuitbreaker-Usage-Document)
- [Spring Cloud Tencent Router](https://github.com/Tencent/spring-cloud-tencent/wiki/Spring-Cloud-Tencent-Router-Usage-Document)
- [Spring Cloud Tencent Metadata Transfer](https://github.com/Tencent/spring-cloud-tencent/wiki/Spring-Cloud-Tencent-Metadata-Transfer-Usage-Document)

### Version Standard

We use a version policy related to Spring Cloud's major version number.

Project version includes ```${MAJOR_VERSION}.${MINOR_VERSION}.${PATCH_VERSION}-${CORRESPONDING_MAJOR_VERSION_OF_SPRING_CLOUD}.${CORRESPONDING_MINOR_VERSION_OF_SPRING_CLOUD}-${RELEASE_TYPE}```.
```${MAJOR_VERSION}```, ```${MINOR_VERSION}```, ```${PATCH_VERSION}``` are in numbers starting from 0.
```${CORRESPONDING_MAJOR_VERSION_OF_SPRING_CLOUD}``` is the same as the major version number of Spring Cloud, like Hoxton, Greenwich. ```${CORRESPONDING_MINOR_VERSION_OF_SPRING_CLOUD}``` is the same as the major version number of Spring Cloud, like RS9.
```${RELEASE_TYPE}``` is like RELEASE or RC currently. Actually, the RELEASE version does not add a release type in the version, and the RS version will add a suffix and start from RC0.

For example: 1.2.0-Hoxton.SR9-RC0

## License
The spring-cloud-tencent is licensed under the BSD 3-Clause License. Copyright and license information can be found in the file [LICENSE](LICENSE)
