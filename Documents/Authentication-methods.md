
---

<a name="readme-top"></a>

<!-- PROJECT LOGO -->


<div align="center">
  <a>
    <img src="https://raw.githubusercontent.com/Morvie/Documentation/main/img/logo.png" alt="Logo" width="250" height="250">
  </a>
    <h1>Research document</h1>
  <h3 align="center">Identity and Access Management-document</h3>

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


# OpenID Connect

<div align = "center">
    <img src = "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/OpenID_logo_2.svg/1200px-OpenID_logo_2.svg.png" width = "500">
</div>

### What is OpenID Connect?
- Open ID Connect is an `open-source authentication protocol` and is one of the latest security protocols available. It targets consumers to use authentication to validate the user and confirm the given credentials. The protocol is based on the OAuth 2.0-protocol and can use additional `JSON-webtoken (JWT)` to validate the usercredentials. And OAuth 2.0-protocol will validate the user permissions such as scopes and end-point discorvery. 

## Usage of external identity providers.

- With the use of `OpenID Connect` it is possible to use different external identity providers(idP) in to authenticate to the application. With the usage of keycloak, it is possible to set up the external identity providers to the application. And the main advantage of using this is that the application allows users to log-in with account-connections from social Identity Providers such as: `GitHub`, `Facebook`, `Twitter` and other social media platforms. 


<div align = "center">
<img src = "https://developer.okta.com/assets-jekyll/blog/illustrated-guide-to-oauth-and-oidc/authorize-tpotd-contacts-9f4dca35e4c91b5d808f65f64bb14cc40e7c701742f4b764c5baa8acfeb59020.jpg" height = "500">
</div>

With the usage of this social media login, the user is making usage of an OAuth2.0 workflow. So that means that OpenID connect does not only use JWT to identify the user, but also the OAuth2-protocol.

Within my keycloak instance, I configured this with GitHub:
<div align = "center">
<img src = "..\img\Security\OAuth-config.png">

Configuring the `OAuth2 workflow` within GitHub.

<br/>

</div>

<div align = "center">
<img src = "..\img\Security\OAuth-keycloak.png">
Configuring the OAuth2 workflow within keycloak for access to the workflow.
</div>

Once everything is configured correctly, users are able to login within keycloak!


<div align = "center">
<img src = "..\img\Application\Keycloak login.png">
There appears an option to login with GitHub for the user.
</div>

<div align = "center">
<img src = "..\img\Security\OAuth-login.png">
The user can login with its GitHub account and continue with the application!
</div>

---


# JWT 

This is a authentication standard that can be used to authenticate users within the application. With JWT it is a generated token by the authentication server. It contains information about the user (userID, email, username etc.) The information is formatted as a JSON format. The structure is as followed: 
- `HEADER` the place that conatins the algorithm and token type.
- `PAYLOAD` contains the payload of information about the user.
- `SIGNATURE`

The use-case of using this method is when you want to sent information to an untrusted client. In that way the client can verify the information within the payload itself. This way the user will store the information itself that is stored in the token.

With an in-build token expiration mechanism, the client will only be able to use the token for a period of time. After the time has expired, the client will not be able to use the token anymore. And from a security perspective, the client will be able by changing password, the expiration timer of the token. And thus use the previous tokens longer.

---

## OAuth2.0

With OAuth2.0 the users can obtain `Opaque` tokens. These tokens are not meant to be read by anyone hence only the issuer knows the format of the token. This token reference to the database entry with the data. This brings the disadvantage of user roles can be modified and the user will be able to the new roles. So, not good for untrusted clients.

OAuth2.0 stands for `Open Authorization` 2.0 which is designed to allow a website or application to access resources hosted by other web apps on behalf of the user. It is an `authorization protocol` and not a authentication protocol. In order to give the users access to the resources, OAuth2.0 uses `access tokens` to represent the authorization to access resources. For this access token, the token `JSON Web Tokens (JWT)` can be used to enable issuers to include data in the token itself.

With OAuth2.0, there are four different roles:
- `Client` 
- `Authorization server`
- `Resource owner`
- `Resource server`

1. The way OAuth2.0 works is the way that the user makes authorization request from the Authorization server. It provides an endpoint URL to send the access token or the authorization code.

2. The authorization server authenticates the Authorization server to grant access to resources.

3. The resource owner interacts with the authorization server to grant access.

4. The Authorization server redirects backs to the cliebt with either an Authorization code or Access Token depending on the grant type.

5. With the access token, the clinet requests access to the resource from the resource server (external identity provider).

<div align = "center">
<img src = "https://developer.okta.com/assets-jekyll/blog/illustrated-guide-to-oauth-and-oidc/authorize-tpotd-contacts-9f4dca35e4c91b5d808f65f64bb14cc40e7c701742f4b764c5baa8acfeb59020.jpg" height = "500">
</div>

---


# Sources 

* https://www.okta.com/nl/identity-101/whats-the-difference-between-oauth-openid-connect-and-saml/

* https://www.pingidentity.com/en/resources/identity-fundamentals/authentication-authorization-standards/openid-connect.html#:~:text=OpenID%20Connect%20(OIDC)%20is%20an,network%2C%20to%20authenticate%20their%20identities.

* https://developer.okta.com/docs/concepts/identity-providers/

* https://developer.okta.com/blog/2019/10/21/illustrated-guide-to-oauth-and-oidc

* https://supertokens.com/blog/oauth-vs-jwt

* https://auth0.com/intro-to-iam/what-is-oauth-2