# Project Structure

There are many repositories that make up lightblue.  Here's the high level overview of what is in each.

## lightblue
The main repository at this time.  It is broken into three major sub-projects which are documented here with a prefix of "lightblue/".  Long term expect this project to go away once these sub-projects become proper top level projects in lightblue-platform.

https://github.com/lightblue-platform/lightblue

## lightblue/lightblue-core
Core lightblue fucntionality.  In scope are the following in the puzzle:
* lightblue CRUD Layer
* abstract code for the metadata and controller plugins

## lightblue/lightblue-metadata-mongo
The MongoDB metadata and CRUD controller implementation.

## lightblue/lightblue-rest
The lightblue REST API and implementation.

## lightblue-applications
There are two management applications that enable easier use of metadata and data services.  This repository is for that code.

![Lightblue Applications](https://raw.githubusercontent.com/lightblue-platform/lightblue/master/docs/overview.png)

https://github.com/lightblue-platform/lightblue-applications

## openshift-lightblue-all
All rest apps and web apps bundled into a single WAR for deployment on OpenShift.  See [lightblue in action](lightblue_in_action/README).

https://github.com/lightblue-platform/openshift-lightblue-all

## lightblue-tests
All functional (integration) tests and load tests for lightblue.  These tests can be executed for every deployment to verify that lightblue is working well.

https://github.com/lightblue-platform/lightblue-tests

## lightblue-docs
The documentation you are reading right now.

https://github.com/lightblue-platform/lightblue-docs

## pyresttest
A python based rest testing framework forked from [svanoot/pyresttest](https://github.com/svanoort/pyresttest).  Functionality is added as needed and all changes are sent up-stream.

https://github.com/lightblue-platform/pyresttest

## shakespears-monkey
A library written on java for generating JSON documents that meet a documented structure.  For example, to create test data you might use shakespears-moneky to generate a few million records.

https://github.com/lightblue-platform/shakespeares-monkey
