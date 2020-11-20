# Node.js project with typescript

## Development

We use `node` version `14.9.0`

```
nvm install 14.9.0
```

```
nvm use 14.9.0
```

The first time, you will need to run

```
npm install
```

Then just start the server with

```
npm run start
```
It uses nodemon for livereloading :peace-fingers:

# API Validation

 By using celebrate the req.body schema becomes clary defined at route level, so even frontend devs can read what an API endpoint expects without need to writting a documentation that can get outdated quickly.

 ```js
 route.post('/signup',
  celebrate({
    body: Joi.object({
      name: Joi.string().required(),
      email: Joi.string().required(),
      password: Joi.string().required(),
    }),
  }),
  controller.signup)
 ```

 **Example error**

 ```json
 {
  "errors": {
    "message": "child \"email\" fails because [\"email\" is required]"
  }
 }
 ```
 