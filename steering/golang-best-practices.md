---
title: Golang Best Practices
inclusion: fileMatch
fileMatchPattern: '*.go'
---

# Golang Best Practices

## Code Style
- Follow official Go formatting with `gofmt` or `goimports`
- Use meaningful variable and function names
- Use camelCase for unexported identifiers
- Use PascalCase for exported identifiers
- Use ALL_CAPS for constants only when part of exported API
- No line length limit (gofmt handles formatting)

## Type Safety
- Use interfaces for abstraction and testing
- Prefer composition over embedding
- Use type assertions and type switches carefully
- Leverage generics for type-safe collections (Go 1.18+)
- Use `any` instead of `interface{}` (Go 1.18+)

## Error Handling
- Handle errors explicitly, don't ignore them
- Use `errors.New()` or `fmt.Errorf()` for simple errors
- Wrap errors with context using `fmt.Errorf("context: %w", err)`
- Use custom error types for complex error handling
- Check errors immediately after function calls

## Code Organization
- Use Go modules for dependency management (`go.mod`)
- Follow standard project layout conventions
- Keep packages focused and cohesive
- Use internal packages for private code
- Organize imports: standard library, third-party, local

## Testing
- Write tests using the built-in `testing` package
- Use table-driven tests for multiple test cases
- Name test functions `TestFunctionName`
- Use `t.Helper()` in test helper functions
- Mock interfaces, not concrete types
- Run tests with minimal output: `go test -v ./...` or `go test -short`
- Filter specific tests: `go test -run TestName`

## Performance
- Use `sync.Pool` for object reuse
- Prefer slices over arrays for flexibility
- Use buffered channels appropriately
- Profile with `go tool pprof` before optimizing
- Use `strings.Builder` for efficient string building
- Leverage goroutines and channels for concurrency
