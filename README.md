# android-props
Gradle and ProGuard files for quick dependencies declaration in a new Android project

## Getting started

First, add this repository as a submodule of your repository by running the following command: 
`git submodule add https://github.com/eduardb/android-props.git props`

It is important to note that from now on, to clone the project on a new machine and have the submodule files fetched as well, you'll have to either run `git submodule init` and `git submodule update`, or to add the `--recurse-submodules` argument to the `git clone` command. To learn more about working with submodules, have a look [here](https://git-scm.com/book/en/v2/Git-Tools-Submodules).

Now that you have added the submodule, you should have the files under the `prop` directory. To start using it, first add the following line inside the `buildscript` closure in your main `build.gradle` file: `apply from: 'props/props.gradle'`. It should look someting like this: 
```gradle
buildscript {
    apply from: 'props/props.gradle'

    repositories {
        jcenter()
        google()
    }
    dependencies {
        ....
    }
}
```

To start adding dependencies and ProGuard rules defined in this project, keep reading :)

## Dependencies

Dependencies defined by this project are located in the [dependencies.gradle](https://github.com/eduardb/android-props/blob/master/dependencies.gradle) file. There are two kind of dependencies: Gradle plugins and libraries.

### Gradle Plugins

You can refer to the Gradle plugins with `gradlePlugins.*`. These plugins can be added in the `dependencies` closure inside the `buildscript` one of your main Gradle file. As a result, it could look like this: 
```gradle
buildscript {
    apply from: 'props/props.gradle'

    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath gradlePlugins.androidTools
        classpath gradlePlugins.kotlin
    }
}
```

List of plugins:
* `androidTools`
* `kotlin`

### Libraries

TBC

## ProGuard rules

TBC
