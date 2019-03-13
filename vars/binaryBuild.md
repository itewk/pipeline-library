# binaryBuild

This trigger binary build if pointed to BuildConfig with binary -strategy.

Sample usages:

Assumes that artifacts are in directory called "deploy":
```
stage {
    steps{
        binaryBuild(projectName: "example", buildConfigName: "hello-world-build")
    }
}
```
Defined your own artifacts directory:
```
stage {
    steps{
        binaryBuild(projectName: "example", buildConfigName: "hello-world-build", artifactsDirectoryName: "artifacts", buildFrom "--from-dir")
    }
}
```

Include this library by adding this before "pipeline" in your Jenkins:
```
library identifier: "pipeline-library@master", retriever: modernSCM(
  [$class: "GitSCMSource",
   remote: "https://github.com/redhat-cop/pipeline-library.git"])
```
