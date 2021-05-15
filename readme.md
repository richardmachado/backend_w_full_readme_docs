# How to create a node.js backend with Express

## Step 1  - skip if you already initalized it as a git repo
`git init` 

## Step 2 - initialize your project
`npm init -y`

creates a package.json

## Step 3 -- install dependencies

`npm i nodemon express knex sqlite3 bcryptjs cors helmet pg morgan jsonwebtoken dotenv`

## Step 4 --  add a start script to package.json

```  
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "start": "nodemon index.js"
  },
```

## Step 5 -- add index.js in root of project - TIME TO TEST THIS!

```
const server = require('./api/server.js');

const port = process.env.PORT || 4000;

server.listen(port, () => {
  console.log((`Server is listening now, live on port ${port}!!!!!`));
});
```

## Step 6 -- create that file that's reference in step 5

`api/server.js`

in this file add the following

```
const express = require("express");
const cors = require("cors");
const helmet = require("helmet");
const server = express();

server.use(helmet());
server.use(cors());
server.use(express.json());

module.exports = server;
```


## Step 7 - npm run start

in your terminal, type `npm run start` or `yarn start` and hit `enter`

you should see the following

```
> nodemon index.js

[nodemon] 2.0.7
[nodemon] to restart at any time, enter `rs`
[nodemon] watching path(s): *.*
[nodemon] watching extensions: js,mjs,json
[nodemon] starting `node index.js`
Server is listening now, live on port 4000!!!!!
```

step 8 - gitignore

You should ignore node modules and .env files from being pushed to github


in your terminal type
`touch .gitignore && echo "node_modules/" >> .gitignore`

this will create the file and add node_modules, go in there and add `.env` in a new line