Welcome! This tutorial demonstrates how to secure an API endpoint using Keycloak running in Docker and hosting it on Katacoda. 

*The aim of this tutorial is to:*

* Showcase how to set up a simple Flask app in Python 3
* Introduce Oauth2, OpenID Connect and Keycloak
* Showcase how to set up Keycloak and host it using Docker
* Expand the Flask app to allow interaction with the Keycloak server and use it for login procedures for certain endpoints
 
*Information regarding the tools that we will be using:*
 
**Keycloak**

Keycloak is an open source software community project which is developed by Red Hat. It is founded on standard protocols that offers security solutions for applications, including SSO (”Single-Sign On”), social login and multifactor authentication. Furthermore, Keycloak supports technologies such as OpenID Connect and OAuth 2.0<sup>1,2</sup>. Keycloak is rather popular, due to its powerful and secure implementation and open-source nature. It is employed by many major corporations for authentication procedures and learning a bit about it could be an useful endeavour. Documentation can be found [here](https://www.keycloak.org/documentation).

**Flask**

Flask is a framework for Python that is used for building web applications<sup>3</sup>. If you're unfamiliar with the framework, we recommend you to check out [this](https://www.geeksforgeeks.org/python-introduction-to-web-development-using-flask/) source. Furthermore, you can access the official documentation [here](https://flask.palletsprojects.com/en/1.1.x/).

**Oauth2**

OAuth2 is a protocol for authorization which is used to grant applications delegated access to resources in place of a user, but in a secure manner <sup>4</sup>. Documentation can be found [here](https://oauth.net/2/).

**OpenID Connect**

OpenID Connect builds upon Oauth2, by adding an identity layer to it. Documentation can be found [here](https://oauth.net/2/).

Sources: 
1. https://www.keycloak.org/about 
2. https://www.thomasvitale.com/introducing-keycloak-identity-access-management/
3. https://www.geeksforgeeks.org/python-introduction-to-web-development-using-flask/
4. https://auth0.com/intro-to-iam/what-is-oauth-2/

