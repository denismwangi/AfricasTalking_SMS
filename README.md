# AfricasTalking_SMS

## Documentation
Take a look at the [API docs here](http://docs.africastalking.com).

## Install

You can depend on the .jar through Maven (from `http://dl.bintray.com/africastalking/java`):
```xml
<dependency>
  <groupId>com.africastalking</groupId>
  <artifactId>core</artifactId>
  <version>3.3.3</version>
</dependency>
```
or sbt:

```
resolvers += "africastalking maven repository" at "http://dl.bintray.com/africastalking/java"
// Get all services
libraryDependencies += "com.africastalking" % "core" % "3.3.3"
```

or Gradle:
```groovy
repositories {
  maven {
    url  "http://dl.bintray.com/africastalking/java"
  }
}

dependencies{
  // Get all services
  compile 'com.africastalking:core:3.3.3'
}
```

## Usage

The SDK needs to be initialized with your app username and API key, which you get from the [dashboard](https://account/africastalking.com).

> You can use this SDK for either production or sandbox apps. For sandbox, the app username is **ALWAYS** `sandbox`

- Open and change application.yml
```yml
africastalking:
  USERNAME: 
  API_KEY: 
  ```
  
  ```java

// Initialize a service e.g. SMS
SmsService sms = AfricasTalking.getService(AfricasTalking.SERVICE_SMS);

// Use the service
List<Recipient> response = sms.send(message, from, recipients, true);
```
