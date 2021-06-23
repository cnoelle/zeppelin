# Overview
MongoDB interpreter for Apache Zeppelin. Thanksgiving to [bbonnin/zeppelin-mongodb-interpreter](https://github.com/bbonnin/zeppelin-mongodb-interpreter).
I found bbonnin's mongodb interpreter was not working with newest zeppelin version, it has not been maintained for a long time.
so I forked this for those people who want to use mongodb in zeppelin.

### Technical overview
it use mongo shell to execute scripts.All you need to do is to configure mongodb interpreter,
and then study mongo aggregate functions.

Alternatively, the new mongosh shell is supported (for MongoDB >= 4.0). 

## Usage with Docker and mongosh

(Note: as of 2021-06-04 this does not work with the current version 0.9.0, but rather requires a SNAPSHOT build at least of the mongodb interpreter)

### Build

In this folder run

```
docker build -t zeppelin .
```

### Run

```
docker run -d --rm -p 8080:8080 -e MONGO_SERVER_HOST=localhost -e MONGO_SERVER_DATABASE=MyDatabase --name zeppelin zeppelin
```

Adapt the host and database name to your needs. In a notebook, enter

```
console.log(db.MyCollection.findOne({}))
```

and run the paragraph



