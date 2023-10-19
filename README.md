# Cassandra project : Restaurants inspection

## Introduction

This project consists of deploying a Cassandra cluster, using Docker containers to centralize results of restaurants inspections. An API was developped to test accessibility and times response of database.

## Prerequisite

- Docker

## Project structure

Project is structured as following:

```
/projet-cassandra
    /cassandra1_data
    /cassandra2_data
    /serveur_rest
    docker-compose.yml
    Dockerfile-serveur
    README.md
```

## API

API was developped using Flask and it offers these functionnalities:


- Obtain information about a restaurant from its ID.
- Take back names list of restaurant depending of cooking type.
- Obtain number of inspections of a restaurant from its ID.
- Take back names of 10th first restaurants depending of grade.

## Deployement of Cassandra cluster and API 

To ddeploy Cassandra cluster and API, execute the following command at project's root:

```bash
docker-compose up -d
```

This will load two Cassandra nodes and API using Docker.

## API use

Voici comment utiliser l'API :

- To obtain information about a restaurant from its identifier:

```http://localhost:5001/api/restaurant/<id>```

- To retrieve a list of restaurant names by cuisine type:

```http://localhost:5001/api/type_cuisine/<type_de_cuisine>```

- To obtain the number of inspections of a restaurant from its identifier:

```http://localhost:5001/api/inspection/<id>```

- To obtain the names of the first 10 restaurants in a given grade:

```http://localhost:5001/api/grade/<grade>```

    
The URLs return the response in JSON from the API.



## Conclusion

This project demonstrates how to deploy a Cassandra cluster using Docker containers and how to develop an API to interact with the database. It also illustrates how Cassandra can be used to manage large amounts of data while offering fast response times.
