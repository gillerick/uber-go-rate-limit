# Uber Go rate limiter

### Learnings

#### 1. Golang Functional Options/Default Configuration Values [Pattern](https://www.youtube.com/watch?v=fe8vJSIzWss)

```go
func buildConfig(opts []Option) config {
	c := config{
		clock: clock.New(),
		slack: 10,
		per:   time.Second,
	}

	for _, opt := range opts {
		opt.apply(&c)
	}
	return c
}
```