# Why lightblue?

True to SOA principles, lightblue brings choice to data administrators, operations, developers, and business users.

Data administrators and InfoSec know that data is secure with optional plugable authentcation and authorization components.  This allows for consistent access control down to individual attributes / columns on all data even if the underlying technology doesn't support such controls!

Operations has the flexibility to securely deploy lightblue anywhere.  Lightblue has been carefully architected to support the authentication and authorization you require while making it completely optional.

Development teams can focus on the core business logic by providing a consistent query based CRUD layer for data access, providing unified view of your data.

With versioned metadata protecting clients from changes to data structures the management of data structures can finally be offloaded from development teams to those that ask for those changes!  With enforcement of backwards compatible changes for minor changes, lightblue ensures that existing clients are both protected from other client changes and empowered to make changes knowing they cannot disrupt other applications.

## Why is security such a focus?
Developers talk in terms of technical debt when something done results in additional work later on.  When you control your data and application tier hardware it is easy to be lax with security, incurring security debt.  Additionally, moving data and applications off of hardware you control may require more robust security.  The final step is making your data available publically.  Enabling the move to public API access to even sensitive data requires a lot of rigor.

Lightblue addresses these concerns with a plugin approach to authentication and authorization.  Apply as much security as you need and want for your use case without incurring the cost of features you will never use!

## I only have one datastore, why should I look at lightblue?
Everybody starts with one thing.  With success comes pressure to provide more and many times that means moving to new technologies including data storage technologies.  Today, in many cases, this means possibly moving from a relational database to a NoSQL solution like MongoDB and others.  With lightblue you get the flexibility to choose where your data is stored and patterns for moving from one data storage technology to another.

## How can lightblue help me?
Basically lightblue can free up developer time by removing efforts for getting access to data.  The robust query language of lightblue means every client has a consistent view of any data, regardless of where it is stored.  Versioned metadata means developers don't have to write a single line of code to change a data model.  Metadata can be managed by anybody!  Management applications exist to make viewing and editing data accessible to anybody.

![Lightblue Applications](https://raw.githubusercontent.com/lightblue-platform/lightblue/master/docs/overview.png)

### Robust API
The REST API of lightblue is designed to do everything a client could want.  There are some key points that the API addresses:
* Query: a very rich query language
* Projection: return only the data a client wants
* Bulk Operations: ability execute CRUD operations against many records or entire collections

### Datastore Agnostic
Clients do not care where data is stored as long as it is available and secure.  With lightblue we have controller implementations for:
* MongoDB (1.9.0 and higher)
* RDBMS (ANSI SQL92)

Not seeing a contoller you need?  We welcome new implementations and contributions in general!  From opening a request for enhancement to writing code, your ideas and help are greatly appricated.

### Versioned Metadata
All data in lightblue is controlled by its metadata.  Think of this as all the DDL for a table in a relational database.
Data structures are maintained by metadata.  A specific version of this metadata provides a window to the stored data.  You can have many versions of metadata active at a time, providing different clients with different windows to this data.  Key points to remember:
* all data structures are captured as metadata
* each data stucture can have multiple versions active at a time
* each client views data with a specific version
* clients using different versions are seeing the same data, just viewed through a different window

<insert example, something simple that anybody can relate to>
