![Logo of the project](https://upload.wikimedia.org/wikipedia/commons/9/95/Infosys_logo.svg)

# AWS-DynamoDB-Java-Blueprint
> Only Java without knowing AWS cloud.

This is a reusable AWS Java tech component can be used as maven dependency for other projects.
It integrated with aws sdk and provide commonly and frequently used functions with additional scope,
without writing much code to communicate with Amazon DynamoDB services.

## Getting started

Two way to add maven depedency 

```shell
Clone repository to IDE workspace
git clone https://github.com/your/AWS-DynamoDB-Java-Blueprint.git
cd AWS-DynamoDB-Java-Blueprint/
mvn clean install

or

Open the AWS-DynamoDB-Java-Blueprint folder in any maven supported java IDE as a maven project
mvn clean install
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

Here's a brief intro about what a developer must do in order to start developing
the project further:
