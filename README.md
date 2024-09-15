## 1. Add Dependency for Navigation
Reference URL - https://developer.android.com/jetpack/androidx/releases/navigation#declaring_dependencies
```
Add dependency for Navigation in app level build.gradle.kts
dependencies {
     val nav_version = "2.7.7"
     // Navigation Library
     implementation("androidx.navigation:navigation-fragment-ktx:$nav_version")
     implementation("androidx.navigation:navigation-ui-ktx:$nav_version")
}
```

## 2. Add Safe Args
Reference URL - https://developer.android.com/jetpack/androidx/releases/navigation#safe_args
```
Add dependency for Navigation in project level build.gradle.kts
buildscript {
    repositories {
        google()
    }
    dependencies {
        val nav_version = "2.7.7"
        classpath("androidx.navigation:navigation-safe-args-gradle-plugin:$nav_version")
    }
}
```

## 3. In project level build.gradle.kts add below code
```
tasks.register<Delete>("clean") {
    delete(rootProject.buildDir)
}
```

## 4. Need to add SafeArgs plugin
Add plugin in app level build.gradle.kts add below code
```
plugins {
    id("androidx.navigation.safeargs.kotlin")
}
```

## 5. Check settings.gradle.kts if google() is added in the dependencyResolutionManagement
eg: -
```
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}
```
if google is not added in settings.gradle.kts Do the below
In project level build.gradle.kts add below code
```
allprojects {
    repositories {
        google()
    }
}
```

## 6. Add DataBinding
```
android {
     buildFeatures{
        dataBinding = true
    }
}
```

## 7. For creating Navigation Graph
```
rec -> RTClick -> New -> Android Resource File
Name - nav_graph , ResourceType - Navigation
```
































