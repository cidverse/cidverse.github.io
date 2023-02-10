# SDK - Java

## Getting Started

### Installation

=== "Gralde - Kotlin DSL"

    ``` kotlin
    implementation("io.github.cidverse:cid-sdk-java:0.0.4")
    ```

=== "Gralde - Groovy DSL"

    ``` groovy
    implementation 'io.github.cidverse:cid-sdk-java:0.0.4'
    ```

=== "Maven"

    ``` xml
    <dependency>
        <groupId>io.github.cidverse</groupId>
        <artifactId>cid-sdk-java</artifactId>
        <version>0.0.4</version>
    </dependency>
    ```

### SDK Documentation

- [github.com/cidverse/cid-sdk-java](https://github.com/cidverse/cid-sdk-java)
- [javadoc.io/doc/io.github.cidverse/cid-sdk-java](https://javadoc.io/doc/io.github.cidverse/cid-sdk-java/latest/io/github/cidverse/cid/sdk/CIDSDK.html)

### Example

!!! note "Notes"

    - actions should be packaged as cli applications and exit with a error code if execution failed for any reason

``` java title="Main.java"
public class Main {
    public static void main(String[] args) {
        CIDSDK sdk = new CIDSDK();
        var config = sdk.config();
        var module = sdk.module();

        var installResult = sdk.executeCommand("yarn build", false, module.getModuleDir(), Collections.emptyMap());
        if (installResult.getCode() != 0) {
            System.out.println("yarn build failed: " + installResult.getError());
            System.exit(1);
        }
    }
}
```
