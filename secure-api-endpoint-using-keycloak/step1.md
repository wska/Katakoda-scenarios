
## Installing python3 and pip
First off, install Python3 and its dedicated package-manager, pip.
```
yum install python3
yum install python3-pip
```{{execute}}

## Fetch Flask using Pip
*what is flask*
Fetch the flask package for Python3, which we will use to create a basic Python API.
```
pip3 install flask
```{{execute}}

## Fetching the Docker Image for Keycloak
Docker comes pre-installed with the current Ubuntu image we are using (18.04). The last thing we need is the Keycloak docker image, which you can obtain by performing:

```
docker pull quay.io/keycloak/keycloak
```{{execute}}