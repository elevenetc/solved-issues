# Problem 1: Importing android modules from file system
## Errors
```
ERROR: Unable to resolve dependency for ':app@debugUnitTest/compileClasspath': Could not resolve project :library.
```
## Solution
Replace

```
include ':library'
project(':library').projectDir = new File('/dir/to/proj')
```
With specified module

```
include ':library'
project(':library').projectDir = new File('/dir/to/proj/library')
```
And add dependencies if needed to root project

```
buildscript {
  dependencies {
    classpath "org.jetbrains.dokka:dokka-gradle-plugin:0.10.1"
  }
}

```

## Links
- [https://stackoverflow.com/questions/24658422/android-studio-creating-modules-without-copying-files](https://stackoverflow.com/questions/24658422/android-studio-creating-modules-without-copying-files)