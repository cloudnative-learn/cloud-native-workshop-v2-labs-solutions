# Bulent's notes

## Installation

### Maven

Since 3.8.1, Maven comes with a default configuration to block all HTTP (insecure) repositories. Tell Maven to allow downloading from our insecure repository by adding this mirror to our ~/.m2/settings.xml:

```
  <mirrors>
    <mirror>
      <id>insecure-repo</id>
      <mirrorOf>external:http:*</mirrorOf>
      <url>http://maven.repository.redhat.com/ga/</url>
      <blocked>false</blocked>
    </mirror>
  </mirrors>
```

### Properties

For Quarkus services, add the following to inventory, cart and order services:
m4/invertory-service/src/main/resources/application.properties
m4/cart-service/src/main/resources/application.properties
m4/order-service/src/main/resources/application.properties

```
# BK: change image group (default image group is username which can cause a problem if includes a special char)
quarkus.container-image.group=coolstore
```

Upgrade jquery resolution in m4/coolstore-ui/bower.json:
```
    "resolutions": {
        "jquery": "~3.6.0",
    }
```

### Native build 


### Run script

oc login ...
oc project bulent-cloudnativeapps

USERXX=bulent

```
sh scripts/deploy-solution-m4.sh
```
