# Overview
A set of docker images to aid Infrastructure debug and test.
Each folder contains a docker-compose file for the relevant system.  
This should be enough to run the relevant container.

## Setup
While networking is provided within each docker-compose cluster, in order to communicate between the clusters a bridge will need to be created.
This will need to be created independently before running:

    docker network create mirada-test

## Running
Each folder contains a docker-compose.yml that can be used to start the cluster:

    docker-compose up -d

To force a rebuild of the containers run:

    docker-compose up --build -d

To stop the cluster run:

    docker-compose down

