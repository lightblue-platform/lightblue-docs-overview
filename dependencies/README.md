# Dependencies

| Dependency | Why | License
| ---------- | --- | -------
| [Jackson](http://wiki.fasterxml.com/JacksonHome) | Java library for processing JSON documents.  Use in complicated cases where processing is required on the JSON document. |[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
| [JSONassert](https://github.com/skyscreamer/JSONassert) | Used in unit tests to compare JSON documents before and after processing.  Useful for verifying parsing and type conversions (JSON -> Java -> JSON for example) | [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
| [json-schema-validator](https://github.com/fge/json-schema-validator) | Validation of JSON documents against a JSON schema.  Similar to XML Schema validation. | [LGPLv3 or later](https://www.gnu.org/licenses/lgpl.html)
| [Flapdoodle Embedded MongoDB](https://github.com/flapdoodle-oss/de.flapdoodle.embed.mongo) | In memory MongoDB used in unit tests to test against a real database. | [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
| [mongo-java-driver](https://github.com/mongodb/mongo-java-driver) | MongoDB driver for Java.  Used for all interactions with MongoDB from Java. | [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
| [hystrix](https://github.com/Netflix/Hystrix) et al.| Hystrix core is a java framework to build a Distributed/Cloud-enabled Systems. It's "... is a latency and fault tolerance library designed to isolate points. .., stop cascading failure and enable resilience ...". | [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
| [pyresttest](https://github.com/svanoort/pyresttest)| Python utility for testing and benchmarking RESTful services. | [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
