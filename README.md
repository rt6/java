# JAVA

### Building runnable JAR Packages with IntelliJ from Maven project
---

1. Build `jar` package in IntelliJ

  1. Select File menu > Project Structure > Artifacts > Hit the "+" button to create new artifact

  1. Select JAR and select from modules with dependencies
  
  1. Select Module and Main Class and press "OK" button
  
  1. Press "OK" on the next window and take note of the output directory.
  
  1. Select Build menu > Build Artifacts to build jar package to the output directory
  
  1. Note: that the manifest.mf file should be stored in `src/main/resource` instead of `src/main/java`

2. Test that you can run the jar in the command line
```sh
$ java -cp my-package.jar <ClassPathContainingMainMethod> <args>

# for example
$ java-cp my-package.jar <MainClass>

```
