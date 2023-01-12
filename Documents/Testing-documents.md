
---
<a name="readme-top"></a>

<!-- PROJECT LOGO -->


<div align="center">
<a>
<img src="https://raw.githubusercontent.com/Morvie/Documentation/main/img/logo.png" alt="Logo" width="250" height="250">
</a>

<h1 align="center">Test Report document.</h1>
<h3 align="center">Documentation | Morvie organization</h3>

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
    <li><a href="#Tools"> ➤ 🛠️ Used tools.</a></li>
    <li><a href="#Code-tests"> ➤ 💻 Code based tests.</a></li>
    <li><a href="#Use-case-tests"> ➤ 👤 Use-case based tests.</a></li>
    <li><a href="#Security-tests"> ➤ 🔐 Security based tests.</a></li>
  </ol>
</details>

---

<h2 id="Tools">🛠️ Used tools</h2>

<table>
    <tr>
        <th>
            <h3 align = "center"> Code-test | Unit testing </h4>
        </th>
    </tr>
    <tr>
        <th>
        <div align = "center">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSTBx2ZWjw7KCqQZeY7Qq2n0qu8WpLmB27RrXhXR_ZrRQPl9qAc_2pPBU53kN3vXcrCibc&usqp=CAU" width="200">
            </div>
        </th>
    </tr>
    <tr>
        <th>
            <p><div align="center">This framework is a <code>Unit and Integration</code> test framework.</p></div>
        </th>
    </tr>
    <tr>
        <th><div align="center">
            <p>Motivation:</p>
            <p>The main reason this testing framework was chosen over alternatives such as: <code>MS Test</code> or <code>NUnit</code> was due to the fact to the following points:</p> 
            </div>
            <ol>
                <li><code>Open-source:</code> Like other framework options this framework is open-source. </li>
                <li><code>Single Object Instance per test method:</code> This means that test-methods are isolated. Whether the tests are being executed, the state of the application e.g. variables gets reset to the original state in order to prevent failed tests by other tests.</li>
                <li>
                    <code>No [SetUp] is required:</code> Within this framework, no setup is required before executing the written tests.
                </li>
            </ol>
            <p> The main reason of my choice of using xUnit is due to its flexibility.</p>
        </th>
    </tr>
</table>

---

<table>
    <tr>
        <th>
            <h3 align = "center"> Use-case tests | System testing </h4>
        </th>
    </tr>
    <tr>
        <th><div align="center">
            <img src="https://s4-recruiting.cdn.greenhouse.io/external_greenhouse_job_boards/logos/400/113/000/original/logo_landscape_(1).png?1643756332" width="200">
            </div>
        </th>
    </tr>
    <tr>
        <th>
            <p><div align="center">This framework is a <code>System and End-to-end</code> testing framework.</p></div>
        </th>
    </tr>
    <tr>
        <th><div align="center">
            <p>Motivation:</p>
            <p>The reason, I chose this is due to personal preference. I wanted to setup some quick test so, I can test the implemented reCAPTCHA protection and validate the working flow of the front-end, back-end and database.</p>
        </th>
    </tr>
</table>

---

<table>
    <tr>
        <th>
            <h3 align = "center"> Security testing | Automated security testing</h4>
        </th>
    </tr>
    <tr>
        <th><div align="center">
            <img src="https://pbs.twimg.com/card_img/1612837224164245507/xNsw78dW?format=png&name=240x240" width="200">
            </div>
        </th>
    </tr>
    <tr>
        <th>
            <p><div align="center">OWASP ZAP</p></div>
        </th>
    </tr>
    <tr>
        <th>
            <p><div align="center">This is a <code>Automated security</code> testing tool.</p></div>
        </th>
    </tr>
    <tr>
        <th><div align="center">
            <p>Motivation:</p>
            <p>In order to check the webapplication against possible vulnerabilities, I wanted to execute an automatic scanner. By advice of Xuemei, my teacher, I wanted to give this tool a try. And so far, I found the following items benefits for using this tool:</p></div>
            <ol>
            <li>It is <code>open-source</code> web application security scanner. Which does not charge me anything and it has large community support.</li>
            <li>It is a great tool for beginners, it enables developers to perform penetration testing on their application to discover vulnerabilities. </li>
            <li>The OWASP Zap application focuses on being the man-in-the-middle with proxy. So, doing this intercept and examine messages between the browser and web-application.</li>
            <li>This tool is developed by <code>OWASP</code> which the known to be the expert based on web-application security.</li>
            </ol>
        </th>
    </tr>
