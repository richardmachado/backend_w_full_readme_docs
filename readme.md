# How to create a node.js backend with Express

## Step 1  - skip if you already initalized it as a git repo
`git init` 

## Step 2 
`npm init -y`

creates a package.json

## Step 3 -- install dependencies

`npm i nodemon express knex sqlite3 bcryptjs cors helmet pg morgan jsonwebtoken dotenv`

## Step 4 --  add a start script to package.json

```  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "nodemon index.js"
  },
```