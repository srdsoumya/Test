![Logo of the project](https://upload.wikimedia.org/wikipedia/commons/9/95/Infosys_logo.svg)

# AWS-DynamoDB-Java-Blueprint
> Only Java without knowing AWS cloud.

This is a reusable AWS Java tech component can be used as maven dependency for other projects.
It integrated with aws sdk and provide commonly and frequently used functions with additional scope,
without writing much code to communicate with Amazon DynamoDB services.

## Getting started

Two way to configure maven depedency 

```shell
Clone repository to IDE workspace
git clone https://github.com/your/AWS-DynamoDB-Java-Blueprint.git
cd AWS-DynamoDB-Java-Blueprint/
mvn clean install
or open the AWS-DynamoDB-Java-Blueprint folder in any maven supported java IDE as a maven project
```

```shell
Download AWS-DynamoDB-Java-Blueprint.jar copy/paste inside .m2 repository folder 
C:\Users\soumya.2136099\.m2\repository

or

mvn install:install-file -Dfile=c:\Users\soumya.2136099\Downloads\AWS-DynamoDB-Java-Blueprint.jar 
-DgroupId=com.infosys.aws.dynamodb.blueprint -DartifactId=com-infosys-aws-dynamodb-blueprint 
-Dversion=0.0.1-SNAPSHOT -Dpackaging=jar
```

The maven dependency successfully configured in the system and ready to use as a maven dependency.

### Add dependency configuration to project .pom file
```shell
<!— Infy AWS DynamoDB custom component maven dependency -->
<dependency>
  <groupId>org.infy.aws.dynamodb.component</groupId>
  <artifactId>org-infy-aws-dynamodb-component</artifactId>
  <version>0.0.1-SNAPSHOT</version>
</dependency>
```

## Developing

To implement AWS-DynamoDB-Java-Blueprint API, must understand functional scope or features 
and how to implement these methods to project:

### Environment Variables Setting

If your project needs some additional steps for the developer to build the
project after some code changes, state them here:

What's all the bells and whistles this project can perform?
* What's the main functionality
* You can also do another thing
* If you get really randy, you can even do thisl


Here again you should state what actually happens when the code above gets
executed.

### Deploying / Publishing

In case there's some step you have to take that publishes this project to a
server, this is the right time to state it.
