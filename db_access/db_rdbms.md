#### RDBMS database access libraries

In GO there are plenty of ORM like database libraries, there is native go slq library and bunch of libs mixing ORM and plain sql style. But because there are so many none of them covers all the issues.

What key points I would expect from decent db access library:
- good documentation
- simple table model definition
- basic crud operations
- easy way to handle native sql
- easy way to handle more complex queries (Joins)
- automatic handling off null fields
- transactions
- connections pool


- ~~thread pool (so we don't starve application on long running db queries)~~


>>Last strike through point is for people coming from JVM world. In GO you don't need to crate separate thread pools because go-routine are not mapped to system threads, thy are cheap and light weight. You can have thousands of them.




Among many I have chosen most popular ones and which I found to be most recommended (from my perspective)

1. Gorm
2. Xorm
3. Sqlx

I know there are many others if you want to add a chapter for you favorite one don't hesitate and create a PR.


##### 1. GORM

Most popular ORM there is for GO, it has biggets amount of stars on GH and is frequently mentioned in blog posts, reddit discussions etc.

- [x] (7/10) good documentation
- [x] simple table model definition
- [x] basic crud operations
- [ ] easy way to handle native sql _(no examples in the docs)_
- [ ] ~~easy way to handle more complex queries (Union etc)~~ Not tested
- [x] automatic handling off null fields
- [x] transactions
- [x] connections pool

**BUT** lot of people complain that when it comes to bit more complicated queires thay have to use plain SQL. For example when you are doing a join usign gorm dsl you need to call Preleoad() operation on the tables you want to join which under the hood is making new query to db (select * form sub_table), **multiple join will generate multiple queries**. This was raised as an issue [gh issue](https://github.com/jinzhu/gorm/issues/1436) and is forcing people to do manual queries with manual result mapping. Union are far from intuitive (for me at least).
Also mapping of plain queries is not good documented and therefore not easy to use.

But they is [V2 version](https://github.com/jinzhu/gorm/issues/2886) coming so maybe GORM will become a leader like Hibernate in Java world.


* [crud and simple join](https://github.com/gwalen/bettertomorrow/tree/master/context/company/persistance)

##### 2. XORM

- [x] (5/10) good documentation
- [x] simple table model definition
- [x] basic crud operations
- [x] easy way to handle native sql
- [ ] ~~easy way to handle more complex queries (Union etc)~~ Not tested
- [x] automatic handling off null fields _(but there are some tricks necessary)_
- [x] transactions
- [x] connections pool

It's less less powerful than GORM as ORM but adds nice features when you have to use plain sql query. Mapping struct to db rows is quite easy even if you have many entities returned in query result. Although mapping plain sql query result when you have one-to-many or many-to-many is still a pain the ass.
Joins are easy to use and don't to create extra sql queries (like Preload in Gorm)

So has ORM capabilities mixed with useful features for mapping plain queries.

Unfortunately the documentation does not have enough examples and you have to look for solutions in blogs or in stack overflow.

###### Code samples:
* [crud and simple join](https://github.com/gwalen/bettertomorrow/tree/master/context/customer/persistance)

###### Useful links:

* [xorm github](https://github.com/go-xorm/xorm)
* [xorm gobook](http://gobook.io/read/gitea.com/xorm/manual-en-US/)
* [xorm sql builer](https://gitea.com/xorm/builder)

##### 3. SQLX

- [x] (6/10) good documentation
- [x] simple table model definition
- [ ] basic crud operations
- [x] easy way to handle native sql
- [ ] easy way to handle more complex queries (Union etc)
- [ ] automatic handling off null fields _(but there are some tricks necessary)_
- [x] transactions
- [x] connections pool

Sqlx **is not an ORM**.
It is package with extensions over native database/sql package.

Among other features is allows for marshaling rows in structs, maps and slices.
But its super annoying (lot of boiler plate) when doing join and you must alias each field from joined tables.

It's a good choice when you don't want full ORM engine and its problems, but be prepared to write lot of boiler plate code.

###### Code samples:
* [crud and simple join](https://github.com/gwalen/bettertomorrow/tree/master/context/employee/persistance)

#### Conclusion
This are just a few I tried to briefly evaluate. Go has many options for ORM style and plain sql libs to access database. For me none of them seems full future/documentation complete but definitely you can get a job done and write efficient code with some extra code to cover edge cases.
