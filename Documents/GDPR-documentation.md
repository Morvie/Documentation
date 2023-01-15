
---

<a name="readme-top"></a>

<!-- PROJECT LOGO -->


<div align="center">
  <a>
    <img src="https://raw.githubusercontent.com/Morvie/Documentation/main/img/logo.png" alt="Logo" width="250" height="250">
  </a>

  <h1 align="center">GDPR + Observability and Performance documentation</h1>
  <h3 align="center">Morvie Documentation</h3>

  <p align="center">
    <br />
    <a href="https://github.com/orgs/Morvie/repositories"><strong>View repositories»</strong></a>
    <br />
    <br />
    <a href="">View Demo</a>
    ·
    <a href="https://github.com/Morvie/Documentation/issues">Report Bug</a>
  </p>
</div>

---

<!-- TABLE OF CONTENTS -->
 <h1 id="table-of-contents"> :mailbox_with_mail: Table of Contents</h1>


<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#GDPR and Data comlexity"> ➤ GDPR and Data complexities.</a></li>
    <li><a href="#Distributed data"> ➤ Distributed data.</a></li>
    <li><a href="#Observability tools"> ➤ Observability tools.</a></li>
  </ol>
</details>

&nbsp;


<h1 id = "GDPR and Data comlexity">🔏 GDPR and Data complexities</h1>

## 1 - Lawful basis and transparency

* Art. 6 GDPR: Lawfulness of processing
* Art. 12 GDPR: Transparent information,communication and modalities for the exercise of the rights of the data subject.
* Art. 30 GDPR: Records of processing activities

---

Morvie as the application holds several data topics. These topics are personal data, movie data and user input data (such as user given reviews and ratings). So, this will explain what will be done with the personal data of our customers.

`Personal data` gets collected by the application in order to make it run operations. Only the `username, password, name and a unique email address` is required to create a personal account. And with the personal account the user would be able to create a feed within the forums about a movie. So, at registry the application will create a unique personal identifier so that the application can use this identifier to allocate the forums with the correct account. The email of the user will be used to make sure that the user can login and/or can perform a 'forgot my password' recovery whenever the user forgot this (possibility in the near future as a feature). And thus can recover the account. Also uses it called: `metadata` which will be used to prevent harm to the account. This is encrypted and hashed to prevent vulnerabilities:

<img src = "..\img\Security\Keycloak-encryption.png">
<img src = "..\img\Security\OTP policy .png">

The operators of morvie can not see the personal information of the user since `keycloak` user management service has the access control configured to not been able to see any user information. And all user-data processing activities will be recorded under the Event section of Keycloak, which holds uneditedable information about the data processing activities. 

<img src= "..\img\GDPR\Keycloak-Events.png">

The personal data, storage location, usage of the data and duration of holding this data is important to be explained. Within the table below, this will bee explained. Thereby, I hope to inform the usage of the personal data within this application.

<table align = center>
  <tr>
    <th width="200">
        Personal data type
    </th>
    <th width="600">
        Location of storage
    </th>
    <th width="600">
        Usage of this data.
    </th>
    <th width="600">
        Duration of holding this data
    </th>
  </tr>
  <tr>
    <td>
       Email-address + username + password
    </td>
    <td>
        Stored in a Keycloak authentication database server, which is stored locally on the developers laptop. With a single connection by keycloak and the database. It can still be deleted by keycloak.
        The database is an <code>PostgreSQL database.</code>
    </td> 
    <td>
        This data gets used to validate the user on registry and authentication and/or authorization operations. It is an identifier of the unique user.
    </td> 
    <td>
        This data gets stored as long as the user is active. The initial plans for implementing GDPR friendly data-removal will be done when the user is no longer active and have not logged in  within the past 2 years. The user will receive multiple notifications by mail to log in otherwise the data will be removed and destroyed.
    </td> 
  </tr>
  <tr>
    <td>
       User Identifier
    </td>
    <td>
        Will be stored within the keycloak user database using <code>PostgreSQL database</code> and the Feed- and Forums-database using <code> MSQL database</code>
    </td> 
    <td>
      This data will be used to make a connection between the user-made feed and/or forums. In order to let the application make a correlation between the owner of the feed/forum and the feed/forum itself.
    </td> 
    <td>
      It remains as long as the user wants it feed/forum to be shown on the website. Unless it is inapropriate to display, it will be destroyed immediately with the user identifier. And the user is free for removal of the feed/forums.
    </td> 
  </tr>
  

