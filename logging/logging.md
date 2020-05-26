## Efficient and easy to use logging

Here I found several competitors: stdlib, logrus, go-kit, log15, zap, zero logger and others.
What I expect of of a logger is
- be fast (I've seen apps when performance was degraded by slow/blocking logging)
- log in structured json format for prod use and pretty console style for local development
- be able to log stack traces of the errors
- have a decent documentation

I read about all of them and chose to check the most popular (according to github) and the fastest.

#### [Logrus](https://github.com/sirupsen/logrus)
Has most stars on GitHub and is on the scene for a long time.
It has pretty good documentation and lot of posts on stack-overflow when you don't know how do something.
&nbsp; It can log in json and pretty console format.

It is not the fastest one and I have seen people reporting locking issues during write  - [link to reddit](https://www.reddit.com/r/golang/comments/6irpt1/is_there_a_golang_logging_library_around_that/)

There is no OOTB way of logging stack traces, you need to add it manually - it's not difficult but still pretty basic thing. Here is the link to solution [link to stack-overflow](https://stackoverflow.com/questions/54369295/how-to-get-logrus-to-print-stack-of-pkg-errors)

Also on github web page we can read that no new features will be added and project is in maintenance mode.

#### [Zap logger](https://github.com/uber-go/zap)

Offers reflection-free, zero-allocation JSON encoder and according to benchmarks along with zero logger is the fastest Go logger lib. It was created by Uber team so for sure it is production ready.
It allows structured json logging and pretty console logging.

Docs are far from perfect. There is a godoc but not enough examples.

###### Code samples:
* [logger creation and simple facade](https://github.com/gwalen/bettertomorrow/blob/master/common/logger/logger_zap.go)

#### [Zero logger](https://github.com/rs/zerolog)

Based on similar idea as Zap, also blazing fast.
Can log in json as well as in pretty console format.
Great thing is that logging error stack trace is quite intuitive which I find a great advantage over its competitors (it's also compatible with `github.com/pkg/errors`) - but you can easily override stack trace marshaller if you are using other error structure.

Documentation has a lot of examples which makes using zero logger much easier.

###### Code samples:
* [logger creation and simple facade](https://github.com/gwalen/bettertomorrow/blob/master/common/logger/logger_zero.go)

#### Conclusion

Go has a wide variety of logger libraries to choose from, which are enterprise ready.
My personal favorite logger is zero thanks to docs and easy to use api, and ofcourse its speed.
