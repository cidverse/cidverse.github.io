# SDK - Go

## Getting Started

### Installation

``` bash
go get -u github.com/cidverse/cid-sdk-go
```

### SDK Documentation

- [github.com/cidverse/cid-sdk-go](https://github.com/cidverse/cid-sdk-go)
- [pkg.go.dev/github.com/cidverse/cid-sdk-go](https://pkg.go.dev/github.com/cidverse/cid-sdk-go)

### Example

Most of the official cid actions are built using go, you can take a look at this project for more complex examples here: [https://github.com/cidverse/cid-actions-go](https://github.com/cidverse/cid-actions-go)

!!! note "Notes"

    - actions should be packaged as cli applications and exit with a error code if execution failed for any reason

``` go title="node-build.go"
func main() {
	// init sdk
    sdk, err := cidsdk.NewSDK()
    if err != nil {
        fmt.Printf("Fatal: Failed to initialize SDK: %s", err.Error())
        os.Exit(1)
    }

    // query project context (current module, env, config, ...)
	ctx, err := sdk.ModuleAction(nil)
	if err != nil {
        fmt.Printf("Fatal: Failed to query project metadata: %s", err.Error())
        os.Exit(1)
	}

    // run `yarn build` to build the project
    _, err = sdk.ExecuteCommand(cidsdk.ExecuteCommandRequest{
        Command: `yarn build`,
        WorkDir: ctx.Module.ModuleDir,
    })
    if err != nil {
        fmt.Printf("Fatal: Command execution failed: %s", err.Error())
        os.Exit(1)
    }
}
```
