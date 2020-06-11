# From JVM to GO : enterprise applications developer path

Path to GO from perspective of Java/Scala enterprise applications developer.

During pandemic lock-down I decided to learn GO.
My goal was to learn the language and verify if the ecosystem is ready to be easily used in enterprise applications with complicated business data models and typical cases we you have to face when developing such system.

It's an experiment others can use to find tools they need in their projects without scanning google for long hours.
I decided to host it on GitHub so anybody could create a PR to add something I missed, extend particular subject or fix what I wrote.

Each chapter has has code example in my pet project created during this journey.
GitHub repo for the project: [bettertomorrow](https://github.com/gwalen/bettertomorrow)

## What do we need when writing an enterpise web application

Here is the list of fetures/tools one need to jump straight in to writing business logic.
Assumption is we are building a system with microservice architecture, web UI, database (rdbms), message broker, with CI/CD pipeline all that deployed in the cloud. So nothing too fancy.

#### _Must have libs or frameworks and language features for :_

### &nbsp; 1. Efficiently build rest-api
  * [Web framework](http/http.md)
  * Generate rest-api documentation **TBD**


### &nbsp; 2. DB access
 * [RDBMS](db_access/db_rdbms.md)
 * NoSql **TBD**

### &nbsp; [3. Efficient and easy to use logging](logging/logging.md)

### &nbsp; [4. Clear way for DI](di/di.md)

### &nbsp; [5. Reactive programming libraries (streaming data)](reactivex/reactivex.md)

### &nbsp; [6. Clear error handling](error_handling/errors.md)

### &nbsp; [7. Concurrency as first class citizen](concurrency/concurrency.md)

### &nbsp; [8. Code debugging and profiling](debugging_profiling/debugging_profiling.md)

### &nbsp; [9. Testability](testing/testing.md)

### &nbsp; 10. Communication with message brokers **TBD**

### &nbsp; 11. [IDE support](ide/ide.md)

#### _Less essential but nice to have :_

### &nbsp; [1. Configure app using file or environment variables](app_config/app_config.md)

### &nbsp; [2. Db migration tools](db_migration/db_migration.md)


&nbsp;

![#c5f015](https://placehold.it/15/c5f015/000000?text=+) *I deliberately omitted generics in the list above to avoid endless discussion*
