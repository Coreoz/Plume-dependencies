Plume Dependencies
==================

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.coreoz/plume-dependencies/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.coreoz/plume-dependencies)

Plume Dependencies fixed all maven dependencies that are used in the Plume ecosystem:
- [Plume Framework](https://github.com/Coreoz/Plume): the lightweight modular Java framework
- [Plume Admin](https://github.com/Coreoz/Plume-admin): provides Jersey web services to build an administration area
- [Plume File](https://github.com/Coreoz/Plume-file): a group of modules to manage files

This Maven import feature enables:
- to resolve maven conflicts: there will not be a dependency that bring an old version of Jackson that will break Swagger
- to facilitate the integration of a Plume module: there is no need to specify Plume dependencies versions:
```xml
<dependency>
  <groupId>com.coreoz</groupId>
  <artifactId>plume-conf</artifactId>
</dependency>
```

This project provides a POM file that should be imported in the maven project file when using Plume Framework.
The pom.xml should contains something like:
```xml
<project>
  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <maven.compiler.source>1.8</maven.compiler.source>
    <maven.compiler.target>1.8</maven.compiler.target>

    <plume.version>2.0.1</plume.version>
  </properties>

  <!-- The POM import of Plume Dependencies -->
  <dependencyManagement>
    <dependencies>
      <dependency>
        <groupId>com.coreoz</groupId>
        <artifactId>plume-dependencies</artifactId>
        <version>${plume.version}</version>
        <scope>import</scope>
        <type>pom</type>
      </dependency>
    </dependencies>
  </dependencyManagement>
</project>
```

