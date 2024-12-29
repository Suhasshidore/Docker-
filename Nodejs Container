# package.json  :

{
    "name": "node-app",
    "description": "hello jenkins test app",
    "version": "0.0.1",
    "private": true,
    "dependencies": {
       "express": "3.12.0"
    },
    "devDependencies": {
       "mocha": "10.2.0",
       "supertest": "6.3.3"
    }
   }

# index.js:

var express = require('express');
 
var app = express();//Respond with "hello world" for requests that hit our root "/"
app.get('/', function (req, res) {
 res.send('changed not ');
});//listen to port 3000 by default
app.listen(process.env.PORT || 3000);
 
module.exports = app;

# Docker File:

FROM node
WORKDIR /usr/src/app
COPY package.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node","index.js"]



# Instructions to Use:

-To build Dockerfile :
docker build -t imgname .
-To check whether image is created using Dockerfile :
docker images
-To launch a container using image of this Dockerfile :
docker run -d -p80:3000 --name nodecontainer imgname
-To check whether container is created using image :
docker ps
-Here the port 80 is port of EC2 instance whereas the port 3000 is port of Nodejs container
