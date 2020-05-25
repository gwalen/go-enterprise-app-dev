## Clear error handling

In Go errors are values. There is no concept of exception (although there are panic/recover functions about which I will write later).
Most common pattern is to pass an error value (or nil if operation was successful) to the caller function. Than you either log it and handle as you need or propagate up in the call stack again with return statement. Errors can wrap other errors, so you can add extra info to given error value.
You can create own type of errors, your struct just need to implement error interface.

This most basic error definition error must implement:
```
type error interface {
    Error() string
}
```

##### But what about stack trace ?

If you come from JVM world this question will arise for sure.
Basic error interface does not have this idea implemented. In Go errors are values, so it's up to you what your error structure contains.
If you need a stack-trace u can use for example: [pkg/errors](https://github.com/pkg/errors). When you create a new error `errors.New("error")` stack trace is automatically added.

Other option is to use errors without stack trace and relay on `panic()` and `recover()` functions. You can use `panic` for bugs and value errors is for actionable failures.
When you call `panic` it is similar to throwing and an Exception in JVM language. It is propagated and crashes the app with full stack trace printed or you can catch and handle it with `recover`

There is no silver bullet here, you must choose which option best fit your needs.

Different options and opinions can be found on this [reddit post](https://www.reddit.com/r/golang/comments/gdq6f4/why_githubcompkgerrors_is_not_a_golden_standard/).
