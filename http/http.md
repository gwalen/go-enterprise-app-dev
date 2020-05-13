### 1. Web framework to efficiently build rest-api

There are a lot of web frameworks written in Go and many of them has really good docs, essential functionalities and have good reviews among users.

Here is quite useful page with list of frameworks with git data as number of commits stars etc. [gh link](https://github.com/mingrammer/go-web-framework-stars)

top 3 (as of 02-05-2020) are :

1. [Gin](https://github.com/gin-gonic/gin)
2. [Beego](https://beego.me/)
3. [Echo](https://github.com/labstack/echo)

In my pet project I used **Echo**. It has great documentation, easy to use api and bunch of useful features. Including: json parsing, JWT, CORS, file serving, data streaming, WebSockets, HTTP/2.

###### Code samples:
* [endpoint definition](https://github.com/gwalen/bettertomorrow/blob/master/context/employee/restapi/employee_routes.go)
* [routing](https://github.com/gwalen/bettertomorrow/blob/master/route/routes.go)

###### Here are some useful links :
* [Sample rest app, comapre gin, echo, mux, chi](https://brunoscheufler.com/blog/2019-04-26-choosing-the-right-go-web-framework)
* [writing custom middleware for Echo](https://ednsquare.com/story/golang-how-to-setup-basic-middleware-with-golang-echo-framework------pBJHaZ)
* [Full echo documentation](https://echo.labstack.com/)
* [Echo sample app with middleware implementation exmaple](https://github.com/eurie-inc/echo-sample)

#### Conclusion
Go has mature battle tested web frameworks that are flexible, performant and easy to use.