</table>


&nbsp;

#### Data processing and legal justifications.

Within the user registery form, there will be a `clear` and `big` text box in where the user is mandatory to read the usage and collection of user personal data over the email address and password. And will let the user continue after it fully red the usage over their information and collection. 

&nbsp;
&nbsp;

## 2 - Data security

In order to maintain the security of data, I applied the CIA-triad requirements as well for data usage. Within this application data get secured by using an encrypted transit over `HTTPS`. Which is to be configured for every keycloak action that needs to be performed. To enable `HTTPS`, I had to go to the settings and enable HTTPS for all requests.

<img src= "..\img\Security\Keycloak-RequirementForSSL.png">

Another thing I did to mainstain data security, is to encrypt user data. I did it by using `encryption` and `hashing iterations`. The used encryption to encrypt user information is: `pbkdf2-sha256` and the used hashing iterations are: `27500`. Which should users protect their information against `rainbow-table attacks`. As seen in the image below on the configurations:

<img src= "..\img\Security\Keycloak-encryption.png">
<img src= "..\img\Security\Keycloak-password.png">

There is also being a internal security policy for the keycloak users. And this is by using a two-factor authentication mechanism in order to protect the account of the individual. To enable the two-factor authentication, the user has it freedom to share the device-id in order to secure itselves against possible attacks.

<img src= "..\img\Security\Keycloak-2FA-registry.png">

This can be found within the account configuration console, where the user can set up the 2FA and see the latest log in attempts:

<img src= "..\img\GDPR\Account console-Signings.png">

---

## 3 - Accountability and governance

* GDPR Article 25 – Data protection by design and by default

* GDPR Article 27 – Representatives of controllers or processors not established in the Union

* GDPR Article 37 – Designation of the data protection officer
---

Within Morvie organization, there is no `Data Protection Officer` simply because the team is too small for this. And so does the development team need to take this in account. The developers are constantly monitoring the data protection and GDPR compliance. And act as a team of advisers and implement these advise.

The company acts within the European Union and so, there needs no reponsible representative in each country to represent to the data protection authorities. And since this company is operative within the `European Union`, the rules validation of GDPR complaince `apply to all member states of the European Union`.

With using a cloud provider which does the hosting and infrastructure of "Morvie", the contract of hosting the data service is signed by the purchase. Since the cloud provider `Azure` is of product name of  `Microsoft` and will be stored on a server in `North-Germany`. It is a risk of using a `public` hosting provider, but the costs currently does not allow to buy our own `private hosting domain`. 

The current reponsible person over ensuring the GDPR compliance accros the organization is the `developer: Mark Goertz`. And will be reponsible for creating awareness to the new members of the organization and will the desicion makers be informed about the data protection legislation.

&nbsp;

## 4 - Privacy rights

* GDPR Article 15 – Right of access by the data subject
* GDPR Article 16 – Right to rectification
---

In order to give the user the right to view it information, it must first be logged in. Once the user is logged in, the user has the availabillity to view its data. This can be performed by clicking on their username in page of Morvie:

<div align = "center">
<img src= "..\img\Application\Frontend-Home.png">
In this case by clicking on John Doe.
</div>

When the user clicked on this name, it will get redirected to the `account console`. Where they will see three options: 
* Personal Info
* Account security
* Applications.

<div align = "center">
<img src= "..\img\GDPR\Account console.png">
</div>

On the Personal Info page, the user will be able to see its personal information of name, username and email. This data can easily be modified (except for username since this needs to be unique). But also to be removed from the application, and thus choose not be a user anymore.

<div align = "center">
<img src= "..\img\GDPR\Account console - update data.png">
</div>


&nbsp;



<h1 id = "Distributed data">📅 Distributed data | CAP theorem</h1>
The CAP theorem is a way to validate the distributed data systems. A distributed data system provider can be divided into three selections. 

