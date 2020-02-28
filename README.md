## Adding package dependency

Added the following element to  `pom.xml`:

```xml
<dependency>
    <groupId>com.mycompany.app</groupId>
    <artifactId>my-app</artifactId>
    <version>1.0.3</version>
</dependency>  
```

## Adding package registry settings

Added the GitHub Packages feed to `settings.xml`:

```xml
  <activeProfiles>
    <activeProfile>github</activeProfile>
  </activeProfiles>

  <profiles>
    <profile>
      <id>github</id>
      <repositories>
        <repository>
          <id>github</id>
          <name>GitHub OWNER Apache Maven Packages</name>
          <url>https://maven.pkg.github.com/jcansdale-test/*</url>
        </repository>
      </repositories>
    </profile>
  </profiles>
```

Added a server configuration that gives access to public packages:

```xml
<server>
    <id>github</id>
    <!-- Public token with `read:packages` scope -->
    <username>jcansdale-robot</username>
    <password>&#x31;&#x36;&#x31;&#x39;&#x37;&#x37;&#x36;&#x63;&#x36;&#x39;&#x36;&#x30;&#x33;&#x38;&#x66;&#x35;&#x32;&#x33;&#x30;&#x39;&#x39;&#x37;&#x63;&#x30;&#x35;&#x38;&#x39;&#x33;&#x64;&#x33;&#x33;&#x39;&#x61;&#x36;&#x34;&#x30;&#x30;&#x39;&#x66;&#x66;</password>
</server>
```    

## Building the project

```
mvn package -s settings.xml
```

## Clear cached packages

```
mvn dependency:purge-local-repository -s settings.xml
```
