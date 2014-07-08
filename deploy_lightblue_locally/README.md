# Deploy lightblue on Fedora 20

To deploy lightblue locally requires a container to deploy the application into and a database to store metadata and data.  This shows how to install this on Fedora 20.  Similar steps can be followed for earlier Fedora releases.

## Install WildFly
```
# install
yum install -y wildfly

# fix symlink for jboss-marshalling
rm -f /usr/share/wildfly/modules/system/layers/base/org/jboss/marshalling/river/main/jboss-marshalling-river.jar
ln -s /usr/share/java/jboss-marshalling/jboss-marshalling-river.jar /usr/share/wildfly/modules/system/layers/base/org/jboss/marshalling/river/main/jboss-marshalling-river.jar

# create missing symlink for resteasy-json-p-provider-jandex.jar
ln -s /usr/share/java/resteasy/resteasy-json-p-provider-jandex.jar /usr/share/wildfly/modules/system/layers/base/org/jboss/resteasy/resteasy-json-p-provider/main/resteasy-json-p-provider-jandex.jar

# start on bootup
chkconfig wildfly on

# start service
service wildfly start
```

## Install MongoDB
```
# install
yum install -y mongodb mongodb-server

# start on bootup
chkconfig mongod on

# start service
service mongod start
```

## Deploy lightblue!
Assuming you have followed steps to [build for wildfly](../build_source/README.md).

Two things need to be done to setup lightblue.  First, deploy the lightblue module to wildfly:
```
sudo mkdir -p /usr/share/wildfly/modules/com/redhat/lightblue/main
sudo cp lightblue-rest/etc/mongo/* /usr/share/wildfly/modules/com/redhat/lightblue/main
```

And now the RPMs can be deployed:
```
sudo yum install `find -name lightblue*.rpm`
```

## Uninstall!
If you decide to uninstall, here's how to cleanup everything previously done..

```
yum remove -y mongodb mongodb-server wildfly
```
