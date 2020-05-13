#### Concurrency as first class citizen

Goroutines are core of concurrency in Go. Goroutines are like light weight treads (? READM more).
They don't map one to one to os threads. There can be thousands of go routines (they cost couple KB on stack - how much exactly ?)

When you create a Goroutine it is a independent concurrent process from its parent. You need a pipe to communicate between Goroutine which in go is called channel.
Channels can be buffered or unbuffered.

This is a powerful abstraction that allows building efficient concurrent data flows.

**But there is no free lunch**

Writing and reading from a channel is blocking. Which can create deadlocks (luckily go has tools to detect them).
When Go routines panic, error will not be returned in the parent Go routine but it will crash the application. So you have to create workarounds that will wrap the go routine invocation and allow recovery from the error ([gh link](https://github.com/golang/go/issues/20161)) without crashing the whole application.
You also have to watch for go routines than could became zombie when they are waiting for data on the channel to which nobody is writing anymore (ex.: writing Go routine had an error)

###### Code samples :
* [worker pool implementation](https://github.com/gwalen/bettertomorrow/tree/master/common/util/concurrency/worker_pool.go)
* [worker pool usage](https://github.com/gwalen/bettertomorrow/blob/master/context/customer/application/customer_wallet_service.go)
* [safe Go routine with panic recovery](https://github.com/gwalen/bettertomorrow/blob/master/common/util/concurrency/safe_goroutine.go)

###### Here are some useful links :
* https://golangbot.com/goroutines/
* https://golangbot.com/channels/
* https://golangbot.com/buffered-channels-worker-pools/
* (catching errors in subroutines) https://github.com/golang/go/issues/20161

#### Conclusion

Go definitely has mad concurrency a first class citizen. It's different model in other languages and everybody should take a look at it.
