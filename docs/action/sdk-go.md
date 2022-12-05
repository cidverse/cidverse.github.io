# SDK - Go

## Getting Started

``` go title="node-build.go"
type BuildConfig struct {
}

func BuildAction() (err error) {
    // init sdk
    sdk, err := cidsdk.NewSDK()
    if err != nil {
        return fmt.Errorf("Fatal: Failed to initialize SDK: %s", err.Error())
    }

    // query project context (current module, env, config, ...)
	cfg := BuildConfig{}
	ctx, err := sdk.ModuleAction(&cfg)
	if err != nil {
		return err
	}

    // run `yarn install` to download all dependencies
    _, err = sdk.ExecuteCommand(cidsdk.ExecuteCommandRequest{
        Command: `yarn install`,
        WorkDir: ctx.Module.ModuleDir,
    })
    if err != nil {
        return err
    }

    // run `yarn build` to build the project
    _, err = sdk.ExecuteCommand(cidsdk.ExecuteCommandRequest{
        Command: `yarn build`,
        WorkDir: ctx.Module.ModuleDir,
    })
    if err != nil {
        return err
    }

	return nil
}
```
