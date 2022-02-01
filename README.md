# Python Flask Quickstart Sample Code for Integrating with Okta using the Redirect Model

This repository contains a sample of integrating with [Okta](https://www.okta.com/) for authentication using [the redirect model in a Python Flask app](https://developer.okta.com/docs/guides/sign-into-web-app/python/main/).

Read more about getting started with Okta and authentication best practices on the [Okta Developer Portal](https://developer.okta.com).

This code sample demonstrates
* Configuring Okta
* Sign-in and sign-out
* Protecting routes
* Displaying user profile information from the ID Token

## Getting started

To run this example, run the following commands:

```shell
git clone https://github.com/oktadev/okta-python-quickstart.git
cd okta-python-quickstart
pip install -r requirements.txt
```

## Create an OIDC application in Okta

Create a free developer account with the following command using the [Okta CLI](https://cli.okta.com/):

```shell
okta register
```

If you already have a developer account, use `okta login` to integrate it with the Okta CLI.

Provide the required information. Once you register, create a client application in Okta with the following command:

```shell
okta apps create
```

You will be prompted to select the following options:
* Type of Application: **1: Web**
* Redirect URI: `http://localhost:8080/authorization-code/callback`
* Logout Redirect URI: `http://localhost:8080`

The Okta CLI created an `.okta.env` file in your current directory. This file includes your Okta domain, client ID, and client secret:

```
export OKTA_OAUTH2_ISSUER=https://${yourOktaDomain}/oauth2/${authorizationServerId}
export OKTA_OAUTH2_CLIENT_ID=${clientId}
export OKTA_OAUTH2_CLIENT_SECRET=${clientSecret}
```

Create a `.env` file with the following details:

```
OKTA_DOMAIN={yourOktaDomain}
CLIENT_ID={clientId}
CLIENT_SECRET={clientSecret}
```

Start the app by running

```shell
python3 -m flask run --port=8080
```

## Helpful resources

* [Learn about Authentication, OAuth 2.0, and OpenID Connect](https://developer.okta.com/docs/concepts/)
* [Get started with Flask](https://flask.palletsprojects.com/en/2.0.x/quickstart/)

## Help

Please visit our [Okta Developer Forums](https://devforum.okta.com/).
