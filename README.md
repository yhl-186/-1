# Read Me First

The following was discovered as part of building this project:

* The JVM level was changed from '1.8' to '17', review
  the [JDK Version Range](https://github.com/spring-projects/spring-framework/wiki/Spring-Framework-Versions#jdk-version-range)
  on the wiki for more details.

# Getting Started

### Reference Documentation

For further reference, please consider the following sections:

* [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
* [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.0.0/maven-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.0.0/maven-plugin/reference/html/#build-image)
* [GraalVM Native Image Support](https://docs.spring.io/spring-boot/docs/3.0.0/reference/html/native-image.html#native-image)
* [Spring Configuration Processor](https://docs.spring.io/spring-boot/docs/3.0.0/reference/htmlsingle/#appendix.configuration-metadata.annotation-processor)
* [Spring Boot DevTools](https://docs.spring.io/spring-boot/docs/3.0.0/reference/htmlsingle/#using.devtools)

### Additional Links

These additional references should also help you:

* [Configure AOT settings in Build Plugin[HELP.md](https://github.com/yhl-186/-1/files/13785506/HELP.md)
](https://docs.spring.io/spring-boot/docs/3.0.0/maven-plugin/reference/htmlsingle/#aot)

## GraalVM Native Support

This project has been configured to let you generate either a lightweight container or a native executable.
It is also possible to run your tests in a native image.

### Lightweight Container with Cloud Native Buildpacks

If you're already familiar with Spring Boot container images support, this is the easiest way to get started.
Docker should be installed and configured on your machine prior to creating the image.

To create the image, run the following goal:

```
$ ./mvnw spring-boot:build-image -Pnative
```

Then, you can run the app like any other container:

```
$ docker run --rm xhl:0.0.1-SNAPSHOT
```

### Executable with Native Build Tools

Use this option if you want to explore more options such as running your tests in a native image.
The GraalVM `native-image` compiler should be installed and configured on your machine.

NOTE: GraalVM 22.3+ is required.

To create the executable, run the following goal:

```
$ ./mvnw native:compile -Pnative
```

Then, you can run the app as follows:

```
$ target/xhl
```

You can also run your existing tests suite in a native image.
This is an efficient way to validate the compatibility of your application.

To run your existing tests in a native image, run the following goal:
$ ./mvnw test -PnativeTest
