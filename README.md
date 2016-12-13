# Postman Continuous Integration example

<div><a href="https://travis-ci.org/RaoulvanWoerkom/Postman-CI-example"><img alt="Build Status" src="https://api.travis-ci.org/RaoulvanWoerkom/Postman-CI-example.svg?branch=master"></a><a href="https://github.com/RaoulvanWoerkom/Postman-CI-example/issues"><img src="https://img.shields.io/github/issues/RaoulvanWoerkom/Postman-CI-example.svg" alt="GitHub issues"></a></div>


This is an example on how to implement Postman calls into Continuous Integration (Travis CI).

"Newman is a command-line collection runner for Postman. It allows you to effortlessly run and test a Postman collection directly from the command-line. It is built with extensibility in mind so that you can easily integrate it with your continuous integration servers and build systems."

----------------------------------------------------------------------------------------------------------------------------------------

Sample Builds can be found here:
https://travis-ci.org/RaoulvanWoerkom/Postman-CI-example

----------------------------------------------------------------------------------------------------------------------------------------

Documentation on how to use Newman can be found here:
https://www.getpostman.com/docs/newman_intro

----------------------------------------------------------------------------------------------------------------------------------------
## Sample (.travis.yml)
```
# Speed up building using Cache
cache:
  directories:
    - node_modules
   
# Turn off notifications so you won't go crazy 
notifications:
  email: false

sudo: required
dist: trusty
language: node_js
# required node version >=4
node_js:
  - "4.0.0"

# Install newman
before_install:
  - npm install -g newman
# Run Postman Collection
script:
  - newman -c mycollection.json
```
----------------------------------------------------------------------------------------------------------------------------------------

