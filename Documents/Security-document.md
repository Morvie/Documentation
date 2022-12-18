
---

<a name="readme-top"></a>

<!-- PROJECT LOGO -->


<div align="center">
  <a>
    <img src="https://raw.githubusercontent.com/Morvie/Documentation/main/img/logo.png" alt="Logo" width="250" height="250">
  </a>

  <h3 align="center">Security document.</h3>

  <p align="center">
    <br />
    <a href="https://github.com/orgs/Morvie/repositories"><strong>View repositories»</strong></a>
    <br />
    <br />
    <a href="https://morvie-frontend-alpha.vercel.app/">View Demo</a>
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
    <li><a href="#Introduction"> ➤ Introduction.</a></li>
    <li><a href="#OWASP"> ➤ OWASP Top 10</a></li>
    <li><a href="#CIA"> ➤ CIA-Model</a></li>
    <li><a href="#Keycloak"> ➤ Keycloak authentication manager</a></li> 
    <li><a href="#GitHub actions"> ➤ GitHub actions security</a></li>
    <li><a href="#Infrastructure"> ➤ Infrastructure security</a></li>
    <li><a href="#references"> ➤ Links</a></li>
  </ol>
</details>
<br/>

---

<h1 id = "OWASP">Checklist with OWASP Top 10!🔐</h1> 

On this research I will explain about the OWASP top 10. This will be implemented to research about possible cyber risks and measurements I want to perform to secure my applications against possible threats. 

&nbsp;

<div align = center>

![](../img/Aspose.Words.f33ffc15-76a1-44a7-b085-29765b1ee53d.001.png)
#### Source from: | [https://owasp.org/Top10/assets/mapping.png](https://owasp.org/Top10/assets/mapping.png)

</div>


&nbsp;
&nbsp;

