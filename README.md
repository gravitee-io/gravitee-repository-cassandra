[![Build Status](https://ci.gravitee.io/buildStatus/icon?job=gravitee-io/gravitee-repository-cassandra/master)](https://ci.gravitee.io/job/gravitee-io/job/gravitee-repository-cassandra/job/master/)

# Gravitee Cassandra Repository

Cassandra repository based on Cassandra NoSQL Database.
This repository uses Datastax Java driver for synchronous communication with Cassandra.

## Requirement

The minimum requirement is :
 * Maven3
 * Jdk8

In order to use **Gravitee** snapshot, You need to declare the following repository in you Maven settings :

https://oss.sonatype.org/content/repositories/snapshots


## Building

```
$ git clone https://github.com/gravitee-io/gravitee-repository-cassandra.git
$ cd gravitee-repository-cassandra
$ mvn clean package
```


## Installing

Unzip the gravitee-repository-cassandra-1.0.0-SNAPSHOT.zip in the gravitee home directory.

Move the *gravitee-repository-cassandra-1.0.0-SNAPSHOT.zip* in the **Gravitee** */plugins* directory.


## Configuration

| Parameter                                            |   Description   |         default |
| ------------------------------------------------ | ------------- | -------------: |
| contactPoints                                         | allows to connect to Cassandra cluster nodes. It is not necessary to add all contact points because Cassandra driver will use auto-discovery mechanism |       localhost |
| port                                                  | defines the CQL native transport port |            9042 |
| keyspaceName                                          | name of the keyspace. Note that the final will be prefixed with the corresponding scope | <scope>cluster |
| username                                              | permit to connect to Cassandra if using access with credentials. If not, username is ignored |        gravitee |
| password                                              | permit to connect to Cassandra if using access with credentials. If not, password is ignored |        password |
| connectTimeoutMillis                                  | defines how long the driver waits to establish a new connection to a Cassandra node before giving up |            5000 |
| readTimeoutMillis                                     | controls how long the driver waits for a response from a given Cassandra node before considering it unresponsive |           12000 |
| consistencyLevel                                      | sets the level of consistency for read & write access, e.g. ONE, QUORUM, ALL (see Datastax documentation for comprehensive list) |             ONE |


> The script for creating keyspace and tables is in *src/main/resources*.