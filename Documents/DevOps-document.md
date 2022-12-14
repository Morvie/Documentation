
---

<a name="readme-top"></a>

<!-- PROJECT LOGO -->


<div align="center">
  <a>
    <img src="https://raw.githubusercontent.com/Morvie/Documentation/main/img/logo.png" alt="Logo" width="250" height="250">
  </a>

  <h3 align="center"></h3>

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
    <li><a href="#introduction"> ➤ Introduction.</a></li>
    <li><a href="#CI-pipeline"> ➤ Continious integration visualised.</a></li>
    <li><a href="#Steps + Tools"> ➤ Steps and tools within the CI-pipeline.</a></li>
    <li><a href="#CD-pipeline"> ➤ Continious deployment</a></li>
    <li><a href="#getting-started"> ➤ Links</a></li>
  </ol>
</details>
<br/>

<h1 id="introduction">Introduction</h1>

Within this document all the general development circle of the GitHub actions will be explained. So, the DevSecOps circle of the Continious integration and Continious Deployment. 

All used tools, examples and how I did set it up will be explained within this document. And what the tools will cover throughout the development of the microservice.

---

<h1 id = "CI-pipeline">CI-pipeline visualised.</h1>
<div align = center>
  <a href = "https://github.com/Morvie/Forums.API/actions"><img src="../img\job.png" alt= "CodeCov-logo" width="700" ></a>
</div>

&nbsp;
&nbsp;


<h1 id = "Steps + Tools">Steps and tools within the CI-pipeline.</h1>
<h3>Tools</h3>
<p>The used tools within the CI-Pipeline the following tools are defined below. These tools all add up for a contribution. 

All tools are on a open-source subscription and require no money. But once the project gets extended, it will be required to purchase a subscription for some.
</p>

<table align = center>
  <tr>
    <th>
        <a href = "https://github.com/codecov"><img src="https://avatars.githubusercontent.com/u/8226205?s=200&v=4" alt= "CodeCov-logo"></a>
    </th>
    <th>
        <a href = "https://github.com/docker"><img src="https://avatars.githubusercontent.com/u/5429470?s=200&v=4" alt= "Docker"></a>
    </th>
    <th>
        <a href = "https://www.sonarsource.com/products/sonarcloud/"><img src="https://avatars.githubusercontent.com/u/39168408?v=4" alt= "SonarCloud"></a>
    </th>
    <th>
        <a href = "https://github.com/actions"><img src="https://avatars.githubusercontent.com/u/44036562?s=200&v=4" alt= "GitHub Actions"></a>
    </th>
    <th>
        <a href = "https://github.com/snyk"><img src="https://avatars.githubusercontent.com/u/12959162?s=200&v=4" alt= "Snyk"></a>
    </th>
    <th>
        <a href = "https://github.com/dependabot"><img src="https://avatars.githubusercontent.com/u/27347476?s=200&v=4" alt= "dependabot"></a>
    </th>
  </tr>
  <tr>
    <td>
    Code-reports and code-coverage gives the developer a mile-stone experience about the progress of code-coverage.
    </td>
    <td>
      Builds and pushes the code to DockerHub account. 
    </td>
    <td>
      Could also be used as code coverage, but primarily used for static code analysis.
    </td>
    <td>
      Used for making artifacts and making the artifact available for other CI-jobs.
    </td>
    <td>
      Used as a security monitoring feature were the developer gets weekly notifications about possible security issues.
    </td>
    <td>
      Used as a dependency monitoring feature were the developer gets weekly notifications about possible new releases.
    </td>
  </tr>
</table>