</table>

---

<table>
    <tr>
        <th>
            <h3 align = "center"> Security testing | Load testing </h4>
        </th>
    </tr>
    <tr>
        <th><div align="center">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ef/K6-logo.svg/1058px-K6-logo.svg.png" width="200">
            </div>
        </th>
    </tr>
    <tr>
        <th>
            <p><div align="center">This is a <code>load</code> testing tool.</p></div>
        </th>
    </tr>
    <tr>
        <th>
        <div align = "center">
        <p>This is a load-testing tool provided by Grafana labs. When chosing this type of tests, it has the ability to use Influx DB databases and Grafana dashboards to monitor the test-results of load testing the application.</p>
        </div>
        The main advantages of using this tool are: 
        <ol>
            <li>Easy to learn since it does not require much in order to run a test.</li>
            <li>Integration with <code>CI/CD</code> which can be used for reporting issues to GitHub/slack etc.</li>
            <li><code>A very lightweight tool</code> that comes almost out-the-box with features and can be ran by using a PowerShell script.</li>
            <li>With usage of <code>InfluxDB database</code> and <code>Grafana dashboards</code> publishing real-time data into the dashboard. Thus, monitoring options over data is possible.</li>
        </ol>
        <br/>
        <p>The main advantages of using this tool are:</p>
        <ol>
        <li>Not generating a HTML report like <code>J-meter</code> does.</li>
        <li><code>Distributed load generation</code> is not yet possible out-of-the-box. However, we can implement that using a single Grafana + InfluxDB setup.</li>
        </ol> 
        </th>
    </tr>
</table>

---

<table>
    <tr>
        <th>
            <h3 align = "center"> Security testing | Static code analysis</h4>
        </th>
    </tr>
    <tr>
        <th><div align="center">
            <img src=https://blog.cellenza.com/wp-content/uploads/2018/02/article-SonarCloud-Analysez-votre-projet-GitHub-via-VSTS.jpg" width="200">
            </div>
        </th>
    </tr>
    <tr>
        <th>
            <p><div align="center">This is a <code>Static code analysis security</code> testing tool.</p></div>
        </th>
    </tr>
    <tr>
        <th><div align="center">
            <p>Attribution towards project:</p>
            <p>This tool performs static code analysis, which attributes to writing better quality and more secure code. It gets triggert on CI-pipeline and scans the repository for code-smells, security issues and duplications</p> 
            </div
        </th>
    </tr>
</table>

---

Before I continue on giving the test-results, based on the level from code to the whole picture. It is important to understand that some test can be fully automated and some need to be fully configured. And with the following tests, I integrated all these tests and some more.

`And it is important to know that all tests are integrated within the CI-pipeline` so, this means that once a push in main-branch all tests will be triggered!

And to make this document short, I will explain the a performed test, its purpose and why it is implemented.

<div align = "center">
    <img src = "https://survivejs.com/249f5e772e285a5c5a12490b3b662035.png" width = "350">
</div>

<h2 id="Code-tests">💻 Code-based tests</h2>

Within the application, I wanted to perform the following tests that are seen as `Code-based tests`:

- Unit tests
- Integration tests

---

### Unit testing

Beginning with the Unit tests. These tests are created to test code components, idealy service-layer components, but anything is fine. It never tests the system as it whole since this is the integration test. I applied this test in the `feeds` and
`forums` microservices.

For this project, I wanted to test the `GET` operation of the `MediatR handler function`:

```C#
        [Fact]
        public async Task GetSingleForum()
        {
            //Arrange
            var handler = new GetFeedHandler(_mockRepo.Object);
            var expected = new FeedDto() { Id = new Guid("208e2274-db97-4ac4-b17c-27d10abca7a8"), TopicName = "Harry Potter & The Deathly Hallows Part 1 - Hagrid?!", Content = "Just Hagrid in the movie?!.", LastEdited = DateTime.MaxValue, CreatedAt = DateTime.MaxValue, Author = "Henk" };

            //Act
            var result = await handler.Handle(new GetFeedQuery(new Guid("208e2274-db97-4ac4-b17c-27d10abca7a8")), CancellationToken.None);

            //Assert
            Assert.Equal(expected.ToString(), result.ToString());
        }
```

