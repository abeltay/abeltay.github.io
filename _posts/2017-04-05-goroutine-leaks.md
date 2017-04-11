---
layout: post
title:  "Goroutine Leaks"
date:   2017-04-05 23:00:00 +0800
categories: golang
---
# Go Routine leaks

https://blog.minio.io/debugging-go-routine-leaks-a1220142d32c


```
package main

import (
	"fmt"
	"runtime"
)

func main() {
	fmt.Println("Hello, playground")
	fmt.Println(runtime.NumGoroutine())
	for i := 0; i < 100; i++ {
		leakyFunc()
	}
	fmt.Println(runtime.NumGoroutine())
}

func leakyFunc() {
	ch := make(chan int)
	go func() {
		ch <- 1
	}()

	ch2 := make(chan int)
	go func() {
		ch2 <- 2
	}()

	i := <-ch2
	if i == 2 {
		return
	}

	j := <-ch
	fmt.Println(j)
}
```
https://play.golang.org/p/esP-ijjFY5

```
package main

import (
	"context"
	"fmt"
	"runtime"
	"time"
)

func main() {
	ctx, cancel := context.WithCancel(context.Background())
	fmt.Println("Hello, playground")
	fmt.Println(runtime.NumGoroutine())
	for i := 0; i < 100; i++ {
		leakyFunc(ctx)
	}
	cancel()
	time.Sleep(1000)
	fmt.Println(runtime.NumGoroutine())
}

func leakyFunc(ctx context.Context) {
	ch := make(chan int)
	go func() {
		select {
		case ch <- 1:
		case <-ctx.Done():
		}
	}()

	ch2 := make(chan int)
	go func() {
		select {
		case ch2 <- 2:
		case <-ctx.Done():
		}
	}()

	i := <-ch2
	if i == 2 {
		return
	}

	j := <-ch
	fmt.Println(j)
}
```
https://play.golang.org/p/FDp_lQXC3L
