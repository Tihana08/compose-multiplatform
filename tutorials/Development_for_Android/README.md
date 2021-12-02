# Development for Android 

## What is covered

This tutorial covers topic of using Compose Multiplatform for multiplatform build that includes Android

## Intro

Compose Multiplatform doesn't contain any Android artifacts. 
Instead it references Jetpack Compose Android artifacts [published by Google](https://developer.android.com/jetpack/compose).

## Usage

Jetpack Compose interoperability is enabled on the publication level - nothing needs to be explicitly enabled. 


The easiest way to start is to use Kotlin Project Wizard with Compose Multiplatform template - one of the target platform is Android. 


To see how it could be achieved see [multiplatform template](https://github.com/JetBrains/compose-jb/tree/master/templates/multiplatform-template).


## Versioning

Compose Multiplatform 1.0.0 references Jetpack Compose 1.1.0-beta02. If you want to use higher version, you could explicitly 
add Jetpack Compose dependencies to the Android module like this

```kotlin
configurations.all {
   resolutionStrategy {
       force("androidx.compose.animation:animation:1.1.0-beta03")
   }
}
```


However please note, that Kotlin Compiler version used for Android must match.  

## Android Gradle Plugin (AGP) version

Currently, Using AGP 4.1.3 with block like
```kotlin
dependencies {
        classpath("com.android.tools.build:gradle:4.1.3")
}
```
is recommended. We're working on providing compatibility with more recent AGP versions, see [KT-49835](https://youtrack.jetbrains.com/issue/KT-49835) and 
[KT-49789](https://youtrack.jetbrains.com/issue/KT-49798).