# Maven 

Maven nos permite la construccion de un arquetipo, esto nos es muy util ya que una vez que concebimos una arquitectura
repetitiva optimizaremos con ello la reutilizacion no de codigo, si no de la modularidad de los proyectos.



Nos movemos al directorio examples/ y ahí con linea de comando corremos:

     mvn archetype:create-from-project -Darchetype.filteredExtensions=java

Luego nos movemos a la carpeta target que tiene la estructura de este arquetipo

    cd target/generated-sources/archetype/

Tendremos algo así:

```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>mx.certificatic.practicas</groupId>
    <artifactId>archetype-certificatic-archetype</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>maven-archetype</packaging>
    <name>archetype-certificatic-archetype</name>
    <build>
    <extensions>
      <extension>
        <groupId>org.apache.maven.archetype</groupId>
        <artifactId>archetype-packaging</artifactId>
        <version>2.2</version>
      </extension>
    </extensions>
    <pluginManagement>
      <plugins>
        <plugin>
          <artifactId>maven-archetype-plugin</artifactId>
          <version>2.2</version>
        </plugin>
      </plugins>
    </pluginManagement>
    </build>
    </project>
```

Luego corremos:

     mvn install

Listo, nos movemos a la carpeta CursoEJB/02-JavaEE/practices/practice1  y creamos nuestra practica apartir de este nuevo arquetipo que acabamos de crear:

    mvn archetype:generate -DarchetypeCatalog=local


![](http://snag.gy/v6UUS.jpg)

Nos da las opciones que podemos tomar de nuestro repositorio

    [INFO] No archetype defined. Using maven-archetype-quickstart (org.apache.maven.archetypes:maven-archetype-quickstart:1.0)
    Choose archetype:
    1: local -> mx.certificatic.practicas:archetype-certificatic-archetype (archetype-certificatic-archetype)
    Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): :

Damos en opcion 1:

    Define value for property 'groupId': : mx.certificatic.practicas
    Define value for property 'artifactId': : practica-maven
    Define value for property 'version':  1.0-SNAPSHOT: :
    Define value for property 'package':  mx.certificatic.practicas: :mx.certificatic.practicas.maven
    Confirm properties configuration:
    groupId: mx.certificatic.practicas
    artifactId: practica-maven
    version: 1.0-SNAPSHOT
    package: mx.certificatic.practicas.maven
    Y: :

Esta listo para importarlo y trabajar

![](http://snag.gy/cT2ah.jpg)


###Agregar Testing sources

Vamos a agregar carpetas de recursos a nuestro proyecto de tal manera que quede asi:

![](http://snag.gy/QOQ44.jpg)


Agregamos el Application Server y realizamos el deploy:

![](http://snag.gy/2f77d.jpg)


#No olvides dar commit y push a tus cambios.
