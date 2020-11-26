###Initial teps:
- blade init -v 7.3 LPS-117485
- cd LPS-117485
- ./gradlew build 

(all normal)

###Add the dependency management plugin

Add to gradle.build:
```
buildscript {
    repositories {
        maven { url 'https://repo.spring.io/plugins-snapshot' }
    }
    dependencies {
        classpath 'io.spring.gradle:dependency-management-plugin:1.0.7.BUILD-SNAPSHOT'
    }
}

apply plugin: "io.spring.dependency-management"
```

### Build
- ./gradlew build 

```
* What went wrong:
A problem occurred evaluating root project 'LPS-117485-demo'.
> Failed to apply plugin [id 'io.spring.dependency-management']
   > Cannot add task 'dependencyManagement' as a task with that name already exists.
``` 

- Remove liferay.workspace.product
- ./gradlew build

```
> Configure project :
The property `liferay.workspace.product` has not been set. It is recommended to set this property in gradle.properties in the workspace directory. See LPS-111700.
```
