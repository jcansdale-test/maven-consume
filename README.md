## Adding package dependency

Added the following element to  `pom.xml`:

```xml
<dependency>
    <groupId>com.mycompany.app</groupId>
    <artifactId>my-app</artifactId>
    <version>1.0.3</version>
</dependency>  
```

Create a `settings.xml` file for this repository:

I'm including an XML encoded token because I don't want it be automatically deleted by GitHub when it appears on a public repository. The token is a PAT with the `read:packages` scope from an account that doesn't own any private packages and is therefore safe to share.

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                      http://maven.apache.org/xsd/settings-1.0.0.xsd">
  <servers>
    <server>
      <id>github</id>
      <username>jcansdale-robot</username>
      <!-- Public token with `read:packages` scope -->
      <password>&#50;&#57;&#100;&#55;&#50;&#97;&#49;&#98;&#53;&#54;&#50;&#55;&#48;&#101;&#54;&#97;&#99;&#101;&#53;&#51;&#49;&#55;&#102;&#102;&#49;&#98;&#52;&#52;&#52;&#50;&#97;&#54;&#99;&#51;&#99;&#101;&#100;&#57;&#101;&#100;</password>
    </server>
  </servers>
</settings>
```

If you have Docker installed, you can XML encode a `read:packages` scoped token like this:

```
docker run jcansdale/gpr encode TOKEN
```

Add `.mvn/maven.config` to use local settings file by default:

```
-s settings.xml
```

## Building the project

```
mvn package
```

## Clear cached packages

```
mvn dependency:purge-local-repository
```
