# Usage - Library

You can add normalizeci as a library to your go projects.

## Installation

```bash
go get -u github.com/cidverse/normalizeci/pkg
```

## Usage

And to normalize the current environment you can call the following:

```go
normalized := normalizer.Normalize()
// optionally convert the spec struct into a map[string]string when passing it to other processes
env := ncispec.ToMap(normalized)
```

Also see: https://pkg.go.dev/github.com/cidverse/normalizeci/pkg/normalizeci
