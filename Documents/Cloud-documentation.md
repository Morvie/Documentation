
---

<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a>
    <img src="https://static.vecteezy.com/system/resources/previews/002/206/166/non_2x/cloud-computing-icon-free-vector.jpg" alt="Logo" width="250" height="250">
  </a>

  # Cloud provider and services
</div>

---

## What is the cloud?

The cloud is basically the internet. 
And it is a general term for anything that involves in delivering hosted services over the internet. Instead of just using the tradional hosting over one single server. But instead its gets hosted over a network of connected virtual and physical cloud servers. This ensures a more `scalable` and `flexible` hosting of website and applications. So, if one service gets overloaded or a server is down, the cloud will redirect the user to an another cloud server.

And can offer the option to host databases of SQL and NoSQL servers as well.

It can be seen as a platform-as-a-service (PaaS), in which software services can be integrated into with the software application. Such as:
- data storage
- data analysis
- monitoring and logging
- Container Orchestration
- Autoscaling
- Database solutions

But there is also Software-as-a-service `SaaS`, and Infrastructure-as-a-service: `IaaS`. For this project, I will look up the IaaS services and will consider the options within my project.

And will I use a public cloud over the private and hybrid cloud options. This is because I simply do not have the money to buy my own physical hardware for hosting the cloud myself. 

&nbsp;

***GDPR Sensitive!*** 

So, since I do not use a private hosting option. I do have to keep in mind, I can not control the physical server and have to rely on the provider. So, the  third-party could abuse usage over the cloud-services and get user sesitive data! Which can harm the GDPR rules over personal data that could be stored within the future in this application.

&nbsp;
&nbsp;

## What are the needs for this project with Cloud-hosting?

### Google cloud

<table align = center>
  <tr>
    <th width="200">
    </th>
    <th width="600">
      Explaination of usage
    </th>
    <th width="600">
      Average Costs €
    </th>
  </tr>
  <tr>
    <td>
      Autoscaling
    </td>
    <td>
      Maximizes the application reposiveness by scaling up the cluster automatically when needed.
      It is a Infrastructure feature that can either horizontally or vertically scale up the cluster.
    </td> 
    <td>
      No given costs, since it charges the company or user the cost it is using. So, if suddenly the website gets one hundred thousand requests. It scales automatically up.
    </td> 
  </tr>
  <tr>
    <td>
      Cloud Databases 
    </td>
    <td>
      <p>The cloud database comes with encryption over data that gets stored in the cloud database. And is over  <code>SSAE 16, ISO 27001</code> and <code>PCI DSS  complaint.</code>
      It provides a 99,95% availability of access and functionality anywhere in the world. 
      And can also automatically replicate itself to reduce the number of overloading.    
      </p>
    </td>
    <td>
      €10.95 euros a month
    </td> 
  </tr>
  <tr>
    <td>
      Registry and hosting
    </td>
    <td>
      Needed for hosting and deploying the Kubernetes cluster to the cloud environment. 
    </td>
    <td>
      €53.44 for hosting the environment with using kubernetes. Where the access to <code>1vCPU</code> and <code>3,75 GB of RAM memory</code> is given.
    </td> 
  </tr>
  <tr>
    <td>
      Self-signed certificate
    </td>
    <td>
      Needed to make everything secure by having <code>HTTPS</code>. So that the connection between services and gateways have a encrypted connection.
    </td>
      <td>
        € free of costs.
    </td>
  </tr>
</table>

&nbsp;
&nbsp;

### Azure cloud

<table align = center>
  <tr>
    <th width="200">
    </th>
    <th width="600">
      Explaination of usage
    </th>
    <th width="600">
      Average Costs €
    </th>
  </tr>
  <tr>
    <td>
      Autoscaling
    </td>
    <td>
      Maximizes the application reposiveness by scaling up the cluster automatically when needed.
      It is a Infrastructure feature that can either horizontally or vertically scale up the cluster.
    </td> 
    <td>
      No given costs, since it charges the company or user the cost it is using. So, if suddenly the website gets one hundred thousand requests. It scales automatically up.
    </td> 
  </tr>
  <tr>
    <td>
      Cloud Databases 
    </td>
    <td>
      In Azure, all newly created databases are encrypted by default and the database encryption key is protected by a built-in server certificate. Also access protection can be setup to even more limit the numbers of people that can have access to the database. 
      </p>
    </td>
    <td>
      €12,- euros a month
    </td> 
  </tr>
  <tr>
    <td>
      Registry and hosting
    </td>
    <td>
      Needed for hosting and deploying the Kubernetes cluster to the cloud environment. 
    </td>
    <td>
      €0,097 per cluster per hour
    </td> 
  </tr>
  <tr>
    <td>
      Self-signed certificate
    </td>
    <td>
      Needed to make everything secure by having <code>HTTPS</code>. So that the connection between services and gateways have a encrypted connection.
    </td>
      <td>
        € free of costs.
    </td>
  </tr>