<div align = center>
    <img src = "../img/CAP.png">
</div>

#### Information and given examples.
The selection above describe the guarantees that you can promise to the users. But the promise can not be all three of them, but only 2. Explained what all guarantees are it will be explained below:

- `Consistency`: All clients have the same view of the data. So, this means that the users all see the most recent write or otherwise receive an error. And means that the data, the latest write data, is also highly accurate. Since consistency aims to be consistend.

- `Availability`: The guarantee promises users that the database service is more important than the information. These databases are widly seen in E-commerce businesses and applications. These databases replicate themselves when receiving a higher load than they can process.

- `Partion Tolerance`: This guarantee gives the users the guarantee that the database system will work well despite the physical network partions. So, the database cluster will continue to work even when two seperate nodes can not communicate with each other.


#### Choice within the project.
Within the project, I have decided to choose the following databases:
- `MSSQL database`: which runs on Docker.
- `PostgreSQL database`: which runs on Docker.
- `Azure(MySQL) database`: Which runs on Azure Cloud environment.
- `InfluxDB database`: Which will capture timeseries data from the performed Loadtesting.

With these chosen databases, I will explain which parts the database system will cover of the CAP theormen. Both of these databases will cover the CA parts of the CAP theorm. And will I give my motivation why I chose these database providers.

### Usage of Microsoft SQL Database.

---

With `MSSQL` database, the feature always on is enabled on the local development environment. It is a relational database which means it has the abillity to cover the two-factors of the CAP-theorm `Consistency` and `Availability`.
Since I am using a forum application, I wanted to have a `data-requirement` of users having the latest written data. Which can be shown with the usage of relational database with `Consistency`. 

Also a reason, I chose the microsoft sql database is because of the usage of an `Object Relation Mapper (ORM)`. Which the application uses to access the data from the database, build with `Entity Framework`, an tool made by Microsoft for relational databases. This tool can be used with all providers in relational databases.

This database gets to be used within the development database of this application, thus serve as Docker containers for the microservices:
`Feeds and Forums.`

<div align = "center">
  <img src = "..\img\GDPR\Usage of microsoft database.png">
</div>

&nbsp;

---

### Usage of PostgreSQL database

Within the keycloak service in this application, I have to store safely in order to make use of user and configuration data storage. To make sure I chose the right database, I looked up at the documentation of keycloak and it stated the following information:

```YML
Configuring the database

An overview about how to configure relational databases
This guide explains how to configure the Keycloak server to store data in a relational database.

Supported databases

The server has built-in support for different databases. You can query the available databases by viewing the expected values for the db configuration option. The following table lists the supported databases and their tested versions.

```
* mariadb version 10
* mssql | 2016
* mysql | 8
* oracle | 12c
* postgres | 10


So, I decided to go with PostgreSQL. I noted that these databases are all relational so, I wanted to know why this was the case. And it seems that keycloak wants to have a `Consistency requirement` on their database, so the users can view the lastest written data available. And the main reason for chosing Postgres is that it has a strong reputation for its reliability, data integrity(UNIQUE, PK, FK). And for my own learning purpose, since I don't have any experience with this relational database provider.

---

### Usage of Azure Cloud database.

The `Azure| MySQL database` will be used on the cloud environment. Which will automatically scale up by Azure services when needed. This brings an addional server usage costs, but it only charges only what the company requires.

I used the Azure database service for hosting a cloud database provider that will store the data and handle it strictly. Azure database which uses primarly `MySQL` database, will take this job.

The main advantage, I have with having a MySQL database over other relational database providers is the fact that MySQL is known for its `speed prioritaztion`. In benchmark tests it came close with Postgresql but still holds the reputation for a exceedingly fast database solution. The Azure MySQL database can automatically scale up when needed `vertically` and `horizontally`, and the availability is promised by Azure by `99.95%` in a year. That is `4,38 hours downtime` of a whole year.

As I use my Azure database with the `serverless compute tier` mode, it billed me only for the compute costs and storage.

<div align="center">
  <img src = "..\img\GDPR\Azure-Serverless.png">
  It only charges me cost of the usage of the vCores during the database usage.
</div>

&nbsp;

