## 5. Clear way for DI

Go has 3 major libs to perform DI

1. [Wire](https://github.com/google/wire) - native Go
2. [Dig](https://github.com/uber-go/dig) - from Uber
3. [Inject](https://github.com/facebookarchive/inject) - from Facebook **not maintained anymore**

I have only tried _Wire_ which is does not operates during run-time but it's generates code based on provided definition. There is no reflection nor DI container with services you can inject when building dependency graph.
Wire can work with interfaces and because its a compile time tool you can get rid of all the problems before actually running the program.
But you need to define in wire terms each service definition in a separate non-compiled file and than new file which is used during compilation is generated. So you end up with two extra files just for DI dependencies each time you want to define DI for some service.
Also each time you want a **singleton you need to do it by hand** creating a special function with mutex (or sync package) and use it as provider for other injections.
In my opinion its altogether it's a lot of boilerplate code for such a common functionality.

###### Code samples:
* [wire DI service definition](https://github.com/gwalen/bettertomorrow/blob/master/context/employee/restapi/wire_init.go)
* [wire generated file](https://github.com/gwalen/bettertomorrow/blob/master/context/employee/restapi/wire_gen.go)


#### Conclusion

Yeah you can do DI, but I wouldn't call it seamless.
Maybe I am spoiled using Guice like libs in JVM world but in Go land they seems to be way less mature than their JVM neighbors.
