# Evolution of Identity

## Identity Management Approaches
### Per Application Identity Silo

each application often implemented its own identity repository, authentication, and authorization. Each application often had its own dedicated database or other storage in which user identities, credentials, and user profile data were stored, and each application prompted the user to log in and then validated the user’s credentials against its own repository of user information.

### Centralized User Repository

Directory services are optimized for information that is frequently read but infrequently modified, which is often the case for user identity data. Applications were able to use a directory service to store user data and credentials. It was also possible for an application to prompt a user to log in and validate the entered credentials using information in a directory service.

A centralized directory service also provided a single point of control at which to implement password policy or quickly terminate an identity if necessary. 👍

A directory service by itself did not maintain any sort of session for a user. so user still had to enter the credentials into each application’s login screen. 👎

### Early SSO Servers

Early SSO (Single Sign-on) servers leveraged the identity information in a directory service, but provided a layer on top of the directory service that maintained a session to remember users that had already authenticated.

#### How it works?

Application could redirect a user’s browser to an SSO server to have the user authenticated there and receive the authentication results in a secure, predetermined fashion. 

Users benefited from the ability to access multiple applications with a single authentication. Security teams appreciated that the user’s static directory password was only exposed to the SSO server, instead of to each application the user accessed. 👍

The interaction between applications and SSO servers was somewhat proprietary, and SSO products were often time-consuming to implement. 👎

### Federated Identity & SAML 2.0

SAML (Security Assertion Markup Language) provided a solution for web single sign-on across domains and federated identity. 

### WS-Fed

Web Services Federation Language (WS-Fed)

### OpenID

### OAuth 2.0 👌

The OAuth 2.0 version of the specification allows a user to authorize one application, known as a client (**the photo printing site**), to send a request to an API, known as a resource server (**the social media site**), on the user’s behalf to retrieve data at the resource server owned by the user.

#### How?

The application interacts with an authorization server which authenticates a user as part of obtaining their consent for the application to access their resources. The application receives a token which enables it to call the resource server on the user’s behalf. 

### OpenID Connect (OIDC) 👌

OAuth 2.0 + Authentication

Even if OAuth 2.0 authorization servers were capable of authenticating users, the framework did not provide a standard way to securely convey the identity of an authenticated user to an application. OIDC provided a solution for this need. OIDC was devised as a layer on top of the OAuth 2.0 protocol to provide information in a standard format to applications about the identity of an authenticated user.

## Standard Protocols

Why to use standard protocols

- As open standards, these protocols have been scrutinized for flaws by many people.
- These protocols are widely used, providing interoperability between your application and service providers which support the protocols.
- If you wish to access user profile data from services such as Google, you will have to use the standard protocols as implemented by these services. 
- using an existing protocol can save you time as many programming languages offer SDKs that support them. 