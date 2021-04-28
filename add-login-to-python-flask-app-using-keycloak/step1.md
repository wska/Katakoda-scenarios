
## Installing Python3 and pip

Python3 comes preinstalled on the running Ubuntu partition (18.04). However, we are going to need one additional package later on, and for this we will need Pythons dedicated package manager `pip`.

Install `pip` with the following code:
```
sudo apt install python3-pip
```{{execute}}

## Fetch Flask using pip

Fetch the Flask package for Python3, which we will use to create a basic Python API. We will also need an extension package for Flask called `flask_oidc` for some more advanced usage later on.

Install `flask_oidc` with the following code:

```
pip3 install flask flask_oidc
```{{execute}}

## Fetching the Docker Image for Keycloak

Docker comes pre-installed on the running Ubuntu partition (18.04). The last thing we need is the Keycloak Docker image, which you can obtain by performing:

```
docker pull quay.io/keycloak/keycloak:12.0.4
```{{execute}}