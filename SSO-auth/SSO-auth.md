# Single Sign-On Auth

**Single sign-on** (**SSO**) is an authentication scheme that allows a user to log in with a single ID and password to any of several related, yet independent, software systems. 


This is the core of the org-in-a-box project in a lot of ways. It helps tie a user identity to a bunch of different web-apps. 

This is necessary because otherwise, every-time you add an additional web app to your org you increase the number of usernames and passwords the user needs to remember AND you also increase the requirements for administrators to keep up with administrating stuff. 

There are a lot of different ways to build a SSO flow but here is the basic anatomy of the SSO Solutions Engine:

## SSO Solutions Engine

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

### What's the difference between authentication/authorization? 

Imagine that getting into a web app is like getting into a house. Authentication is like having a friend lend you their key so you can get into their house. Authorization determines what you are allowed to do in the house, what rooms you can go into, whether or not you can kick your feet up on the couch etc. 

You can have authentication without authorization, but most SSO systems are going to have both. 