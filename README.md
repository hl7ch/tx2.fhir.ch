# Readme about tx2.fhir.ch

This is the configuration project for running a tx.fhir.ch server based on the [FHIRsmith](https://github.com/HealthIntersections/FHIRsmith) server.

## Configuration

### Configuration server

The configuration of the server is done in the file data/config.json

See [Basic Configuration](https://github.com/HealthIntersections/FHIRsmith?tab=readme-ov-file#basic-configuration)


### Configuration TX cache

The configuration of the packages to be provided by this tx server is defined in the file 
config/library.yml

see the documentation [Library Configuration](https://github.com/HealthIntersections/FHIRsmith/blob/main/tx/README.md#library-configuration)
and an [example](https://github.com/HealthIntersections/FHIRsmith/blob/main/tx/tx.fhir.org.yml)


### Get cache files

To provide the SNOMED-CT and LOINC code systems, the corresponding cache files have to be downloaded using

    ./downloadcachefiles.sh


## Run the server

You can create and start the docker instance using following commend

    docker compose up

If the server is running well, you can stop it and start the created docker image with

    docker start tx2-fhir

The log can be followed either by

    docker logs -f tx2-fhir

or by

    tail -f data/logs/server-yyyy-mm-dd.log

## Update the server

Updating the server you can stop a running instance with

    docker stop tx2-fhir

The you can run

    docker compose pull

to dowload the latest image and run it first time with

    docker compose up

the follow the other instructions in the chapter above


