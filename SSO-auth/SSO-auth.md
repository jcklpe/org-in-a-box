# Single Sign-On Auth

**Single sign-on** (**SSO**) is an authentication scheme that allows a user to log in with a single ID and password to any of several related, yet independent, software systems. 


This is the core of the org-in-a-box project in a lot of ways. It helps tie a user identity to a bunch of different web-apps. 

This is necessary because otherwise, every-time you add an additional web app to your org you increase the number of usernames and passwords the user needs to remember AND you also increase the requirements for administrators to keep up with administrating stuff. 

There are a lot of different ways to build a SSO flow but here is the basic anatomy of the SSO Solutions Engine:

## SSO Solutions Engine: Anatomy

Examples: Auth0, Gluu, Keycloak, Shibboleth, Ping, Okta

### Identity

Who is this person?

#### Identity Standard

This is a protocol that has been agreed upon by people as the standardized way to build an identity. 

Examples: LDAP, Active Directories

#### Identity Standard Implementation (AKA Identity Provider)

This is the actual implementation of a standard in code. Often when people refer to Identity Providers by the standard used but there are often several different implementations of Identity Standards by different private-companies/FOSS-projects, so it's helpful to distinguish between the two. 

Examples: Gluu LDAP server, Shibboleth Identity Provider

### Authentication

Is the person allowed in?

#### Authentication definition language

This is a specific syntax used for defining  the authentication definition. 

Example: SAML

#### Authentication Definition/Standard

This is the protocol that has been agreed upon by people to determine the authentication process. 

Examples: Shibboleth, OpenID

### Authorization

What privileges is the person allowed? 

#### Authorization/Access-Delegation Standard

This is the protocol agreed upon to process authorization

Examples: Oauth

#### Authorization Standard Implementation/Server

This is the specific implementation of the standard

Examples: Gluu oxAuth

## What's the difference between authentication/authorization? 

Imagine that getting into a web app is like getting into a house. Authentication is like having a friend lend you their key so you can get into their house. Authorization determines what you are allowed to do in the house, what rooms you can go into, whether or not you can kick your feet up on the couch etc. 

You can have authentication without authorization, but most SSO systems are going to have both. 

Here's [an article](https://spin.atomicobject.com/2016/05/30/openid-oauth-saml/) that explains more in depth. 

## Primary division in SSO solution engines: Shibboleth/SAML versus OpenID Connect

### Comparisons between OIDC and Shibboleth/SAML:

- https://www.gluu.org/blog/oauth-vs-saml-vs-openid-connect/
- https://identityblog.switch.ch/2016/03/08/openid-connect-meets-saml-and-shibboleth/

### Notes:

- OIDC is an OpenID authentication layer built ontop of a OAuth2 authorization layer
- The choice seems to be primarily between Shibboleth and OIDC. 
- OIDC is the more modern of the two and seems to have a lot of momentum behind it and is used by Google, Microsoft, Paypal, AOL, Salesforce and a bunch of others. 
- OIDC relies on SSL for encryption stuff
- OIDC uses a JSON Web Token.
- SAML and OpenID 2.0 use XML
- OIDC can work with both browser and mobile app integrations while SAML appears to be limited to just web
- SAML website is: https://www.oasis-open.org/standards#samlv2.0

OIDC website is: https://openid.net/connect/faq/

### Factors to consider in making comparisons between the two:

- Where is the puck going, and how do we skate to where it’s going?
- Developer ease of use
- Compatibility with web apps? Jitsi doesn’t support OIDC but it does support SAML



## Further Reading:

- [What Is and How Does Single Sign-On Authentication Work?](https://auth0.com/blog/what-is-and-how-does-single-sign-on-work/)
- [Federated Identity vs SSO](https://www.okta.com/identity-101/federated-identity-vs-sso/)
- [What is SSO and why your apps should support it](https://www.okta.com/blog/2019/05/what-is-federation-and-why-should-your-apps-support-it/)
- [Ory Project](https://www.ory.sh/hydra/docs/oauth2/)

