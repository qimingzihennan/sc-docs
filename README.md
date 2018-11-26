# sc-docs

## Introduction

sc-docs is a [swagger](https://swagger.io/specification/v2/) tools that can be generated according to the [Java docs specification](https://docs.oracle.com/javase/1.5.0/docs/tooldocs/windows/javadoc.html)


## Requirements

Building the library requires [Maven](https://maven.apache.org/) and [Java8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) to be installed.


## installation

At first generate the JAR by executing:

```shell
mvn package
```

Then manually install the following JARs:

* target/sc-docs.jar


## Getting Started

Please follow the [installation](#installation) instruction and execute the following shell code:

```shell
java -jar ./target/sc-docs.jar -i project -o ./docs
```

## Start Server

```shell
java -jar ./target/sc-docs.jar serve ./docs
```

## Other
```
usage: java -jar ./target/sc-docs.jar  [-i <arg>] [-o <arg>] [-serve <arg>] [-t]
-i,--input <arg>    Source directory
-o,--output <arg>   Output directory
-serve <arg>        Start server
-t,--translation    Translate description
```

## Support environment variables

Name | Description
---|---
-Ddocs.**projectName**.host=localhost|swagger.json host
-Ddocs.**projectName**.basePath=/|swagger.json basePath
-Ddocs.**projectName**.scheme=http|swagger.json scheme
-Ddocs.**projectName**.info.title=demo|swagger.json info.title
-Dbaidu.appId=appId|[Baidu](http://api.fanyi.baidu.com/api/trans/product/desktop?req=developer) translation appid
-Dbaidu.securityKey=securityKey|[Baidu](http://api.fanyi.baidu.com/api/trans/product/desktop?req=developer) translation securityKey

## Using the environment example

```shell
java -Ddocs.projectName.host=localhost:8080 -Ddocs.projectName.scheme=http -Ddocs.projectName.info.title=demo -Dbaidu.appId=appid -Dbaidu.securityKey=securityKey  -jar ./target/sc-docs.jar -i sourceDirectory -o outDirectory -t
```
