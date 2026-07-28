# ego

`ego` is a small Go learning project for reimplementing selected standard-library concepts from scratch. The code is intentionally minimal and is meant to make package APIs and behavior easy to inspect.

## Current Packages

### `src/errors`

Contains a minimal error implementation:

- `New(text string) error` creates an error value.
- The private `errorString` type implements Go's built-in `error` interface.

### `src/context`

This package is currently a placeholder. Context behavior has not been implemented yet.

## Requirements

- Go 1.25.1 or newer, matching `go.mod`.

## Test

Run the implemented package tests from the repository root:

```bash
go test ./src/errors
```

The full `go test ./...` command will fail until `src/context/context.go` contains a Go package declaration and implementation.

## Example

The module path is `ego`, so the custom errors package can be imported as follows:

```go
package main

import (
    "fmt"

    egoerrors "ego/src/errors"
)

func main() {
    fmt.Println(egoerrors.New("something went wrong"))
}
```

## Roadmap

- Expand the custom `errors` package with wrapping and inspection helpers.
- Implement cancellation, deadlines, and value propagation in `src/context`.
- Add behavior-focused tests and examples for each package.

## License

No license has been declared yet.
