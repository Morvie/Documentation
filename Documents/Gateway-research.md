## What is an API-gateway architecture?

An API gateway serves as a reverse proxy to accept API calls from the client application, forwarding this traffic to the appropriate service.” 1*

It is a software component in between the front-end and the back end and separates these components from each other. It could be acted as a front-door of the back-end services to access data, logic or functionalities. It communicates through RESTful API’s and are HTTP-based communications to the front-end and back-end micro-services. 2*

<img src="../img/service-api-gateway.png">
<div align = center>
FIGURE 1: API-GATEWAY Architecture: <a href = "https://learn.microsoft.com/en-us/dotnet/architecture/microservices/architect-microservice-container-applications/direct-client-to-microservice-communication-versus-the-api-gateway-pattern"> Microsoft Learn </a>
</div>

&nbsp;
&nbsp;


With usage of the API-gateways, this could be with used and connected do several front ends with each its own gateway. This has proven to be a benefit to balance the load over the system and cluster together as a aggregation. This is also a way to improve security over the system, since each front-end has different user’s devices.3*

The benefits according to sources, of using an architecture with an API-gateway with micro-services are 4*:

<li>Centralized access to microservices.</bold>

Can handle several API calls simultaneously and route to different backend services. It receives the request from the front-end application and put the targeted service at work and waits for the result.

&nbsp;
&nbsp;


<li><bold>Authentication and Authorization.</bold>
With all requests going by an 

API-gateway, the API-gateway authenticates all traffic before routing it to the called service. The API-gateway can perform the authentication itself or use an external authentication service to do this task.

&nbsp;
&nbsp;

<li><bold>Traffic control to prevent overloading of resources. </bold>

API-gateways have built in barrier against DDoS attacks by throttling back the numbers of requests so, the API-gateway won’t get overwhelmed and still responsive for users.

&nbsp;

<li><bold>Threat protection.</bold>

With an API-gateway implemented, it can protect against cyber threats such as DDoS, SQL-injection etc. The API-gateway can inspect incoming requests and prevent a possible attack. And it is possible to integrate the API-gateway with a security service such as: SIEM or fraud systems to decide the request is good or bad.

&nbsp;
&nbsp;

<li><bold>Monitoring and Observability.</bold>

API-gateways can be fitted with an integrated analytics tool to help developer debug and create infrastructure. Most of the API-gateways use however a third-party monitoring tools so, this can help figuring out what’s happening in the API-gateway.

&nbsp;
&nbsp;

## Sources:


1* Kong Inc. (2022, 8 september). Microservices Challenges and How API Gateways Solve Them. Geraadpleegd op 3 oktober 2022, van https://konghq.com/learning-center/api-gateway/why-microservices-need-api-gateway#:%7E:text=An%20API%20gateway%20is%20a,traffic%20to%20the%20appropriate%20service.

2* What is Amazon API Gateway? - Amazon API Gateway. (z.d.). Geraadpleegd op 3 oktober 2022, van https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html

3* Post, S. P. G. (2021, 27 augustus). Why Do Organizations Use Multiple API Gateways?
SalesPOP! Geraadpleegd op 3 oktober 2022, van https://salespop.net/technology-insights/why-do-organizations-use-multiple-api-gateways/

4* Why Use API Gateway? Pros & Cons | Knowledge Base. (2021, 13 januari). Dashbird. 
Geraadpleegd op 3 oktober 2022, van https://dashbird.io/knowledge-base/api-gateway/pros-and-cons-of-using-an-api-gateway/ 
