# Graphene-SGX Secure Container (GSC)

## Introduction to GSC
Graphene-SGX Secure Container (GSC) is a container system where the containerized application can be protected by Graphene-SGX while it is running in a container environment. The GSC system includes two parts: (1) a Docker container instance where the application is running inside Graphene-SGX and both of them are running inside the container instance; (2) a front-end named GSCE (GSC Engine) which takes a legacy Docker container image and automatically launches the contained application inside a GSC container instance.

__** Disclaimer: This software is a research proof of concept and not intended for production use **_


## How to use GSC
Launching a GSC container instance includes following steps:

(1) Make sure there is a Docker container image of your application in the local or remote image repository.

(2) Download and Build Graphene-SGX, by executing:
    
    ./configure

(3) Launching a GSC container via the following command:

   bin/gsce run [Docker Image Name:Tag] [All the arguments used for launching a normal Docker container].
   
## Examples

Let's take redis, an key-value, in-memory database as an example. Assume the user runs a normal redis from its docker image as follows.

docker run -i -t -p 6379:6379 redis:latest

To launch a GSC container running redis, the user runs the command as follows.

./gsce run redis:latest -i -t -p 6379:6379


## Contact
For any questions, Please contact Li Lei with li.lei@intel.com
