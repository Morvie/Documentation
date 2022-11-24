---

<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a>
    <img src="img\logo.png" alt="Logo" width="250" height="250">
  </a>

  <h3 align="center">Technical Documentation</h3>

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

# :mailbox_with_mail: Content within this document

Within this document, all technical implementation designs will be explained. So, as reader, you can expect several technical implementation details within this document.

Keep in mind, however we try to keep this document up to date, it could happen that the implementation differs from the beforehand made designs and sketches.

<br/> 

<strong>Project description</strong>

With an enormous numbers of enterprise software nowadays the project possibilities are endless.  
So, during the first few weeks I oriented within possible “Enterprise software” products and chose a few possible and fun project ideas.

For this semester my choice for enterprise software for my project would be: 

A clone of IMDB/rotten tomatoes. where the user can browse through films and series and leave a rating. With additional features later. 

This would be a good fit because the project has the possibility to be extended. And it reaches a relatively large target audience: films and series buffs.

<br/>

<strong>What to expect</strong>

Within this document all technical design choices will be explained. The goal behind this is to explain the project structure for the upcoming future developers, who will work on this project.

Within this project, the technical will be explained in a detailed way. 
The reader will receive a generic overview over the made components. Furthermore, will this document contain explanation over the database data-structure design (known as ERD).  

---

### :hammer_and_wrench: Programming languages and tools :

<h4><strong>Back-end</strong></h4>

For this enterprise software application, the choice for a programming language must be made. Because this application is required to have a scalable architecture within the backend, the backend programming language does not matter that much, since we the programmer can choose it preferred the implementing programming language for the targeted microservice.

For this application the backend programming language would be generally written in C Sharp. This choice is based on a personal learning goal; during the internship, I used functional programming a lot. And so, I wanted to use an OOP language for this semester and master the programming language: C sharp. My goal for this semester is to develop my knowledge about this programming language and gain more experience.

<div align=center>
  <img src="https://raw.githubusercontent.com/devicons/devicon/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/csharp/csharp-original.svg" title="Csharp" alt="Csharp" width="100" height="100"/>&nbsp;
  <img src="https://raw.githubusercontent.com/devicons/devicon/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/dotnetcore/dotnetcore-original.svg" title="dotnet" alt="dotnet" width="100" height="100"/>&nbsp;
</div>
<br/>

<h4><strong>Front-end</strong></h4>
For the front-end application where the actor of this application can experience the application the programming language will be: React.js.
Personally, I don’t have any experience with React.js and do I rely on my knowledge about a similar front-end JavaScript framework: Vue.js. And am I able to use React.js with the superset of JavaScript: TypeScript, which I also use in the backend. So, I am expecting to not experience a very steep learning curve within the development phase.

My choice to learn something new among the front-end frameworks is due to two reasons. 
1.	Vue.js is not as popular as React.js and does not have as many features that React.js offers. (Think about mobile development, reusable components etc.)
2.	For the group project we are planning to use React.js, which can be beneficial to reuse some components for this project.

<div align=center>
    <img src="https://raw.githubusercontent.com/devicons/devicon/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/react/react-original.svg" title="React" alt="React" width="100" height="100"/>&nbsp;
</div>
</br>

<h4><strong>Databases</strong></h4>



---

### :calling: C4-model
<h4><strong>Level 1:[System overview]</strong></h4>

In the design, I choose to make use of the C4-model to design the application structure. With help of the C4-model, I can clarify every system, container, component and as final the classes within the C4-model in detail. In this subject, all levels of the C4-model will be explained.
	

Within level one in the C4-model, the software program, external software systems and users are showcased. 

The user roles within this application are viewed as followed:

- ```User (Could be a psychologist/expert or visually) ```

- ```Administrator (Additional rights and functionalities within the application) ```


With two external systems attached to this system, it would help beneficial to improve content to this application. With usage of The Movie Database (TMDB), I can get content to the application about films and series. 

And with help of Auth0, users can log in and use several external services to log in within this application and use it.
<br/>

<h4><strong>Level 2: [Container overview]</strong></h4>

Within the Morvie application the following the system is getting split in multiple containers that support as one system. Below there will be explained what containers this system contains:

The system from figure 1: <strong>“[Level 1: System context]”</strong> is split in multiple components. The system contains now the following components:
<br/>

**Web application.**

 ```This is the container where the actors can interact with the system. This is visual part of the application and communicates with the back-end component. ```

**API Gateway.**


```This component of the application separates the front-end with the back-end components. The API-gateways has all endpoints of the back-end components and communicates with the front-end which it wants to use. But for security reasons the front-end does not know which components and endpoints there are in the back-end. This proves also to be good for scalability.```

