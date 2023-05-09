# upx-optimize

Optimizes the binary size using upx.

Notes:
- This action requires the UPX_ENABLED environment variable to be set to true.
- `upx` requires a lot of compute resources and runs for a long time, only use this action if you have enough resources available (public ci providers have limits).


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `ENV["UPX_ENABLED"] == "true"`

## Configuration


No configuration is required.