And the following test returns as successfull within two items, the code results is succeeded. And the code component gets a 100% code coverage.

<div align = "center">
    <img src = "..\img\Tests\Report-UNIT.png" />
    An 100% code coverage because the Unit tests hits this code component.
</div>

<br/>

<div align = "center">
    <img src = "..\img\Tests\Unit-test result.png">
The Unit Tests of testing the QUERY handler of MediatR came back succeeded!
</div>

---

### Integration testing

With the integration testing, the complexity of executing these tests became more complicated since using the whole application. In order to make a temporary database each time this test gets triggered, I used `SQLlite.` SQLite is a file-based relational database which will execute the tests and throw away the database once the test are executed.

The purpose with doing integration testing is to check the interaction between the services and validate their purpose. And the aim is to test the interfaces of the modules. If this is instable or broken, it will return the test as failed.

In order to make this tests work, I used the following steps:

1. Usage of Partial class program, to get the application context and apply the tests to it

```C#
public partial class Program { }
```

2. Create a shared database fixture which will be used to execute the tests:

```C#
namespace Forums.Test.IntegrationTest
{
    public class SharedDatabaseFixture: IDisposable
    {
        private static readonly object _lock = new object();
        private static bool _databaseInitialized;
        private string dbName = "TestDatabase.db";
        public SharedDatabaseFixture()
        {
            Connection = new SqliteConnection($"Filename={dbName}");
            Seed();
            Connection.Open();
        }
        public DbConnection Connection
        {
            get;
        }
        public ForumDbContext CreateContext(DbTransaction? transaction = null)
        {
            var context = new ForumDbContext(new DbContextOptionsBuilder<ForumDbContext>().UseSqlite(Connection).Options);
            if (transaction != null)
            {
                context.Database.UseTransaction(transaction);
            }
            return context;
        }
        private void Seed()
        {
            lock (_lock)
            {
                if (!_databaseInitialized)
                {
                    using (var context = CreateContext())
                    {
                        context.Database.EnsureDeleted();
                        context.Database.EnsureCreated();
                        SeedData(context);
                    }
                    _databaseInitialized = true;
                }
            }
        }
        private void SeedData(ForumDbContext context)
        {
            var id = new Guid("1c565daf - 3eaa - 4b60 - bc11 - d0a96fce249e");
            var fakeForums = new Faker<ForumsDTO>()
                .RuleFor(o => o.Id, f => id)
                .RuleFor(o => o.Description, f => "This is a movie test description!")
                .RuleFor(o => o.Title, f => "Test forum")
                .RuleFor(o => o.Ownership, f => id)
                .RuleFor(o => o.MovieId, f => f.Random.Int(10000, 99999))
                .RuleFor(o => o.DateOfAdded, f => DateTime.Now)
                .RuleFor(o => o.Amountoflikes, f => f.Random.Int(0, 1000))
                .RuleFor(o => o.Reported, f => false);
            var products = fakeForums.Generate(10);
            context.AddRange(products);
            context.SaveChanges();
        }
        public void Dispose() => Connection.Dispose();
    }
}
```

This database also get seeded with attributes to test the GET operations from.

3. And create the integration test. I called the controller to execute this `POST` test. I provided data and looked up for the result:

```C#
        [Fact]
        public async Task CallMediatorWithCorrectParameters()
        {
            var mediator = new Mock<IMediator>();
            var command = new CreateForumCommand("Title", "Description", new Guid(), DateTime.Now, false, 1346, 54326);
            var controller = new ForumController(mediator.Object);

            await controller.Create(command);

            mediator.Verify(x => x.Send(command, default(CancellationToken)), Times.Once());
        }
```

<div align="center">
<img src="..\img\Tests\IntegrationTest_POST.png">
<br/>
The result came back as succeeded!
</div>

---

<h2 id="Use-case-tests">👤 Use-case based tests</h2>

### Functional Tests

When I wanted to see whether the Docker and Kubernetes are working on networking level. I decided to use Postman for these tests. So, it was fairly easy to setup these kinds of tests.

The purpose of this test is the application to establish the check whether the application works on software requirements such as `response time for single requests`, `functionality` etc. This can also be used to test whether non-functional requirements are met.

So, one of the testsis a POST test I have performed, which will check for:

