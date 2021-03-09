# hello-fun template repo

This template repo provides a simple Hello web app based on Spring Boot and Spring Cloud Function.

It can be deployed as a standalone web app, as a Kubernetes Deployment and Service, or as a Knative Service.

## The code

> **NOTE**: The project is configured for Java 11, if you are using Java 8, then modify the `java.version` property in `pom.xml`.

The project contains the following:

```text
.
├── README.md
├── knative-logo.jpg
├── mvnw
├── mvnw.cmd
├── pom.xml
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── example
    │   │           └── hello
    │   │               └── HelloFunApplication.java
    │   └── resources
    │       └── application.properties
    └── test
        └── java
            └── com
                └── example
                    └── hello
                        └── HelloFunApplicationTests.java

12 directories, 8 files
```

You can modify the source code using [Visual Studio Code](https://code.visualstudio.com/):

```bash
code .
```

The Function that is used by this app is located at `src/main/java/com/example/helloapp/HelloFunApplication.java`

You can build the project using the provided Maven wrapper:

```bash
./mvnw clean package
```

## Standalone app with embedded Netty HTTP server

To run the app using the embedded server you can run this command:

```bash
./mvnw spring-boot:run
```

You can then access the function using `curl`:

```bash
curl -w'\n' -H 'Content-Type: text/plain' localhost:8080 -d "Fun"
```

## Kubernetes Deployment and Service

<img src="https://kubernetes.io/images/kubernetes-horizontal-color.png"
     alt="Kubernetes" width="400" />

You can containerize this template app and deploy it as a Deployment and Service on Kubernetes.
See the [Spring Boot Kubernetes](https://spring.io/guides/gs/spring-boot-kubernetes/) Guide for details.

## Knative Service

<img src="https://avatars3.githubusercontent.com/u/35583233?s=280&v=4"
     alt="Knative" width="100" />

You can containerize this template app and deploy it as a Knative Service.
See the [Hello World - Spring Boot Java](https://knative.dev/docs/serving/samples/hello-world/helloworld-java-spring/) sample for details.
