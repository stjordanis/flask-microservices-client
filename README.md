# FLASK MICROSERVICES

This project is based on [testdriven.io](http://testdriven.io/) Microservices with Docker, Flask and React  

### Structure
1. _[flask-microservices-main](https://github.com/repodevs/flask-microservices-main)_ Docker Compose files, Nginx, admin scripts
2. _[flask-microservices-users](https://github.com/repodevs/flask-microservices-users)_ Flask App
3. _[flask-microservices-client](https://github.com/repodevs/flask-microservices-client)_ client-side based on ReactJS
---

## How To Run
----
1. install dependencies
```bash
$ npm install 
```
2. add react users service url
```bash
$ export REACT_APP_USERS_SERVICE_URL=http://localhost:5555
```
3. run it
```bash
$ npm start
```

In the [flask-microservices-users](https://github.com/repodevs/flask-microservices-users) run the server

```bash
$ source env/bin/activate
$ export APP_SETTINGS=project.config.DevelopmentConfig
$ export DATABASE_URL=postgres://postgres:postgres@localhost:5432/users_dev
$ export DATABASE_TEST_URL=postgres://postgres:postgres@localhost:5432/users_test

## create and seed database
$ python manage.py recreate_db
$ python manage.py seed_db
$ python manage.py runserver -p 5555
```

## Other Command

To Build Docker image React App:
```bash
$ docker build -t "test" ./ --build-arg NODE_ENV=development --build-arg REACT_APP_USERS_SERVICE_URL=http://FLASK_SERVER_URL
```
To run the `test` image:
```bash
$ docker run -d -p 9000:9000 test
```
To view container's environment:
```bash
$ docker exec CONTAINER_ID bash -c 'env'
```
To stop and remove container:
```bash
$ docker stop CONTAINER_ID
$ docker rm CONTAINER_ID
```
To remove the image:
```bash
$ docker rmi test
```


