
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
    <li><a href="Security"> ➤ Security</a></li> 
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

&nbsp;
&nbsp;

<h1 id = "Security">Security within DevSecOps!🦾</h1> 

### Usage of secrets within the pipelines.
For security within the pipeline, there are a several things I kept in mind. To make sure that the CI/CD pipeline performes the operations in a safe way I decided to do a small investigation of the industry standards. 

For the security maintainance I did the following items to make sure that the pipeline is properly secured:

- **Usage of environment variables**:

   These are used to make the pipeline more secure and not to expose sensitive credentials to the public. For this I used GitHub feature: enviromental variables. And during the CI or CD-pipeline these variables are used whenever the credentials are matching. To give an example, see the image below:

<div align = center>
  <a href = "https://github.com/Morvie/FeedMessages/settings/secrets/actions"><img src="../img\DevOps\Secrets-repo.png" alt= "CodeCov-logo" width="700" ></a>
</div>

&nbsp;

These variables are implemented into the ${{ secrets.environmental variable }} parts and take the matching secrets and paste it in there without exposing any credentials.

```yml
  deploy:
    needs: [build, test]
    runs-on: ubuntu-latest    
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Login to Docker Hub
        uses: docker/login-action@v2
        with:
          username: ${{ secrets.DOCKER_HUB_USERNAME }}
          password: ${{ secrets.DOCKER_HUB_ACCESS_TOKEN }}
      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v2
      - name: Build and push
        uses: docker/build-push-action@v3
        with:
          context: .
          file: ./Dockerfile
          push: true
          tags: ${{ secrets.DOCKER_HUB_USERNAME }}/feedmessages:latest
```
&nbsp;

### Static code analysis.
In order to write good and secure code, I implemented several tools to assure the quality of the code. The tools I have used are: 
- DependaBot
- SonarCloud
- Snyk

With SonarCloud I implemented this into the CI-pipeline to check the code quality as seen in the imagine below: And does it show the code-smells, security issues and possible bugs.

<div align = center>
  <a href = "https://github.com/Morvie/FeedMessages/settings/secrets/actions"><img src="../img\DevOps\SonarCloud-security.png" alt= "CodeCov-logo" width="700" ></a>
</div>
<div align = center>
  <a href = "https://sonarcloud.io/project/issues?resolved=false&types=CODE_SMELL&id=Morvie_Forums.API"><img src="../img\DevOps\Security-scanning.png" alt= "CodeCov-logo" width="700" ></a>
</div>

I also used dependabot for security tracking of code, and if there are issues found it gets marked as issue within the GitHub repository. The developers also receive a notification on the email, so the security issue gets solved as fast as possible. As well as updates on version packages and frameworks which are used within the project. However, not all new versions are needs since for .NET the updated also apply for .NET7 which is not supported for .NET6.

<div align = center>
  <a href = "https://github.com/Morvie/Morvie-Frontend/security/dependabot"><img src="../img\DevOps\Dependabot-security.png" alt= "CodeCov-logo" width="700" ></a>
</div>
<div align = center>
  <a href = "https://github.com/Morvie/Morvie-Frontend/pulls"><img src="../img\DevOps\dependabot-versions.png" alt= "CodeCov-logo" width="700" ></a>
</div>

&nbsp;

### KubeLinter.

I also used the KubeLinter, which is an Open-Source tool in the CI-pipeline which checks `all Kubernetes YML files`.  For this I needed to configure two YML files which each define the scope of this tracker. And I use this to validate all used YML files for Kubernetes. To ensure I don't use bad practices or errors in Kubernetes for hosting.

```yml
name: Check Kubernetes YAMLs with kube-linter

on:
  # Note that both `push` and `pull_request` triggers should be present for GitHub to consistently present kube-linter
  # SARIF reports.
  push:
    branches: [ main ]
  pull_request:

jobs:
  scan:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2

      # This prepares directory where github/codeql-action/upload-sarif@v1 looks up report files by default.
      - name: Create ../results directory for SARIF report files
        shell: bash
        run: mkdir -p ../results

      - name: Scan yaml files with kube-linter
        uses: stackrox/kube-linter-action@v1.0.4
        id: kube-linter-action-scan
        with:
          # Adjust this directory to the location where your kubernetes resources and helm charts are located.
          directory: k8s/deploy.yml
          # Adjust this to the location of kube-linter config you're using, or remove the setting if you'd like to use
          # the default config.
          config: k8s/.kube-linter-config.yml
          # The following two settings make kube-linter produce scan analysis in SARIF format which would then be
          # made available in GitHub UI via upload-sarif action below.
          format: sarif
          output-file: ../results/kube-linter.sarif
        # The following line prevents aborting the workflow immediately in case your files fail kube-linter checks.
        # This allows the following upload-sarif action to still upload the results to your GitHub repo.
        continue-on-error: true

      - name: Upload SARIF report files to GitHub
        uses: github/codeql-action/upload-sarif@v2

      # Ensure the workflow eventually fails if files did not pass kube-linter checks.
      - name: Verify kube-linter-action succeeded
        shell: bash
        run: |
          echo "If this step fails, kube-linter found issues. Check the output of the scan step above."
          [[ "${{ steps.kube-linter-action-scan.outcome }}" == "success" ]]
```

&nbsp;


<h1 id = "CD-pipeline">Deployment to Azure!👾</h1> 


