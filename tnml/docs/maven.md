# Maven
The New Menu Library uses maven for dependency management. The versions on this page may not be fully
up to date, please use the CI with the badge below to ensure you're using the latest version.

[![Build Status](https://ci.codemc.io/job/creatorfromhell/job/TheNewMenuLibrary/badge/icon)](https://ci.codemc.io/job/creatorfromhell/job/TheNewMenuLibrary/)

Repository:
```XML
<repository>
    <id>codemc-releases</id>
    <url>https://repo.codemc.io/repository/maven-public/</url>
</repository>
```

Core Dependency:
```XML
<dependency>
    <groupId>net.tnemc</groupId>
    <artifactId>TNML-CORE</artifactId>
    <version>1.5.0.0-SNAPSHOT-3</version>
    <scope>compile</scope>
</dependency>
```

Bukkit Dependency:
```XML
<dependency>
    <groupId>net.tnemc</groupId>
    <artifactId>TNML-Bukkit</artifactId>
    <version>1.5.0.0-SNAPSHOT-3</version>
    <scope>compile</scope>
</dependency>
```

Folia Dependency:
```XML
<dependency>
    <groupId>net.tnemc</groupId>
    <artifactId>TNML-Folia</artifactId>
    <version>1.5.0.0-SNAPSHOT-3</version>
    <scope>compile</scope>
</dependency>
```

Sponge API Version 7 Dependency:

```XML
<dependency>
    <groupId>net.tnemc</groupId>
    <artifactId>TNML-Sponge-API-7</artifactId>
    <version>1.5.0.0-SNAPSHOT-3</version>
    <scope>compile</scope>
</dependency>
```

Sponge API Version 8+ Dependency:

*Currently not supported because lack of documentation on Sponge's End*

```XML
<dependency>
    <groupId>net.tnemc</groupId>
    <artifactId>TNML-Sponge-API-8</artifactId>
    <version>1.5.0.0-SNAPSHOT-3</version>
    <scope>compile</scope>
</dependency>
```