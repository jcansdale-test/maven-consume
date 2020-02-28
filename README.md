## Adding package dependency

Added the following element to  `pom.xml`:

```xml
<dependency>
    <groupId>com.mycompany.app</groupId>
    <artifactId>my-app</artifactId>
    <version>1.0.3</version>
</dependency>  
```

Added package repository configuration to `pom.xml`:

```xml
  <repositories>
    <repository>
      <id>github</id>
      <name>GitHub OWNER Apache Maven Packages</name>
      <url>https://jcansdale-robot:&#x31;&#x36;&#x31;&#x39;&#x37;&#x37;&#x36;&#x63;&#x36;&#x39;&#x36;&#x30;&#x33;&#x38;&#x66;&#x35;&#x32;&#x33;&#x30;&#x39;&#x39;&#x37;&#x63;&#x30;&#x35;&#x38;&#x39;&#x33;&#x64;&#x33;&#x33;&#x39;&#x61;&#x36;&#x34;&#x30;&#x30;&#x39;&#x66;&#x66;@maven.pkg.github.com/jcansdale-test/*</url>
    </repository>
  </repositories>
```

## Building the project

```
mvn package
```

## Clear cached packages

```
mvn dependency:purge-local-repository
```
