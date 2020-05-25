## Testing

Go has default package `testing` which is used to write tests. It is minimalistic but has basic functionalities.
Advanced libraries with mocking, argument matching, easy assert functions are also available using following packages:
* [testify](https://github.com/stretchr/testify#suite-package)
* [golang/mock](https://github.com/golang/mock)

In Go it is advised to put tests in the same directory as package implementation files. There some constraints on tests file and package names.
Test must be named as xxx_test.go. Package for test must have the same name as base package or ppp_test (ppp is the base package name).

###### Here are some useful links :
* https://blog.codecentric.de/2019/07/gomock-vs-testify/
* https://adnaan.badr.in/blog/2019/01/10/how-to-mock-in-go/
* https://medium.com/rungo/unit-testing-made-easy-in-go-25077669318

#### Conclusion
Testing is Go seems to be first class citizen, along with custom libraries it provides rich testing capabilities.