## Threats of OWASP top 10 2021!
|**Number of Threat.**|**Short explanation** |**How to prevent this within the application?**|
| :- | :- | :- |
|A01: 2021 – Broken Access Control|<p>The most common vulnerability that occurs within applications is the Broken Access Control (BAC). This vulnerability lets users perform unauthorized functions that does not belong to their role within the application. And can lead to unauthorized information disclosure, modifications to the application or even worst: destruction of all data within the application.</p><p></p><p>This vulnerability can occur by a violation of privilege, roles or users. So, users who should not get authorized should be denied for access.</p><p></p>|<p>The main prevention of the Broken Access Control should be that the attacker cannot modify the access control check or metadata. Within my application, I was planning to use a third-party authentication/authorization software such as OAuth2.0 or Auth0 to prevent possible faulty implementation. This software has been specialized in developing secure authentication and authorizations for software applications.</p><p></p><p>- Minimalize Cross-Origin Resource Sharing (CORS) usage within the application.</p><p></p><p>- Make sure that the file metadata such as. git and back-up files are not stored within the web roots server. (Cloud hosting)</p><p></p><p>- Set up a limiter on the API and controller access to minimize the harm of automated attack tooling. (API-gateway).</p><p></p><p>- Alert admins when users have repeated failures on login. </p><p></p><p>- Session identifiers should be invalidated after logout. Thus, JWT-tokens or other authentication tokens should be removed or invalid after the user logs out of the system.</p><p></p>|
|A02: 2021 – Cryptographic failures|<p>The cryptographic failure was known as sensitive data exposure, and determines the protection needs of data in transit and at REST. Example given passports, credit card number, personal information etc. need more protection than a regular data storage. </p><p></p><p>This is due to data privacy laws such as EU’s data law, GDPR and PCI DSS. This vulnerability scopes on the lack of security on sensitive data and could occur in different places within the application.</p>|<p>- Do not store sensitive data unnecessarily and discard as much as possible after use. So, that the application does not store and violate the laws of GDPR etc.</p><p></p><p>- Encrypt all sensitive data within the REST API during transfers. So, that during a leak or similar, the data won’t be exposed so easily.</p><p></p><p>- Encrypt all data in transit with security protocols such as TLS and HSTS. And do not use legacy protocols such as FTP and SMTP. Since these are not secure and never build for security of data transfer, and attacks such as spoofing, sniffing and brute force attacks.</p><p></p><p>- Store password using salted hashing functions with a work factor, Argon2, scrypt, BCrypt or PBKDF2.</p><p>	</p>|
|A03: 2021 – Injections|<p>This is rather a category of a few different types of attacks. This concludes the following attacks to this list: </p><p></p><p>- Interceptor injections</p><p>- Cross-site Scripting (XSS)</p><p>- External control of file name/path.</p><p></p><p>The interceptor injections are attacks like: SQL injection, EL injection and some more. The target of the injection is to intercept or gain information about a certain target. The target is mostly sensitive information that should not be exposed. </p>|<p>- This can be prevented by using an Object Relation Mapping tool (ORM) for making query-statements to the database. (Sidenote: When there is an unexpected need of using writing queries. Make sure of using parameterized queries.</p><p></p><p>- Make sure to use a server-side input validation.</p><p></p><p>- Making use of LIMIT and other SQL controls within queries to prevent mass disclosure of records in an event as SQL injection.</p><p></p><p>- Source code review to detect possible vulnerabilities to injections. And automate testing of parameters, headers, URL, cookies, JSON, SOAP and XML data inputs.</p><p></p><p>- Implement security testing tools into the CI/CD pipeline. Which check for injection flaws within the application. Before it goes into production deployment.</p><p></p><p></p>|
|A04: 2021 – Insecure design|<p>This vulnerability is new within the list of ‘OWASP Top 10’ and represents as insecure design. With an insecure design the chance of system abuse is high which hurts the business. The design lacks in validation or limiting requests of the user, which allows the user to abuse the system. </p><p></p><p>An example given:</p><p>*“*Scenario #2: *A cinema chain allows group booking discounts and has a maximum of fifteen attendees before requiring a deposit. Attackers could threat model this flow and test if they could book six hundred seats and all cinemas at once in a few requests, causing a massive loss of income.” – OWASP top 10 AO4-2021: Insecure design.*</p><p></p>|<p>- Test application functions by using unit and integration tests. So, the critical points of the application get tested against threat model. And the application gets tested against possible misfunction.</p><p></p><p>- Use threat modeling for critical authentication, access control, business logic and key flows. </p><p></p><p>- Make tier layer segregation on the application and network layers so that the right protection could be implemented on the targeted layer.</p><p></p><p>- Limit the resource consumption by users of service within the application.</p><p></p>|
|A05: 2021 – Security misconfiguration|<p>Security misconfiguration is a vulnerability that makes the application vulnerable by missing appropriate security hardening, features and settings. This normally occurs by humans who change settings on the computer and or system so, the system is exposed and don’t leave it back on the secured settings. </p><p></p><p>Also, the software usage of external components could be outdated or vulnerable and comes with security risks.</p>|<p>- Using a minimal platform without any unnecessary features, components and frameworks. When something is not used, better remove it. So, the application does not have a security risk.</p><p></p><p>- Conclude review and update on configurations and implement a package reviewer on GitHub actions CI/CD pipeline actions.</p><p></p><p>- Make the application easy and fast to deploy to different environments. So, this can be automated and minimized the effort of setting up new secure environments.</p><p></p><p>- Make sure unnecessary features are disabled, this could harm the application of its infrastructure. This can be unnecessary ports, services, pages, accounts and privileges. This occurs within the deployment as the application its selves. </p><p></p>|
|A06: 2021 – Vulnerable and outdated components|<p>This vulnerability is likely to be caused by not updating and using wrong libraries. By using the wrong version of library or anything related, the chances of getting malware or unwanted threats are likely higher then upgrading it. </p><p></p><p>So, it is not an attack itself, but it is one of the main causes’ attacks can occur. Due to black hats finding ways to infiltrate through a faulty version of a system.</p>|<p>- Remove unused dependencies, unnecessary features, components, files and documentation. For dependencies, a tool can be used within the CI/CD pipeline on GitHub actions for monitoring. This will reduce the risk of being a victim of possible foreseeable attacks.</p><p></p><p>- Only obtain components from official sources over secure links. By not doing this, the chance of getting malicious malware is higher, and the risk of getting malware on the environment is high.</p><p></p><p>- Make sure to be aware of possible new releases on operation systems (OS), servers, database management system (DBMS), API, runtime environments and libraries.</p><p></p>|
|A07: 2021 – Identification and Authentication failures|<p>This is a vulnerability within the application where the user’s identity, authentication and/or session management lacks protection and is vulnerable against authentication attacks such as brute-force attacks and other similar attacks.</p><p></p><p>Also does the application lack in security prevention such as tokens, protected URL’s or encryption.</p><p></p><p>But also, the attacker can use obtained passwords from earlier attacks, and use automated attacks against a few different websites. So, eventually the attacker gets a notification on which websites are using the same password. This could happen due to weak hashing algorithm and could encrypt the user credentials.</p><p></p>|<p>- Implement a weak password check where input can be tested against the top 10.000 worst passwords of all time. In order to prevent an automated or brute force attack.</p><p></p><p>- Delay on failed login attempts, so that the brute force or automated attacks are denied/delayed. And on repeating attempts alarm the moderator so, actions can be performed.</p><p></p><p>- Session Identifier should not be included within the URL parameter. This is a bad practice. And should be secured stored and made invalid after logout, idle and absolute timeouts.</p><p></p>|
|A08: 2021 – Software and data integrity failures|<p>Software and data integrity failures occur when the infrastructure and code implementation lack the ability to protect the code against integrity violations.</p><p>This leaves the system vulnerable against several attacks such as:</p><p>- Denial of Service (DoS)</p><p>- Code Injection</p><p>- Command Execution</p><p></p><p>This attack happens when the attacker intercepts the request of the CI/CD pipeline and install malicious code within the test/build.</p><p></p>|<p>- Only use libraries such as NPM or Maven that are consuming trusted repository. By not doing this, the risk of malicious stuff is higher.</p><p></p><p>- Make sure the CI/CD pipeline has a proper segregation between actions and the integrity of the code flowing through the build and deploy process. </p><p></p><p>- Make sure within GitHub to be authenticate, so the data comes and goes to valid and trusted sources.</p><p></p><p>- The system should be thoroughly tested before deployment to the real users of the application. So, install a test-environment. </p>|
|A09: 2021 – Security logging and monitoring failures|<p>This vulnerability starts by faulty implementation of the security systems. In which the system fails to sufficiently log monitor or report security events. Making the applications detections on suspicious activities non-existing and let the attacker exploit the application without any troubles or performed security measurements.</p><p></p><p>By faulty monitoring and logging, the application gets more vulnerable to attacks as:</p><p>- Code injection</p><p>- Buffer overflow</p><p>- Command injection</p><p>- Cross-site scripting</p>|<p>- Make sure that all login, access control and server-side validation failure can be logged.  So, forensic analysis can identify suspicious or malicious account. This can be implemented by adding a logging feature.</p><p></p><p>- As a DevSecOps operator, I should be able to effectively monitor and alert on suspicious activities that are detected.</p><p></p><p>- By encoding the log data is encoded, so in case of a breach that the log data stays unharmed hopefully.</p>|
|A10: 2021 – Server-side request forgery |<p>This attack happens when the attacker intercepts the request of the CI/CD pipeline and install malicious code within the test/build.</p><p></p><p>So, it is not an attack itself, but it is one of the main causes’ attacks can occur. Due to black hats finding ways to infiltrate through a faulty version of a system.</p>|<p>- Validate all client-input data in order to prevent server-side request forgery. </p><p></p><p>- Disable HTTP redirections and do not click on one of these links.</p><p></p><p>- Enforce URL schema port and destination with an allowance list.</p>|

---

<h1 id = "CIA">Checklist with the CIA-model!👮🏼</h1> 

&nbsp;
&nbsp;

---

<h1 id = "Keycloak">Keycloak authentication manager!🔑</h1> 

In order to let the users of the application login and perform their own unique operations, I have considered a option: "do I want to use a access management solution in my application?" and so have I performed a research about the benefits of this.
So, there are two main competitors about access management solutions:
* Keycloak 
* Auth0

And do I have chosen for using Keycloak as an access management solution for my application. The main reason is that Keycloak provides more then Auth0 and so, the security options are more available.

So I started with setting Keycloak up in my `docker-compose` in order to make the relation work between the application and the keycloak service:

```YML
version: '3.4'

networks:
  backend:

volumes:
  keycloak-database:

services:
  keycloak-instance:
    image: quay.io/keycloak/keycloak:18.0.2
    container_name: "keycloak-instance"
    command: start-dev
    environment:
      - KEYCLOAK_ADMIN=admin
      - KEYCLOAK_ADMIN_PASSWORD=admin
      - KC_DB=postgres
      - KC_DB_USERNAME=keycloak
      - KC_DB_PASSWORD=keycloak
      - KC_DB_URL=jdbc:postgresql://keycloak-database:5432/keycloak
      
    volumes:
      - ./backup:/tmp/import
    ports:
      - "2222:8080"
    networks:
      - backend
    depends_on:
      - keycloak-database

  keycloak-database:
    image: postgres:14.2
    container_name: "keycloak-database"
    environment:
      POSTGRES_DB: keycloak
      POSTGRES_USER: keycloak
      POSTGRES_PASSWORD: keycloak
    ports:
      - "2223:5432"
    networks:
      - backend
    volumes:
      - keycloak-database:/var/lib/postgresql/data
```

And once it started up, I could access the keycloak instance from Docker🐳 on the following url: `http://localhost:2222/` where I could perform configuration operations! And do I have a keycloak database of `PostgreSQL database.`

I have performed an operation in which I create a keycloak realm called: `Morvie`, just like my application, where I am able to create public and private keys for JWT, security measures and user authentication/authorization configurations. And so focusses Keycloak on providing `high security measures and standards`, and do I have implemented the following features with it:

- Brute force detection
- ReCaptcha bot detection
- Usage of OAuth2.0 authentication principle.
- Usage of JWT tokens.
- Usage of PBKDF2 hashing algorithm for storing password credentials.

&nbsp;

### Brute force detection 🤖

In order to activate brute force detection, I have enabled a feature within keycloak under the realm:

<div align="center">
  <a>
    <img src="../img/security/Brute-force detection.png"/>
  </a>
</div>

&nbsp;

Once it is enabled, I could configure the login failure settins, wait times and etc. And how this works is that the black hat user triggers automated brute force attack, and the malicious machine 'guesses' with a dictionary of possible passwords on the password of the user. The username is often received by social engineering or human errors by the blackhat user. And by enabling this feature, the malicious machine is limited on attempts since the account gets locked out for a set amount of time.

&nbsp;

### reCAPTCHA bot detection 🤖
In order to protect the application against bots, who try to create a account within this application, is the application protected with `ReCaptcha`. ReCaptcha is a tool by `Google` which let users who are new or have suspicious activities perform a recaptcha challenge. If the users fails to complete this challenge, it may not create a new account. 

<div align="center">
  <a>
    <img src="../img/security/Recaptch-protection.png"/>
  </a>
</div>

&nbsp;

### User protection validation 🔐🖇️
The users of this application are required to make a password that is protected with requirements. The following requirements are set and required for the users who want to make a account.
- Minimal lowercase characters: 1
- Minimun length: 8
- Special characters: 1
- Not containing any email addresses.
- Hashing algorithm: PBKDF2-SH256
- Hashing iterations: 27500

As seen below within the keycloak configuration:

<div align="center">
  <a>
    <img src="../img/security/keycloak-password.png"/>
  </a>
</div>

&nbsp;

## Two Factor Authentication.

<div align="center">
  <a>
    <img src="../img/security/keycloak-2FA.png"/>
  </a>
</div>

The application uses a Two-Factor Authentication to authenticate users with a two factor operation. If the user wants to login, the user needs to fill in its username and password. And once it is succeeded by the application, the two factor authentication gets triggered and the user needs to use the google multifactor authentication mechanism and fill in a once-time code:
<table align = center>
  <tr>
    <th>
        <a href = "https://play.google.com/store/apps/details?id=com.azure.authenticator&hl=nl&gl=US"><img src="https://play-lh.googleusercontent.com/_1CV99jklLbXuun-6E7eCPR-sKKeZc602rhw_QHZz-qm7xrPdgWsJVc7NtFkkliI8No" alt= "Authenticator" width= "800"></a>
    </th>
    <th>
        <a href = "https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=nl&gl=US"><img src="https://play-lh.googleusercontent.com/oMv9o-L-mNKdyL3Hp6fvNwrhAyIYB1iP3p644hxN03oFU0R2oevnmxmCLF6FewjzZXU" alt= "Google Authenticator" width= "800"></a>
    </th>

  </tr>
  <tr>
    <td>
      Microsoft authenticator
    </td>
    <td>
    Google Authenticator
    </td>
  </tr>
</table>

<div align="center">
  <a>
    <img src="https://www.iphoned.nl/wp-content/uploads/2020/12/google-authenticator-accounts-overzetten-uitg.jpg"/>
  </a>
</div>


&nbsp;

## OAuth2.0 authentication.
Keycloak authentication service uses a high-level industry-standard protocol for authorization called: `OAuth2.0`. OAuth2.0 is a secure, open data sharing standards that secures authentication and authorization operations between services without revealing the user's identity or credentials. 

The way it works is that it enables applications to access each other's data without revealing user's identity or credentials and uses username and password tokens. It uses a `SSL Secure Sockets Layer` to ensure that data between services remain private.

Also does the accesstokens and refreshtoken, which are refreshed during times. Once the user is not-active, the refreshtoken' job is to shut down the session and let the user later on not be able to perform any operations later.

<div align="center">
  <a>
    <img src="../img/security/OAuth2.0.png"/>
  </a>
</div>

---

<h1 id = "GitHub actions">GitHub actions security tools🛸</h1> 

&nbsp;
&nbsp;

---

<h1 id = "Infrastructure">Infrastructure security🛣️</h1> 

- Azure database connection is secure by TLS1.2 encryption.
- Usage of HTTPS in Ingress controller.
- Usage of HTTPS in application.
- Usage of secrets within 
- Usage of secrets within the pipeline GitHub actions.

&nbsp;
&nbsp;

---

<h1 id = "references">Used sources🖇️</h1> 

&nbsp;
&nbsp;