- HTTP code is 200
- Response time for single requests is less than 200ms
- POST requests is successful
- Body matches with string as response.

<div align="center">
<img src="..\img\Tests\Functional-test.png">
</div>

---

### System/End-to-end tests

With the system tests, I want to check whether the system operates correctly as responding within the requirements. The system test (similar to end-to-end tests, but not the same!) will execute a manually written test by the developer and check if the system does execute the workflow correctly accoding to the test.

This is also a way to test whether a system is secure and has no hidden flow misseption. Within the two written tests, I will demostrate the system workflow.

1. **Trigger reCAPTCHA**

```js
  it("Registry of a user should not be automated", () => {
    cy.visit("https://morvie-frontend-markgoertz.vercel.app/");
    cy.origin("http://localhost:2222/", () => {
      cy.get("a").contains("Register").click();
      cy.get("#firstName").type("Cypress");
      cy.get("#lastName").type("bot");
      cy.get("#email").type("cypress.bot@mail.com");
      cy.get("#username").type("Im am a bot!");
      cy.get("#password").type("Bot123!");
      cy.get("#password-confirm").type("Bot123!");
      cy.get("#kc-form-buttons").click();

      //Checking the window alert text
      cy.on("window:alert", (txt) => {
        //Assertion
        expect(txt).to.contains("Invalid Recaptcha");
      });
    });
  });
```

By executing this test, it opens up an automated test execution, which will execute the test by performing the actions-order. By using this it shown it has passed:

<div align = "center">
    <img src = "..\img\Security\Cypress.io-test overview.png">
</div>

Which does look similar like this on the page itself:

<div align = "center">
    <img src = "..\img\Security\Recaptch-protection-trigger.png">
</div>

The purpose with this automated test is to check whether the application succeeds on a level of bot-detection. With the automated test which can perform on a faster speed than a human, the system can validate that this action is automated and ask for the reCAPTCHA validation.

2. **Post operation application.**

With the following test-script, I was able to test my POST action from the front-end all the way back to the database. And it has been done with Docker test databases.

This is the script which is used:

```js
  it("Post thread in detailed page", () => {
    cy.visit("https://morvie-frontend-markgoertz.vercel.app/movie");
    cy.origin("http://localhost:2222/", () => {
      cy.get("#username").type("Cypress");
      cy.get("#password").type("Bot12345!");
      cy.get("#kc-login").click();
    });
    cy.wait(2000);
    cy.get("a").contains("Puss in Boots: The Last Wish").click();
    cy.wait(2000);
    cy.get("button").contains("Open form").click();
    cy.get("#topicName").type("Automated Testing with Cypress");
    cy.get("#content").type("This is fully automated POST test!");

    cy.get("button").contains("Submit").click();

    //Checking the window alert text
    cy.on("window:alert", (txt) => {
      //Assertion
      expect(txt).to.contains("Thread successfully created!");
    });
  });
```

Note the `topicname` and `content` which are currently set on: "Automated Testing with Cypress" and "This is fully automated POST test!". With the assertion on created window alert, I can validate whether the operation succeeded or not.

I can also test this further by pasting injections, input validations and more.

The test result was executed and the result is:

<div align = "center">
    <img src = "..\img\Tests\Cypress-automated.png">
    DOM Screenshot based of mid-testing.
</div>

---

<h2 id="Security-tests">🔐 Security based tests</h2>

On behalf on security testing within this application, I have performed 4 different sorts of tests to validate the security requirements. The security requirements are set with help of `OWASP top 10` and `CIP` requirements.

So, started with using the automated security scanner: `OWASP ZAP`.

---

### Automated security testing

With OWASP ZAP as tool, I manually scanned the Vercel Application against security vulnerabilities. To do this, I installed ZAP on my local machine and installed the required Java runtime 11. 

When everything is configured properly, I opened up the application and started out with the button`automated security testing`. I had to fill in the URL which host the front-end application and that was: 
```
https://morvie-frontend-alpha.vercel.app/
```
It starts out with scanning the webapplication and gives the result back:

<div align = "center">
    <img src = "..\img\Security\WASP-highAlert.png">
</div>

With this result, I can evaluate that the security is not perfect. So can we see that the most vulnerable issue is the: 
`Cloud Metadata Exposed` which results in metrics about the hosting being exposed. This can make the job for blackhat easier to see the data about the machine and get data about the data.

