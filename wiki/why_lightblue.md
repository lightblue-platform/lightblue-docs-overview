# Why lightblue?

Developing enterprise services for access to data (CRUD) can be deceptively simple.  Just write something that gives access to the data you need.  Done!  The challenge is how do to deal with growth over time and not replicate the data access layer for every component.

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

