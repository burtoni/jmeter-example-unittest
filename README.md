# Example JMeter Maven Performance Tests

This directory contains the test artifacts required to execute the example unit performance test:

* `pom.xml`: Maven instruction for how the test should be run
* `unittest.example.jmx`: JMeter JMX file run against the individual API endpoints
* `unittest.example.threadgroups.conf`: Definition for the load profile for each API endpoint
* `unittest.example.xml`: Definition of the target SLAs for each endpoint.

To execute:

      mvn clean verify

To edit:

      mvn clean jmeter:gui

## Test Types

There are two types of tests supported:

* A __benchmark__ test, i.e. where each individual endpoint is tested sequentially, in isolation
* A __load__ test, i.e. where each endpoint is tested concurrently, as part of a load test

By default, a benchmark test is run, unless otherwise specified using the `testType` command-line parameter:

    mvn clean verify -DtestType=load

## Environments

Switching between environments is handled through the use of the `-Denv` command-line parameter:

    mvn clean verify -Denv=perf
    
Test data for the relevant environment should be placed in a subdirectory of `data/`

## Test Data

Test data is included for the purpose of example only.
