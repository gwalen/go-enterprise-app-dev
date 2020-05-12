# From JVM to GO : enterprise applications developer path

Path to GO from perspective of Java/Scala enterprise applications developer

During pandemic lock-down I decided to learn GO.
My goal was to learn the language and verify if the ecosystem is ready to be easily used in enterprise applications with complicated business data models and typical cases we you have to
face when developing such system.

Its an experiment I hope other can use to find tools they need in their projects without scanning google for long hours.
I decided to host it in GitHub so anybody could create a PR to add something I missed, extend particular subject or fix what I wrote.

Each from the chapters below has has code example in my pet project created during this journey.
GitHub repo for the project: [bettertomorrow](https://github.com/gwalen/bettertomorrow)

### its still work in progress so have mercy :)

## What do we need when writing and enterpise web application

Here is the list of fetures/tools one need jump straight in to writing business logic.
Assumption is we are building a system with microservice architecture, web UI, database (rdbms), message broker, with CI/CD pipe line all that deployed in the cloud. So nothing too fancy.

#### _Must have libs or frameworks and language features for :_

### &nbsp; 1. Web framework to efficiently build rest-api [Done, add code refs]

### &nbsp; 2. DB access
 * RDBMS [Done, add code refs]
 * NoSql [TBD]

### &nbsp; 3. Efficient and easy to use logging [Done, add code refs]

### &nbsp; 4. Communication with message brokers

### &nbsp; 5. Clear way for DI [Done, add code refs]

### &nbsp; 6. Reactive programming libraries (streaming data) [TBD]

### &nbsp; 7. Clear error handling [Done]

### &nbsp; 8. Concurrency as first class citizen

### &nbsp; 10. Code debugging and profiling

#### _Less essential but nice to have :_

### &nbsp; 1. Configure app using file or environment variables [Done]

### &nbsp; 2. Db migration tools [Done]


&nbsp;

![#c5f015](https://placehold.it/15/c5f015/000000?text=+) *I deliberately ommit generics in the list above to avoid endless discussion*

# CONTENT SECTION - TODO: divide into pages
