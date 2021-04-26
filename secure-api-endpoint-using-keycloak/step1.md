
## Installing python3 and pip
Python3 comes preinstalled on the running Ubuntu partition (18.04). We are going to need one additional package later on, so we will need Pythons dedicated package manager: pip.

Install it with the following code:
```
sudo apt install python3-pip
```{{execute}}

## Fetch Flask using Pip
*what is flask*
Fetch the flask package for Python3, which we will use to create a basic Python API. We will also need an extension package for flask called flask_oidc for some more advanced usage later on:
```
pip3 install flask, flask_oidc
```{{execute}}



## Fetching the Docker Image for Keycloak
Docker comes pre-installed. The last thing we need is the Keycloak docker image, which you can obtain by performing:

```
docker pull quay.io/keycloak/keycloak:12.0.4
```{{execute}}