In order to apply this context to my project, my cost-monitoring looks like this:

<div align="center">
  <img src = "..\img\GDPR\Azure-monitoring.png">
  It only charges me cost of the used vCores during the database usage.
</div>




---

### Usage of Influx Time-series database.

Within this project, I wanted to make a observation-tool to see the load-test into a `Grafana` dashboard. In order to accomplish this, I used Influx DB to complete this task. Influx DB is not something new for me since I heavily used it during my previous internship. 

Influx DB is a time-series database in where the timestamp is the identifier over data. It maps the metric during over each second in order to create a time-series, which can be used in order to create graphs and plot diagrams.

I host it locally since this is a development tool. It can be hosted on a server in order to measure 24/7 over metrics data. But for load-testing this is not recommended since it can overload the server. The main reason to choose this tool is that it is open-source, has a great integrity with Grafana as tool and I did already have experience with this database provider.

<img src = "..\img\GDPR\InfluxDB.png"/>

#### Automated back-ups

Within Azure SQL database, there is a possibility to created weekly backups of the database. This can be done by simply enable the setting:

<img src = "..\img\Security\Morvie-database backup.png"/>





<h1 id = "Law">GDPR undertaken activities.</h1>

In order to apply the GDPR laws into our system to make it GDPR-proof, the following activities have been undertaken:

* Personal data can be managed by the owner of the data:


### Counterpart of using Relational databases.

When using Relational databases primarly for this application the Partion tollerance type of databases where not used. However for the future expansion I might consider using this type of databases, such as `MongoDB` and `Cassandra` which are NoSQL databases. Why? The reason behind this has to do with `scalability and application up-time.`


<div align= "center">
  <img src="..\img\GDPR\Account console-Devices.png"/>
  The user has once it is logged in into the system to view the options: Personal info, Account security and used applications.
</div>

&nbsp;

With the option: `Personal info`, the user can view its own personal information of the their account. 

Modify the user attributes (username is not adjustable since it is a unique attribute and not needed for GDPR compliant)

And delete the personal account with all its data, this action is truely irreversible. 

<div align= "center">
  <img src="..\img\GDPR\Account console - update data.png"/>
</div>

<h1 id = "Distributed system">Scalable distributed enterprise system</h1>

For this project, I build two microservices on a CQRS code pattern. This is pattern which divide the application in two different services as `READ-operations` and `WRITE-operations`. 

*Why is this good for distributed system?*

- With the usage of Command Query Seggregation Responability, it distributes data faster than the traditional repository code pattern. The reason is that it gives the application an seggregation in between these two operations, which allows the application to perform what is important. If the write operations are getting more used, it can autoscaling of kubernetes to scale up the server usage either horizontally or vertically.

And also can the application use the benefits of SQL and NoSQL databases since SQL have a faster performance in reading data from the SQL database, where the NoSQL database has a better performance in writing and handling data. I performed research about this which can be seen <a href="https://github.com/Morvie/Documentation/blob/main/Documents/Scalability-documentation.md">here</a>.

The disadvantage of using CQRS is that it makes the application harder to understand and maintain. This could trouble future updates and maintainance on the application.

---
### Messaging.

During the development of the scalabillity applications, I used the technique: `messaging`. With messaging, the application is able to make asyncrounous communications between eachother.

So, after a research I decided to use `RabbitMQ` with `MassTransit` and make a Proof-of-concept for my application with a `Producer` and a `Consumer`:



The `feeds-microservice` is my Producer: 

<img src="..\img\MessageBroker\RMQ-ProducerListening.png">

And the Consumer is the `forums-microservice`:

<img src="..\img\MessageBroker\RMQ-ConsumerListening.png">


With an active session in rabbitMQ, I was able to see both of the microservices listed as active connection and ready to do work:

<img src="..\img\MessageBroker\RMQ-Connections.png">

So, I sent a message from the producer to the consumer after I posted a test message:

<img src="..\img\MessageBroker\RMQ-Producer.png">

In which the `forumid` will be sent to the messagequeue:

<img src="..\img\MessageBroker\RMQ-QueuedMessage.png">

And almost instantly, the consumer picks up the produced message by the producer from the queue and will it take in its own application: 

