# Introduction

famodulus is a system for research in outsourcing of modular exponentiation. It consists of three core components:

* [famodulus-server](https://github.com/mainini/famodulus-server) - server for outsourcing big integer calculations
* [famodulus-client](https://github.com/mainini/famodulus-client) - JavaScript library for the browser and node.js
* [famodulus-demo](https://github.com/mainini/famodulus-demo) - demonstrator application for famodulus-client

This repository helps in installation and usage of the full system; for a detailed description of its parts as well
as guidance on separate installation, please have a look at the corresponding repositories.

# Installation

To install famodulus, the following tools are required:

* Java JDK, version 1.8 or later
* [maven](https://maven.apache.org), version 3.0.5 or later
* [node.js](https://nodejs.org), version 6.9.1 or later

## Setting up Sources

If you haven't already, clone this repository. Then, initialize the submodules in it:

    git clone https://github.com/mainini/famodulus.git
    cd famodulus
    git submodule init
    git submodule update

## Building the Client

As the demonstrator application depends on the client, the first step consists in building the client library:

    cd famodulus-client
    npm install

There should now be a `.build` directory containing `js/famodulus.browser.js` as well as the JSDoc documentation
of the library. Proper functioning of the library  may be tested using `npm test`.

## Building the Demonstrator

Change to the demo directory and compile the demonstrator using maven:

    cd ../famodulus-demo/
    mvn compile

## Building the Server

As last step, the server is again built using maven:

    cd ../famodulus-server/
    mvn compile

# Usage

After all components have been built, the system can now be used. Both servers (famodulus-server and the webserver for the demo) can be started using maven, run `mvn exec:java` in the respective directory.

The demonstrator application should now be available at http://localhost:8080 while the server is running on port 8081.

# Version History

## 1.0.3 (2017-01-19)

* Upgrade famodulus-demo -> 1.0.1

## 1.0.2 (2017-01-14)

* Upgrade famodulus-server -> 1.1.0

## 1.0.1 (2017-01-14)

* Upgrade famodulus-client -> 1.0.1

## 1.0.0 (2017-01-11)

* Initial version
* Added famodulus-server 1.0.0
* Added famodulus-client 1.0.0
* Added famodulus-demo 1.0.0
