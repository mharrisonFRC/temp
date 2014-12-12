FRMS-Services
=============

FRMS top level web service container. Includes HTTP server (a la Restify) needed to expose a REST interface. Includes data module packages (e.g. https://github.com/dominionenterprises/FRMS-Places) to provide function to routed endpoints.

Starting Services
-----------------

**Connection Strings**

Connections are established through the config/connection.json file. If adding a new connetion add it there.  On a local machine it may be necessary to add a directory ```/var/log/frms-search/``` and chmod it to allow it to be written to by the service.

If you need to have a local configuration for connections, you can specify a different config file with the configpath option.

```sh
node server.js --configpath="/path/to/config/file.json"
```

**Required Services**

In order to get the FRMS-Services node instance running on your local machine, you will need to have the following services available to the node instance:

* Redis Server
* Mongodb
* Elastic Search

Additionally, you can make use of a Memcached service for certain modules in FRMS-Services, but this is not required. 

**To run:**

0. ```npm install```
1. Modify values in ```config/connection.json```. And make sure the required services are available.
2. ```node server.js```
3. Check ```http://localhost:4000/hello/fr-dev``` for a hello world.
4. Check ```http://localhost:4000/status``` for a health check.

Grunt Tasks
-----------

```sh
# Run JSHint
grunt jshint

# Run Unit Tests (should always pass)
grunt test

# Run Integration Tests (might pass)
grunt test-int

#Run JSHint and Unit Tests
grunt
```

Docs
----

Pretty API documentation is available via [Swagger](https://github.com/swagger-api/swagger-node-express). 

With services running, go to:

```
http://localhost:4000/docs/index.html
```
