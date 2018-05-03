# Node Token Authentication

This repo uses JSON Web Tokens and the [jsonwebtoken](https://github.com/auth0/node-jsonwebtoken) package to implement token based authentication on a simple Node.js API.

This is a starting point to demonstrate the method of authentication by verifying a token using Express route middleware.

## Requirements

- node and npm [https://www.dyclassroom.com/howto-mac/how-to-install-nodejs-and-npm-on-mac-using-homebrew](https://www.dyclassroom.com/howto-mac/how-to-install-nodejs-and-npm-on-mac-using-homebrew)
- postman [https://www.getpostman.com/apps](https://www.getpostman.com/apps)
- mongodb [https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)

## Usage

1. Clone the repo: `git clone https://github.com/mitni455/nodejs-jwt-authentication.git`
2. Install dependencies: `npm install`
3. Optional - Change SECRET in `config.js`
4. Optional - Add your own MongoDB database to `config.js`
5. Start the server: `node server.js`
6. Create sample user by visiting: `http://localhost:3333/setup`

Once everything is set up, we can begin to use our app by creating and verifying tokens.

### Getting a Token

Send a `POST` request to `http://localhost:3333/api/authenticate` with test user parameters as `x-www-form-urlencoded`. 

```
  {
    email: 'nick.mitchell@beamenergylabs.com',
    password: 'password'
  }
```

### Verifying a Token and Listing Users

Send a `GET` request to `http://localhost:333/api/users` with a header parameter of `x-access-token` and the token.

You can also send the token as a URL parameter: `http://localhost:3333/api/users?token=YOUR_TOKEN_HERE`

Or you can send the token as a POST parameter of `token`.