</table>

&nbsp;
&nbsp;

## Options as Cloud-providers

<table align = center>
  <tr>
    <th width="150">
    </th>
    <th>
        <img src="https://miro.medium.com/max/1400/1*b_al7C5p26tbZG4sy-CWqw.png" alt= "AWS cloud logo" width="400">
    </th>
    <th>
        <img src="https://www.apsitdiensten.nl/-/media/handleidingen/microsoft-azure-logo.png?h=514&w=800&hash=6BF9131B8E320F0262F4DF035C0B4F0B" alt= "Azure cloud logo" width="400"></a>
    </th>
    <th>
        <img src="https://www.freecodecamp.org/news/content/images/2020/10/gcp.png" alt= "Google Cloud logo" width="400"></a>
    </th>
  </tr>



  <tr>
    <td align = center>
      <strong>Company Name:</strong>
    </td>
    <td align = center>
      Amazon Web Services
    </td>
    <td align = center>
      Azure Cloud Services 
    </td>
    <td align = center>
      Google Cloud Services
    </td>
  </tr>



  <tr>
    <td align = center>
      <strong>Student credits</strong>
    </td>
    <td align = center>
      ❓/ ✅
    </td>
    <td align = center>
      ✅
    </td>
    <td align = center>
      ✅
    </td>
  </tr>



  <tr>
    <td align = center>
      <strong>Offer for students</strong>
    </td>
    <td align = center>
      <code>Education version of AWS</code>, where it is not specified what it offers. However, it offers courses for students and employees for companies. Furthermore, this option needs to registered with an credit-card.
    </td>
    <td align = center>
      <code>Offers an €100,- student credits</code> for their services, when registering the student e-mail. 
      According to Fontys both normal email and FHICT email work for registering to this student deal!  
    </td>
    <td align = center>
      Google Cloud provides a free trial account option, along with <code>$300 credit.</code> And this is only available for 90 days!
    </td>
  </tr>



  <tr>
    <td align = center>
      <strong>Most popular cloud provider (StackOverFlow)</strong>
    </td>
    <td align = center>
        <h3>🥇</h3>
    </td>
    <td align = center>
       <h3>🥈</h3>
    </td>
    <td align = center>
       <h3>🥉</h3>
    </td>
  </tr>
</table>

&nbsp;
&nbsp;

## Popularity chard by StackOverflow

<div align = center>
  <img src="../img/StackOverFlow trend.svg" width="600"></a>
</div>

&nbsp;
&nbsp;

## Azure hosting and deployment

So I have chosen to host my application in Azure. The reason for this is due to the fact that Azure provides good documentation and support with .NET applications. This is beneficial because the microservices are primarily built with .NET framework.

So I have started out with creating a registry on the Azure environment and made a cluster for the needed services. 

&nbsp;
&nbsp;

<div align = center>
  <img src="../img/Cloud/Azure registry.png"></a>
</div>

&nbsp;
&nbsp;

# Sources:
* Fontys (n.d) Fontys.nl https://fhict.instructure.com/courses/12452/pages/cloud-services-theoretical-background?module_item_id=829969

* Chai, W., & Bigelow, S. J. (2022, November 10). cloud computing. Cloud Computing. https://www.techtarget.com/searchcloudcomputing/definition/cloud-computing

* (2022, December 3). StackOverflow. https://insights.stackoverflow.com/trends?tags=azure%2Camazon-web-services%2Cgoogle-cloud-platform%2Cdigital-ocean&_ga=2.65165606.945540501.1670098375-1087063840.1670098375

* What is cloud hosting. (n.d.). IBM. https://www.ibm.com/cloud/learn/what-is-cloud-hosting

* Hui, J. (2021, March 25). Azure Autoscaling: A Practical Guide. Spot by NetApp. https://spot.io/resources/azure-pricing/azure-autoscaling-a-practical-guide/

* AWS Educate. (n.d.). Amazon Web Services, Inc. https://aws.amazon.com/education/awseducate/

* Google Cloud. (n.d.). Cloud Computing Services  |. https://cloud.google.com/

* Cloud SQL for PostgreSQL, MySQL, and SQL Server  |  Cloud SQL: Relational Database Service  |. (n.d.). Google Cloud. https://cloud.google.com/sql/?utm_source=google

* Pricing Calculator. (n.d.). Microsoft Azure. https://azure.microsoft.com/en-us/pricing/calculator/?

* AWS Pricing Calculator. (n.d.). https://calculator.aws/

