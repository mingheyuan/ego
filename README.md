# ego

`ego` 是一个 Go 学习项目，用于从零实现部分标准库概念。代码保持简洁，便于观察包 API 和核心行为。

## 当前包

### `src/errors`

包含一个最小化的错误实现：

- `New(text string) error` 创建错误值。
- 私有类型 `errorString` 实现 Go 内置的 `error` 接口。

### `src/context`

当前仍是占位包，尚未实现 Context 行为。

## 环境要求

- Go 1.25.1 或更高版本，以 `go.mod` 为准。

## 测试

运行当前已经实现的包测试：

```bash
go test ./src/errors
```

在 `src/context/context.go` 增加有效的 Go 包声明和实现前，完整的 `go test ./...` 会失败。

## 使用示例

模块路径是 `ego`，自定义 errors 包可以这样导入：

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

## 后续计划

- 为自定义 `errors` 包增加包装和错误检查能力。
- 在 `src/context` 中实现取消、截止时间和值传递。
- 为每个包增加以行为为中心的测试和示例。

## 许可证

仓库当前没有声明许可证。
