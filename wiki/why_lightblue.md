# Why lightblue?

True to SOA principles, lightblue brings choice to data administrators, operations, developers, and business users.

Data administrators know that data is secure with optional plugable authentcation and authorization components.  This allows for consistent access control down to individual attributes / columns on all data even if the underlying technology doesn't support such controls!

Operations has the flexibility to securely deploy lightblue anywhere.  Lightblue has been carefully architected to support the authentication and authorization you require while making it completely optional.

Development teams can focus on the core business logic by providing a consistent query based CRUD layer for data access, providing unified view of your data.

With versioned metadata protecting clients from changes to data structures the management of data structures can finally be offloaded from development teams to those that ask for those changes!  With enforcement of backwards compatible changes for minor changes, lightblue ensures that existing clients are both protected from other client changes and empowered to make changes knowing they cannot disrupt other applications.

## Why is it so hard to add a new field?
* Adding a field may break backwards compatibility for clients.
* Updating all clients is not easy to schedule.
* Creating new APIs on the service solves the above problems but leads to sprawling APIs and inconsistency.

## Can we move our data to MongoDB?
* Migrating from one type of tech to another is not trivial, such as RDBMS to NoSQL.
* Moving some proprietary database technologies outside of a traditional datastore can be very costly.
* Changes in underlying datastore will lead to optimized ways accessing the data.  This changes APIs!

## Why is Information Security so concerned with moving to a cloud provider?
* When you control your data and application tier hardware it is easy to be lax with security.
* Moving data and applications off of hardware you control requires robust security.
* Enabling the move to public API access to even sensitive data requires a lot of rigor.

## Do more with less!
* IT budgets are shrinking while business demands continue to rise.  Any place cost can be reduced relative to gains is great!

## How does lightblue benefit developers?
One of the time sinks for developers is adding new features for clients of their software.  To address this for data access, lightblue provides a robust and very capable API, supports a growing number of datastores, and enables changes to data models without impacting existing clients through the use of versioned metadata.

### Robust API
The REST API of lightblue is designed to do everything a client could want.  There are some key points that the API addresses:
* Query: a very rich query language
* Projection: return only the data a client wants
* Bulk Operations: ability execute CRUD operations against many records or entire collections


#### Datastore Agnostic
Clients do not care where data is stored as long as it is available and secure.  With lightblue we have controller implementations for:
* MongoDB (1.9.0 and higher)
* RDBMS (ANSI SQL92)

Not seeing a contoller you need?  We welcome new implementations and contributions in general!  From opening a request for enhancement to writing code, your ideas and help are greatly appricated.

#### Versioned Metadata
All data in lightblue is controlled by its metadata.  Think of this as all the DDL for a table in a relational database.
Data structures are maintained by metadata.  A specific version of this metadata provides a window to the stored data.  You can have many versions of metadata active at a time, providing different clients with different windows to this data.  Key points to remember:
* all data structures are captured as metadata
* each data stucture can have multiple versions active at a time
* each client views data with a specific version
* clients using different versions are seeing the same data, just viewed through a different window

<insert example, something simple that anybody can relate to>

### How does lightblue benefit operations?
One of the challenges with maintaining enterprise applications is ensuring they are always on.  When any change to a data structure requires application deployments it requires operations resources and can require outages to execute.  With lightblue any changes to a data structure is simply a change to metadata.
* metadata updates are not software changes
* metadata updates are guarenteed backwards compatible

Some other benefits beyond simply reducing operations overhead are:
* lightblue is designed to be deployed anywhere
* lightblue employes a flexible component architecture that enables components to be deployed and scaled independently
* lightblue is built to be both latency and fault tollerant
* lightblue works with your preference of authentication and authorization

### Update a single field without lightblue:
![Slow](https://raw.github.com/lightblue-platform/lightblue/master/docs/slow.png)
What does this really mean?
1. Develop changes to code, which may include changing table structures and software configurations.
2. Deploy to development environment and test the changes.  Probably manual tests.  And if it fails, this goes back to development.
3. Once tests pass in development, deploy to QA.  Test again?
4. Get a change request approved.  May require many layers of approval.  You're changing software!
5. Approved and done in QA, now changes can be pushed to stage and production.. where they need verified again, probably manually.

#### Update a single field *with* lightblue:
![Fast](https://raw.github.com/lightblue-platform/lightblue/master/docs/fast.png)
Looks like it's easier.. is it really?
1. Create a new version of metadata with the updates.
2. Deploy to dev then QA.
3. Get a change request approved.  These changes will be proven to not break existing clients.  Expectation is approval process is less onerous.
4. Deploy to stage and production.

But what about testing?!?  Because of the versioned metadata no clients are impacted by the creation of a new metadata version.  Therefore, testing happens with whatever applications consume that new version.


### What about support and development tools?
If lightblue enables data access across many datasources and technologies we also need to provide tools to support that stack!  Enter the management applications:
* Metadata Management Application
* Data Management Application

![Lightblue Applications](https://raw.githubusercontent.com/lightblue-platform/lightblue/master/docs/overview.png)

Each of the applications provides access to the corresponding service layer.  The point of them is provide a nicer interface to the service layer without having to deal with the service directly.  Each application can be secured independent of the service tier, as noted in the diagram.
