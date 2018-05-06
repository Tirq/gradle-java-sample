# gradle-java-sample
This guide walks you through using Gradle to build a simple Java project. This example is based on the Spring guides available in https://spring.io/guides/gs/gradle/. 

## 1 - Install Gradle
An easy way to install Gradle is using the installer called **SDKMAN** - available in http://sdkman.io/, by the way, this installer can be used to install and manager others interesting things, such as Java, Groovy, Maven, Kotlin... 

## 2 - Gradle file
The _build.gradle_ is the file where are the project build configurations.

Plugins: Add many pieces of information using plugins. For example, below is to configure the Java language.
```
apply plugin: 'java'  
```
MainClassName: Add the main class of the project.
```
mainClassName = 'hello.HelloWorld'
```
Repositories: Add what repository will be used to get external libraries. 

```
repositories {
    mavenCentral()
}
```
Jar: Add pieces of information on how to build the project.
```
jar {
    baseName = 'one-gradle'
    version =  '0.1.0'
}
```
Compatibility: Add informations about versions to have a better compabilities between the libraries.
```
sourceCompatibility = 1.8
targetCompatibility = 1.8
```
Dependencies: Add informations about external libraries(3rd party l) and then versions.
There are three types of dependencies:
* compile: Available during compile-time. If is a WAR file, the dependency is included in the /WEB-INF/libs folder.
* providedCompile: the dependency will be provided at runtime by a container running the code.
* testCompile: Available for running tests.

```
dependencies {
    compile "joda-time:joda-time:2.2"
    testCompile "junit:junit:4.12"
}
```

## 3 - Gradle Commands
Command to build the project.
```
gradle build
```
Command to test the project. 
```
gradle test
```
Command to run the project
```
gradle run
```
## 4 - Wrapper project with Gradle
Command to build the project including scripts to add Gradle. With this, you don't need to have Gradle installed in your system.
```
gradle wrapper
```
Command to build the wrapped project 
```
./gradlew build
```