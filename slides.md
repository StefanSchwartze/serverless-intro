#### A talk about
# Serverless
Stefan Schwartze
---

## A typical Node server architecture
![alt a typical node server](https://martinfowler.com/articles/serverless/ps.svg)
---

## Things to master
* Database
* Authentication
* Scaling
* CI / CD
---

## Money, money
* Pay ressources you don't need permanently
---

## Kill the server
![Try serverless!](https://cdn-images-1.medium.com/max/1600/1*hkjYPGxG2q_r_-bUk1qSWw.jpeg)
---

## FaaS
**F**unctions **a**s **a** **s**ervice
----

> Fundamentally, FaaS is about running backend code without managing your own server systems or your own long-lived server applications. 
-- Mike Roberts
---

## Using compute services
* Run your functions in the cloud
----

### AWS Lambda
* Executes your functions on demand
----

### AWS Gateway
---

### AWS config is always pain
---

## Serverless to the rescue
----

> Serverless is your toolkit for deploying and operating serverless architectures. Focus on your application, not your infrastructure.
— Serverless.com
----

### Setting up
```bash
$ npm install -g serverless
```
```bash
$ serverless config credentials --provider aws --key xxxxxxxxxxxxxx --secret xxxxxxxxxxxxxx
```
----

### Create a service
```bash
$ serverless create --template aws-nodejs --path my-service
```
----

### serverless.yml
* Config file for all settings
----

### Writing a first function
```javascript
module.exports.hello = (event, context, callback) => {
  const response = {
    statusCode: 200,
    body: 'Go Serverless v1.0! Your function executed successfully!',
  };
  callback(null, response);
};
```
----

### Deploy and go!
```bash
$ serverless deploy -v
```
![Service deployed](images/output.png)
----

![Service available](images/browseroutput.png)
----

### Testing locally
```bash
$ npm install serverless-offline --save-dev
```
---

## Why serverless architecture?
----

#### Scalability
![alt Serverless Express.js app under heavy load](https://cdn-images-1.medium.com/max/1600/1*F8bP1pP4Pc-eTKj0wLNzhA.jpeg)
----

#### Cost
![Save money](https://cdn-images-1.medium.com/max/1600/1*_SyXSIVxi0a5UKA5nQCBOQ.jpeg)
----

#### Productivity
* Developers can focus on product development
* Less worry about 
---

## Why serverless framework?
* Simplifies setting up
---

## Disadvantages
* Not suitable for long-term tasks
* No websockets with Lambda
---

## Sources

* Slobodan Stojanivic: https://medium.freecodecamp.org/express-js-and-aws-lambda-a-serverless-love-story-7c77ba0eaa35
* Adnan Rahic: https://hackernoon.com/a-crash-course-on-serverless-with-node-js-632b37d58b44
* Martin Fowler: https://martinfowler.com/articles/serverless.html
* Serverless docs: https://serverless.com/framework/docs/