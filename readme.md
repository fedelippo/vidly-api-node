## Introduction

This project is the backend of Vidly, an imaginary video rental app. I've used Vidly as an example in several of my online programming courses, such as:

- https://codewithmosh.com/p/mastering-react
- https://codewithmosh.com/p/the-complete-node-js-course
- https://codewithmosh.com/p/asp-net-mvc

This is the implementation of Vidly in Node.js.

## Setup

Make sure to follow all these steps exactly as explained below. Do not miss any steps or you won't be able to run this application.

### Install MongoDB

To run this project you need to install the latest version of MongoDB Community Edition first.

#### Install MongoDB locally

https://docs.mongodb.com/manual/installation/

Once you install MongoDB, make sure it's running.

#### MongoDB using Docker container

Install [Docker](https://www.docker.com/products/docker-desktop) on your machine.

Clone the following repo which contains a Docker compose project to run an instance of
MongoDB ready to be used with this _vidly-api-node_ app.

```
git clone https://github.com/fedelippo/mongo-docker.git
cd mongo-docker
docker-compose up -d
```

To make sure the container is running execute:

```
docker-compose logs -f
```

### Install the Dependencies

Next, from the project folder, install the dependencies:

    npm i

### Populate the Database

    node seed.js

### Run the Tests

You're almost done! Run the tests to make sure everything is working:

    npm test

All tests should pass.

### Start the Server

    node index.js

This will launch the Node server on port 3900. If that port is busy, you can set a different point in config/default.json.

Open up your browser and head over to:

http://localhost:3900/api/genres

You should see the list of genres. That confirms that you have set up everything successfully.

### (Optional) Environment Variables

If you look at config/default.json, you'll see a property called jwtPrivateKey. This key is used to encrypt JSON web tokens. So, for security reasons, it should not be checked into the source control. I've set a default value here to make it easier for you to get up and running with this project. For a production scenario, you should store this key as an environment variable.

On Mac:

    export vidly_jwtPrivateKey=yourSecureKey

On Windows:

    set vidly_jwtPrivateKey=yourSecureKey
