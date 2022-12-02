# Code pattern.

### How to make databases scalable?

To make the database scalable, a technique can be implemented within the software architecture called: “database caching”. This technique allows the data to be cached and prevent the database to be overloaded by requests. 
How does it work? 
-	This technique works by storing the query statements shortly in the application or cache database. And by setting up the right configurations, the query statements will be executed to the main database on every 2 minutes. This is beneficial when you want the network traffic to lower the latency and keep the scalability and performance high.

&nbsp;
&nbsp;

 
<div align = center>
<img src = "../img/DB-ReadReplicas.png" width="500" />
</div>

&nbsp;
&nbsp;

In order to complete learning outcomes: scalable architectures and security by design I want to make research about how an architecture can contribute to this.

To keep the scope short due to time limits, I want to research about CQRS-code pattern which is popular amongst the ‘scalable software architectures.
## How does the CQRS-code pattern contribute to better scalable applications?

CQRS stands for Command Query Responsibility Segregation and is a pattern that separates read and update operations for a datastore. Compared to traditional architecture the same data model to perform query and update to the database is more complex to implement and can maximize performance, scalability and security.

Due to its so called: Command and Query, the application has two divided tasks that each can specialize to.

- Commands are responsible to perform task-based operations such as POST and UPDATE.
- Queries are responsible for receiving information from the database and can never modify the database.

So, the application structure gets divided into two separate structures: a command and query services. And so, it separately can perform its own actions. Which allows the data schema’s to be optimized for queries and the write side uses a schema optimized for updates. For security reasons it easier to ensure that the right domain entities are performing writings on the data.
<div align = center>

![Introduction to CQRS — In Microservices | by Daniel Chernenkov | Medium](../img/Aspose.Words.d4adb322-9f43-4940-af40-c0e383f85ecb.001.png)
</div>
Combined with the benefits of SQL and NoSQL databases, the application can rapidly perform actions to the NoSQL database. And receive data from the SQL database. In between the databases can communicate through an Event handler or synchronization. 

## Sources:
*CQRS pattern - Azure Architecture Center*. (z.d.). Microsoft Learn. Geraadpleegd op 10 oktober 2022, van <https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs>

Engineering, R. (2022, 31 mei). *CQRS Explained*. RisingStack Engineering. Geraadpleegd op 10 oktober 2022, van <https://blog.risingstack.com/cqrs-explained-node-js-at-scale/>

*What is a database cache and how does one use it? (2012, September 1). Stack Overflow. Retrieved October 5, 2022, from https://stackoverflow.com/questions/12227752/what-is-a-database-cache-and-how-does-one-use-it

*Nnakwue, A. (2021, April 7). Caching in Node.js: Optimizing app performance with Redis. LogRocket Blog. Retrieved October 5, 2022, from https://blog.logrocket.com/caching-node-js-optimizing-app-performance-redis/

