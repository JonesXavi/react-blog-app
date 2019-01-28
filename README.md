# Learnt in 2019 - [React OKTA Express Blog App]

Yay! The learning series still continues. What's this time?

Everyone of us should have had the headache of creating and managing a **login authentication**. It's always an extra work from the app's core functionality. So, I thought why not use **OAuth** or **OAuth 2.0** or even better **Open ID Connect** (built on top of OAuth 2.0) to make the authentication, authorization simple. I have used [OKTA](https://developer.okta.com/) service for authentication, authorization and user management for my app.

This is a simple blog where the user can add, edit or delete his post/content after authenticated via OKTA.

## Learnings

* [React 16](https://reactjs.org/) - Front-end.
* [Express JS](https://expressjs.com/) - Back-end.
* [Okta NodeJS OIDC Middleware](https://github.com/okta/okta-oidc-js/tree/master/packages/oidc-middleware) - Authentication.
* [Sequelize](https://github.com/sequelize/sequelize) - Storing and manipulating data
* [Epilogue](https://github.com/dchester/epilogue) - automatically generates REST endpoints and controllers from the Sequelize data models.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development.

## Prerequisites

Create an account in [OKTA](https://developer.okta.com/) which is a free service for managing user identities.
Once you've signed up for Okta, follow these steps below to configure it:

* Click **Application** on the navigation menu.
* Click the **Add Application** button.
* Select **Web** as the software, click the **Next** button.
* Enter the following information, then click the **Done** button.
    * Name: My Blog
    * Base URIs: http://localhost:3000/
    * Login redirect URIs: https://localhost:3000/authorization-code/callback

Once completed, create a ```.env``` file in the root directory and put the below code:

```OKTA_ORG_URL=<ORG URL>```

```OKTA_CLIENT_ID=<CLIENT ID>```

```OKTA_CLIENT_SECRET=<CLIENT SECRET ID>```

```REDIRECT_URL=<REDIRECT URL>```

```RANDOM_SECRET_WORD='<SUPER STRONG, WEIRD & RANDOM WORD>```

* OKTA_ORG_URL - Find this in the top right corner of OKTA dashboard.
* OKTA_CLIENT_ID, OKTA_CLIENT_SECRET - Find these under app's general page.
* REDIRECT_URL - ```https://localhost:3000/authorization-code/callback```.
* RANDOM_SECRET_WORD - A long, super strong, random word.

**NOTE**: The **RANDOM_SECRET_WORD** setting should be a random string you type out. Just bang on the keyboard for a second to output a long random string, and use that value. This value should never be checked into source control as it is used to manage the integrity of your user sessions. It must be kept private on your web servers and should be extremely hard to guess.

### Installing

1. Clone this repo to your local.
2. Do ```npm install``` inside the repo folder.
3. Do ```npm run start```.
4. Open [http://localhost:3000](http://localhost:3000) to view it in the browser.
