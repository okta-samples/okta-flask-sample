# Python Flask Quickstart Sample Code for Integrating with Okta using the Redirect Model

This repository contains a sample of integrating with [Okta](https://www.okta.com/) for authentication using [the redirect model in a Python Flask app](https://developer.okta.com/docs/guides/sign-into-web-app-redirect/python/main/).

Read more about getting started with Okta and authentication best practices on the [Okta Developer Portal](https://developer.okta.com).

This code sample demonstrates
* Configuring Okta
* Sign-in and sign-out
* Protecting routes
* Displaying user profile information from the ID Token

## Prerequisites

Before running this sample, you will need an Okta Integrator Free Plan account. To get one, sign up for an [Integrator account](https://developer.okta.com/login). Once you have an account, sign in to your [Integrator account](https://developer.okta.com/login). Next, in the Admin Console:

1. Go to **Applications > Applications**
2. Click **Create App Integration**
3. Select **OIDC - OpenID Connect** as the sign-in method
4. Select **Web Application** as the application type, then click **Next**
5. Enter an app integration name
6. Configure the redirect URIs:
- Accept the default redirect URI values:
- **Sign-in redirect URIs:** `http://localhost:5000/authorization-code/callback`
- **Sign-out redirect URIs:** `http://localhost:5000`
7. In the **Controlled access** section, select the appropriate access level
8. Click **Save**

### Where are my new app's credentials?

Creating an OIDC Web App manually in the Admin Console configures your Okta Org with the application settings. You may also need to configure trusted origins for `http://localhost:3000` in **Security > API > Trusted Origins**.

After creating the app, you can find the configuration details on the app’s **General** tab:
- **Client ID:** Found in the **Client Credentials** section
- **Client Secret:** Click **Show** in the **Client Credentials** section to reveal
- **Org URL:** Found in the **Issuer URI** field for the authorization server that appears by selecting **Security > API** from the navigation pane.

```text
ORG_URL=https://dev-133337.okta.com
CLIENT_ID=0oab8eb55Kb9jdMIr5d6
CLIENT_SECRET=NEVER-SHOW-SECRETS
```

## Get the Code

Grab and configure this project using `okta start flask`.

Follow the instructions printed to the console.

## Enable Refresh Token

Sign into your [Okta Developer Edition account](https://developer.okta.com/login/) to add a required setting to your Flask Okta app to avoid third-party cookies. Navigate to **Applications** > **Applications** and select "okta-flask-sample" application to edit. Find the **General Settings** and press **Edit**. Enable **Refresh Token** in the **Grant type** section. **Save** your changes.

## Run the Example

To run this application, install its dependencies:

```
pip3 install -r requirements.txt
```

With variables set, start your app:

```
python3 -m flask run --port=5000
```

Navigate to http://127.0.0.1:5000 in your browser.

If you see a home page that prompts you to login, then things are working!  Clicking the **Log in** button will redirect you to the Okta hosted sign-in page.

You can sign in with the same account that you created when signing up for your Developer Org, or you can use a known username and password from your Okta Directory.

> **Note:** If you are currently using your Developer Console, you already have a Single Sign-On (SSO) session for your Org.  You will be automatically logged into your application as the same user that is using the Developer Console.  You may want to use an incognito tab to test the flow from a blank slate.

## Helpful resources

* [Learn about Authentication, OAuth 2.0, and OpenID Connect](https://developer.okta.com/docs/concepts/)
* [Get started with Flask](https://flask.palletsprojects.com/en/2.0.x/quickstart/)

## Help

Please visit our [Okta Developer Forums](https://devforum.okta.com/).
