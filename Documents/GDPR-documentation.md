
---

# GDPR documentation

Everything about the GDPR is described within this document.

---



### Lawful basis and transparency

* Art. 6 GDPR: Lawfulness of processing
* Art. 12 GDPR: Transparent information,communication and modalities for the exercise of the rights of the data subject.
* Art. 30 GDPR: Records of processing activities


Morvie as the application holds several data topics. These topics are personal data, movie data and user input data (such as user given reviews and ratings). So, this will explain what will be done with the personal data of our customers.

`Personal data` gets collected by the application in order to make it run operations. Only the username, password and a unique email address is required to create a personal account. And with the personal account the user would be able to create a feed within the forums about a movie. So, at registry the application will create a unique personal identifier so that the application can use this identifier to allocate the forums with the correct account. The email of the user will be used to make sure that the user can login and/or can perform a 'forgot my password' recovery whenever the user forgot this (possibility in the near future as a feature). And thus can recover the account. 

The operators of morvie can not see the personal information of the user since `keycloak` user management service uses a plugin that encrypts the personal information of the user. It is called `Secure Credentials Store - Vault SPI`. And by user roles only limited operators can access the encrypted personal information for development purposes and are qualified for accessing this section. 

The authentication service and the morvie application share a `single connection`. And that is when the user wants to login into the morvie system. Which is secure by a secure connection: `HTTPS`. And uses the secure way of authenticating: `OAuth2.0` in which the authentication service lets the user directly communicate with the authentication service for a token. And once it is valid, the user will receive a heavy encrypted by `RS456` token that contains an access and authorization-token. In which the user can perform operations. 

<div align = center>
    <img src = "https://miro.medium.com/max/808/1*1McvnvrW6wh37ECYpmTSxw.png">
</div>

&nbsp;

### Data processing and legal justifications.

Within the user registery form, there will be a `clear` and `big` text box in where the user is mandatory to read the usage and collection of user personal data over the email address and password. And will let the user continue after it fully red the usage over their information and collection. 

# Sources:

- GDPR.eu. (2022, May 26). GDPR compliance checklist. https://gdpr.eu/checklist/

- Fontys (2021). Cyber Security https://fhict.instructure.com/courses/11556/pages/reference-law-standards-and-compliance?module_item_id=680345