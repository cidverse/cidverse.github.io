# SDK - Kotlin

## Getting Started

### Installation

=== "Gralde - Kotlin DSL"

    ``` kotlin
    implementation("io.github.cidverse:cid-sdk-java:0.0.3")
    ```

=== "Gralde - Groovy DSL"

    ``` groovy
    implementation 'io.github.cidverse:cid-sdk-java:0.0.3'
    ```

=== "Maven"

    ``` xml
    <dependency>
        <groupId>io.github.cidverse</groupId>
        <artifactId>cid-sdk-java</artifactId>
        <version>0.0.3</version>
    </dependency>
    ```

### SDK Documentation

- [github.com/cidverse/cid-sdk-java](https://github.com/cidverse/cid-sdk-java)
- [javadoc.io/doc/io.github.cidverse/cid-sdk-java](https://javadoc.io/doc/io.github.cidverse/cid-sdk-java/latest/io/github/cidverse/cid/sdk/CIDSDK.html)

### Example

!!! note "Notes"

    - actions should be packaged as cli applications and exit with a error code if execution failed for any reason

``` kotlin title="Main.kt"
import kotlin.system.exitProcess

fun main(args: Array<String>) {
    val sdk = CIDSDK()
    var config = sdk.config()
    var module = sdk.module()

    var installResult = sdk.executeCommand(command = "yarn build", workDir = module.moduleDir)
    if (installResult.code != 0) {
        println("yarn build failed: ${installResult.error}")
        exitProcess(1)
    }
}
```
