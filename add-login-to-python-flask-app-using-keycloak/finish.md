Congrats on setting up a login procedure for your simple flask application! What we did here is a rather basic variant of it, and there are many additional features available both through Keycloak and the flask_oidc library. One of the most notable one is the use of "roles", where some endpoints require elevated privileges in order to access them (such as a user not being able to access endpoints reserved for administrators!). 

If you are interested, you can read more on the official documentation here for *flask_oidc*:

> https://flask-oidc.readthedocs.io/en/latest/

And for Keycloak:

> https://www.keycloak.org/documentation

There are also multiple different addons and modules that can allow you set up authentication procedures using Keycloak. So if you use something like Django for Python (https://pypi.org/project/django-keycloak-auth/), or Node etc with Javascript (https://github.com/keycloak/keycloak-nodejs-connect). The point is that for any sufficiently popular framework with a purpose of creating a web application or API, there is very likely a complementary module or package for Keycloak support. Keycloak is rather popular, due to its powerful and secure implementation and open-source nature. It is employed by many major corporations for authentication procedures and learning a bit about it could be an useful endeavour. 

While Keycloak is the open source variant, there are also some enterprise versions of authentication service providers which are based upon Keycloak, such as Red Hat Single-Sign On (SSO) (https://access.redhat.com/products/red-hat-single-sign-on). 