As well as `Cross Domain misconfiguration`, this has to do with Cross Origin Resource Sharing (CORS) is possibly exposed by unauthenticated manners. In order to fix this issue, I have to configure the `Access-Control-Allow-Origin` HTTP header to a more restrictive set of domains.

---

### Manual security testing

Within the application not everything is testable by automation, and it sometimes require human testing. With common techniques and known security issues, we can create these tests ourselves and become a `penetration tester` ourselves.

I will execute four security tests which will look up whether the application has prevent measurements against it.


#### SQL injection

First I wanted to the `SQL injection attack` in the database to check to trigger a successful injection attack. This can be done by pasting the next injection into the SQL script:

<div align = "center">
    <img src = "..\img\Security\SQL injection in db.png">
</div>

By pasting the next injection into the SQL script for the `POST` operation, can trigger the injection attack:

```SQL
John';SELECT * FROM <database>;

```
<div align = "center">
<img src = "..\img\Security\SQL injection.png">

Even with encoding the `"` character, the injection attack did not sanitize the injection attack directly. 

<img src = "..\img\Security\SQL-injectionEncoded.png">

This is prevented since I have used an `Object Relation Mapper (ORM)`, which will prevent the injection attack by sanitizing and parameterizing the object into the `SQL script`.
</div>

---

#### Stored Cross-site scripting vulnerability (XSS)

This attack is similar to the SQL-injection attack, but this attacks places a malicious script as text input into the application. Which makes the user think this is something valid since it is on the web application. 

I generated this attack by executing the following script as input: 


```js
<script src ="http://maliciouswebsite.com/">Malicious</script>
```
<div align = "center">
<img src = "..\img\Security\Stored-XSS.png">


But this attack does not work as this is protected as well due to the use of an `ORM`.
</div>

--- 

### Load testing

To test the non-functional requirements for this application, I used load testing on my application. This is a way to test the load-balancing on the web application on its functionalities. The non-functional requirement based on load-balancing testing is: `the application should handle 2k users and handle http requests within 0,5 seconds. 

So, in order to perform this load-testing, I have set-up the environment with K6, InfluxDB and Grafana dashboard. 

<div align = "center">
    <img src = "..\img\Tests\Grafana-LoadTests_GET.png">
    I performed the above test with GET operations. It uses 2k users and it executed the test 95% of the 0,5 seconds within these seconds.
    <img src = "..\img\Cloud\Autoscaler_Load_GET.png">
     And as you can see, the application handles the load but does not correct itselves.
    <br/>
    <br/>
    <img src = "..\img\Tests\Grafana_Load_POST_Nonscaled.png">
    This task is performed with Kubernetes autoscaler on. Which enables the application to scale up horizontally and spread the load over the different pods. And as you can see, the application beings to scale down within the metrics. But due to the <code>rate limiter</code> on my private network at home, it scales up since it can not handle the HTTP request. So, that also the reason I had to test with 10k users. 

</div>

&nbsp;

<div align = "center">
<img src = "..\img\Tests\Load-test_POD-scaling.png">
With this usage of Azure, I could monitor the pods scale up from 9 to 20 pods. So, the autoscaler is working!
</div>


---

### Static code analysis

To automated security on this project, I made sure to use a static code analysis by using the provider `Sonar Cloud`. This can be setup by using a CI pipeline which scans the code for vulnerability:

The following image can show the vulnerability automatically:
<div align = "center">
<img src = "..\img\DevOps\Security-scanning.png">

During the scan, it scans against security vulnerabilities and code smells. Which provides feedback on the CI-pipeline and cloud.
</div>


---

## Sources:

- Clariontech | Vinugayathri (2022) https://www.clariontech.com/blog/why-should-you-use-xunit-a-unit-testing-framework-for-.net#:~:text=xUnit%20is%20far%20more%20flexible,NotEqual%2C%20InRange%2C%20%26%20NotInRange.

- Home. (z.d.). xUnit.net. https://xunit.net/

- JavaScript End to End Testing Framework. (z.d.). JavaScript End to End Testing Framework | cypress.io testing tools. https://www.cypress.io/

- Peerspot | ? | (December 2021)
  https://www.peerspot.com/products/owasp-zap-reviews

- OWASP ZAP – Getting Started. (z.d.). https://www.zaproxy.org/getting-started/