<img src="..\img\MessageBroker\RMQ-Received-Message.png">

The advantage of using Messaging properly is that `confidential` data won't get lost when the message fails. It will be stored in the message bus and wait for the service to come back online again. So, it will cover the `Availabillity of the CIA-triad`.

<h1 id = "Observability tools">🔧 Observability tools</h1>

### Azure | Server and Pod monitoring

In order to see the logs within the pods of my Cloud hosting, I used Azure pod logging. This gives me the ability to monitor the logs on possible error-messages within the pod:



<div align="center">
<img src="..\img\Cloud\Azure-pod-logging.png"/>
In order to see logs errors, I went to the pod and see the live-pod logs.
</div>

&nbsp;

<div align="center">
<img src="..\img\Cloud\Azure-pod-events.png">
And pod event status as well
</div>

&nbsp;

<div align="center">
<img src="..\img\Cloud\Kubernetes-Cluster-monitoring.png">
To be able to see the health over the Kubernetes cluster on Azure, I could filter the metrics into <code>Node pool (CPU usage)</code>, <code>Node pool (memory usage)</code>, <code>Node pool network out</code> and as seen on the image above. This enables to give developers the opportunity to perform actions when the cluster is spiking.
</div>

---

### Keycloak | Logging

By default, this feature is disabled. So, I had to configure this setting within the keycloak configuration menu. So, I wanted to have the ability to view error logging and performance monitoring within the keycloak administration console. 

To be able to monitor the users actions of the administrators, I have added this event-console:

<img src="..\img\GDPR\Keycloak-Events.png"/>
<img src="..\img\GDPR\Keycloak-Events-Admin.png"/>

---

### Grafana | Load-test

In order to view metrics by an Obeservability tool, I used Grafana to view to load-tests. Grafana is an open-source tool that plots metrics into graphs. It will be used in combination with Influx Time-series database. I used Grafana because I also use `K6-load testing` which is also from the Grafana organization. So, it has optimized performance and integration.

In order to set this is up is by using the Grafana docker image. Which I received by getting `Docker-compose`. 

```YAML
 grafana:
    image: grafana/grafana:latest
#    entrypoint: /bin/sh
#    user: root
    networks:
      - grafana
    ports:
      - "3000:3000"
    environment:
      - GF_AUTH_ANONYMOUS_ORG_ROLE=Admin
      - GF_AUTH_ANONYMOUS_ENABLED=true
      - GF_AUTH_BASIC_ENABLED=false
      - GF_SERVER_SERVE_FROM_SUB_PATH=true
    volumes:
      - ./dashboards:/var/lib/grafana/dashboards
      - ./grafana-dashboard.yaml:/etc/grafana/provisioning/dadshboards/dashboard.yaml
      - ./grafana-datasource.yaml:/etc/grafana/provisioning/datasources/datasource.yaml
```
With the volume, I added the dashboard configuration provided as default template from Grafana. 

And after performing the load test, I get to see passively the performance about the load-test which is receiving HTTP information about the performed load-test:

<img src="..\img\Tests\Grafana-LoadTests_GET.png"/>

---

# Sources:

- GDPR.eu. (2022, May 26). GDPR compliance checklist. https://gdpr.eu/checklist/

- Fontys (2021). Cyber Security https://fhict.instructure.com/courses/11556/pages/reference-law-standards-and-compliance?module_item_id=680345

- Advisera.com (2022, April 13). Top 10 GDPR Requirements https://advisera.com/eugdpracademy/knowledgebase/a-summary-of-10-key-gdpr-requirements/

- What is the CIA Triad? Definition, Importance & Examples. (2022, 8 oktober). SecurityScorecard. https://securityscorecard.com/blog/what-is-the-cia-triad

- Savjani, S. (2022, 29 november). Hoge beschikbaarheid - Azure Database for MySQL. Microsoft Learn. https://learn.microsoft.com/nl-nl/azure/mysql/single-server/concepts-high-availability

- Digital Ocean (2022, https://www.digitalocean.com/community/tutorials/sqlite-vs-mysql-vs-postgresql-a-comparison-of-relational-database-management-systems