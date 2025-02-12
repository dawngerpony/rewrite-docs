# Migrate deprecated `javax.annotation` packages to `jakarta.annotation`

**org.openrewrite.java.migrate.jakarta.JavaxAnnotationPackageToJakarta**

_Change type of classes in the `javax.annotation` package to jakarta._

### Tags

* javax
* batch
* jakarta

## Source

[GitHub](https://github.com/openrewrite/rewrite-migrate-java/blob/main/src/main/resources/META-INF/rewrite/jakarta-ee-9.yml), [Issue Tracker](https://github.com/openrewrite/rewrite-migrate-java/issues), [Maven Central](https://central.sonatype.com/artifact/org.openrewrite.recipe/rewrite-migrate-java/2.1.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 2.1.0


## Usage

This recipe has no required configuration options. It can be activated by adding a dependency on `org.openrewrite.recipe:rewrite-migrate-java:2.1.0` in your build file or by running a shell command (in which case no build changes are needed): 
{% tabs %}
{% tab title="Gradle" %}
1. Add the following to your `build.gradle` file:
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("6.3.6")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.jakarta.JavaxAnnotationPackageToJakarta")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:2.1.0")
}
```
{% endcode %}
2. Run `gradle rewriteRun` to run the recipe.
{% endtab %}

{% tab title="Gradle init script" %}
1. Create a file named `init.gradle` in the root of your project.
{% code title="init.gradle" %}
```groovy
initscript {
    repositories {
        maven { url "https://plugins.gradle.org/m2" }
    }
    dependencies { classpath("org.openrewrite:plugin:6.3.6") }
}
rootProject {
    plugins.apply(org.openrewrite.gradle.RewritePlugin)
    dependencies {
        rewrite("org.openrewrite.recipe:rewrite-migrate-java:2.1.0")
    }
    rewrite {
        activeRecipe("org.openrewrite.java.migrate.jakarta.JavaxAnnotationPackageToJakarta")
    }
    afterEvaluate {
        if (repositories.isEmpty()) {
            repositories {
                mavenCentral()
            }
        }
    }
}
```
{% endcode %}
2. Run `gradle --init-script init.gradle rewriteRun` to run the recipe.
{% endtab %}
{% tab title="Maven POM" %}
1. Add the following to your `pom.xml` file:
{% code title="pom.xml" %}
```xml
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.5.2</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.jakarta.JavaxAnnotationPackageToJakarta</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>2.1.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
2. Run `mvn rewrite:run` to run the recipe.
{% endtab %}

{% tab title="Maven Command Line" %}
{% code title="shell" %}
You will need to have [Maven](https://maven.apache.org/download.cgi) installed on your machine before you can run the following command.

```shell
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run \
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-migrate-java:RELEASE \
  -Drewrite.activeRecipes=org.openrewrite.java.migrate.jakarta.JavaxAnnotationPackageToJakarta
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.Generated`
  * newFullyQualifiedTypeName: `jakarta.annotation.Generated`
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.ManagedBean`
  * newFullyQualifiedTypeName: `jakarta.annotation.ManagedBean`
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.Nonnull`
  * newFullyQualifiedTypeName: `jakarta.annotation.Nonnull`
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.Nullable`
  * newFullyQualifiedTypeName: `jakarta.annotation.Nullable`
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.PostConstruct`
  * newFullyQualifiedTypeName: `jakarta.annotation.PostConstruct`
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.PreDestroy`
  * newFullyQualifiedTypeName: `jakarta.annotation.PreDestroy`
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.Priority`
  * newFullyQualifiedTypeName: `jakarta.annotation.Priority`
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.Resource`
  * newFullyQualifiedTypeName: `jakarta.annotation.Resource`
* [Change type](../../../java/changetype.md)
  * oldFullyQualifiedTypeName: `javax.annotation.Resources`
  * newFullyQualifiedTypeName: `jakarta.annotation.Resources`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.jakarta.JavaxAnnotationPackageToJakarta
displayName: Migrate deprecated `javax.annotation` packages to `jakarta.annotation`
description: Change type of classes in the `javax.annotation` package to jakarta.
tags:
  - javax
  - batch
  - jakarta
recipeList:
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.Generated
      newFullyQualifiedTypeName: jakarta.annotation.Generated
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.ManagedBean
      newFullyQualifiedTypeName: jakarta.annotation.ManagedBean
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.Nonnull
      newFullyQualifiedTypeName: jakarta.annotation.Nonnull
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.Nullable
      newFullyQualifiedTypeName: jakarta.annotation.Nullable
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.PostConstruct
      newFullyQualifiedTypeName: jakarta.annotation.PostConstruct
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.PreDestroy
      newFullyQualifiedTypeName: jakarta.annotation.PreDestroy
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.Priority
      newFullyQualifiedTypeName: jakarta.annotation.Priority
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.Resource
      newFullyQualifiedTypeName: jakarta.annotation.Resource
  - org.openrewrite.java.ChangeType:
      oldFullyQualifiedTypeName: javax.annotation.Resources
      newFullyQualifiedTypeName: jakarta.annotation.Resources

```
{% endtab %}
{% endtabs %}

## See how this recipe works across multiple open-source repositories

[![Moderne Link Image](/.gitbook/assets/ModerneRecipeButton.png)](https://app.moderne.io/recipes/org.openrewrite.java.migrate.jakarta.JavaxAnnotationPackageToJakarta)

The community edition of the Moderne platform enables you to easily run recipes across thousands of open-source repositories.

Please [contact Moderne](https://moderne.io/product) for more information about safely running the recipes on your own codebase in a private SaaS.
