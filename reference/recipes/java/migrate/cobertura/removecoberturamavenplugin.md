# Remove Cobertura Maven plugin

** org.openrewrite.java.migrate.cobertura.RemoveCoberturaMavenPlugin**
_This recipe will remove Cobertura, as it is not compatible with Java 11._

### Tags

* cobertura
* java11

## Source

[Github](https://github.com/openrewrite/rewrite-migrate-java), [Issue Tracker](https://github.com/openrewrite/rewrite-migrate-java/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-migrate-java/1.8.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 1.8.0


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-migrate-java:1.8.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.23.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.cobertura.RemoveCoberturaMavenPlugin")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:1.8.0")
}
```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.26.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.cobertura.RemoveCoberturaMavenPlugin</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>1.8.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipesorg.openrewrite.java.migrate.cobertura.RemoveCoberturaMavenPlugin`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Remove Maven plugin](../../../maven/removeplugin.md)
  * groupId: `org.codehaus.mojo`
  * artifactId: `cobertura-maven-plugin`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.cobertura.RemoveCoberturaMavenPlugin
displayName: Remove Cobertura Maven plugin
description: This recipe will remove Cobertura, as it is not compatible with Java 11.
tags:
  - cobertura
  - java11
recipeList:
  - org.openrewrite.maven.RemovePlugin:
      groupId: org.codehaus.mojo
      artifactId: cobertura-maven-plugin

```
{% endtab %}
{% endtabs %}