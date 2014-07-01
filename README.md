# lightblue

Cloud focused data services with dynamic querying, versioned schemas, and robust security.

![lightblue architecture](https://raw.githubusercontent.com/lightblue-platform/lightblue-docs/master/images/lightblue-puzzle.png "High Level Architecture")

Lightblue is an open source project  built from the ground up to be very flexible.  This pluggable component architecture enables deployment of lightblue in virtually any environment and with only the components needed enabled.  This bascially means:  deploy lightblue where you want and plug in the puzzle pieces you want!

There are many projects for lightblue corresponding to the flexibility depected above.  They are each documented here.


## lightblue
The main repository at this time.  It is broken into three major sub-projects which are documented here with a prefix of "lightblue/".  Long term expect this project to go away once these sub-projects become proper top level projects in lightblue-platform.

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

## openshift-lightblue-all
All rest apps and web apps bundled into a single WAR for deployment on OpenShift.  See [lightblue in action](lightblue_in_action/README).

## lightblue-tests
All functional (integration) tests and load tests for lightblue.  These tests can be executed for every deployment to verify that lightblue is working well.

## lightblue-docs
The documentation you are reading right now.

## pyresttest
A python based rest testing framework forked from [svanoot/pyresttest](https://github.com/svanoort/pyresttest).  Functionality is added as needed and all changes are sent up-stream.

## shakespears-monkey
A library written on java for generating JSON documents that meet a documented structure.  For example, to create test data you might use shakespears-moneky to generate a few million records.



# License

The license of lightblue is [GPLv3](https://www.gnu.org/licenses/gpl.html).  See COPYING in root of each project for the full text.
