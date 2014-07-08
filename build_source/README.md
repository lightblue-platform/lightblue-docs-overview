# Build from Source

## Dependencies
* rpm-build
* git
* maven (3+)
* java (1.7)

```
sudo yum install rpm-build git maven java-1.7.0-openjdk-devel
```

## Checkout
```
git clone https://github.com/lightblue-platform/lightblue.git
cd lightblue
```

## Build (default profile)

```
mvn clean install
```

## Build for Wildfly
Builds lightblue for deployment on wildfly.  The only difference is where the artifacts get deployed on the filesystem.  By default lightblue builds for deployment on JBoss EAP6.

```
mvn clean install -P wildfly
```
