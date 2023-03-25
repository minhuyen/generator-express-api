# Generator Expressjs Rest

## Features

- User Registration
- Basic Authentication with username and password
- Admin use [react-admin](https://github.com/marmelab/react-admin)
- Oauth 2.0 Authentication
  - Facebook
  - Google
- Upload Photo to S3 amazon
- Docker

### Prerequisites

- [Docker (at least 1.10)](https://www.docker.com/)
- [Docker-compose (at least 1.6)](https://docs.docker.com/compose/install/)

## Installation

Fist, install [Yeoman](http://yeoman.io) and generator-expressjs-rest using [npm](https://www.npmjs.com/) (we assume you have pre-installed [node.js](https://nodejs.org/)).

```bash
npm install -g yo
npm install -g generator-expressjs-rest
```

## Generators

Then, you can use `yo` to generate your project.

```bash
yo expressjs-rest # generate a new project
yo expressjs-rest:api # generate a new api endpoint inside your project
```

## Commands

After you generate your project, these commands.

```bash
cd your-project-name
mv .env.example .env

docker-compose build
docker-compose run --rm client yarn build
docker-compose up
```

## Playing locally

## Deploy

## Directory structure

### Overview

```bash
src/
├─ api/
│  ├─ auth/
│  │  ├─ index.js
│  │  ├─ auth.service.js
│  │  ├─ auth.validation.js
│  │  ├─ auth.controller.js
│  │  └─ auth.test.js
│  ├─ uploads/
│  │  ├─ index.js
│  │  ├─ upload.controller.js
│  ├─ users/
│  │  ├─ index.js
│  │  ├─ user.controller.js
│  │  ├─ user.validation.js
│  │  ├─ user.model.js
│  │  ├─ user.service.js
│  │  └─ user.test.js
│  └─ index.js
├─ services/
│  ├─ index.js
│  ├─ jwt.js
│  ├─ logger.js
│  ├─ mailgun.js
│  ├─ mongoose.js
│  ├─ passport.js
│  ├─ response.js
│  ├─ s3.js
│  ├─ swagger.js
│  └─ your-service.js
├─ app.js
├─ config.js
└─ index.js
```

### src/api/

Here is where the API endpoints are defined. Each API has its own folder.

#### src/api/some-endpoint/model.js

It defines the Mongoose schema and model for the API endpoint. Any changes to the data model should be done here.

#### src/api/some-endpoint/controller.js

This is the API controller file. It defines the main router middlewares which use the API model.

#### src/api/some-endpoint/index.js

This is the entry file of the API. It defines the routes using, along other middlewares (like session, validation etc.), the middlewares defined in the `some-endpoint.controller.js` file.

### services/

Here you can put `helpers`, `libraries` and other types of modules which you want to use in your APIs.

## TODO

- Support optional phone authentication
- Support optional email confirmation process
- Support Twitter and other social login methods
- Socket.io support

PRs are welcome.

## Credits

[@minhuyen](https://github.com/minhuyen) and all [contributors](https://github.com/minhuyen/generator-express-api/graphs/contributors)

## License

MIT © [minhuyen](https://github.com/minhuyen)
