![Logo of the project](https://upload.wikimedia.org/wikipedia/commons/9/95/Infosys_logo.svg)

# AWS-DynamoDB-Java-Blueprint
> Less code more power without knowing AWS cloud.

This is a reusable AWS Java tech component can be used as maven dependency for other projects.
It integrated with aws sdk and provide commonly and frequently used functions with additional scope,
without writing much code to communicate with Amazon DynamoDB services.

## Getting started

Two way to configure maven dependency 

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
and how to implement these methods to project followed by:

* Environment Variables Setting
* Implementation
* Functional and method scope
* Building and Packaging

## Environment Variables Setting

As part of aws cloud service operation Access keys authentication/authorization required to configure in cloud config or
or any key store or secrate mnager or resources/application.properties
* ACCESS_KEY_ID
* SECRET_ACCESS_KEY
* AWS_REGION

Access keys are long-term credentials for an IAM user, for best practice ues IAM profile or role.

## Implementation

Package and class with static method create @return client builder instance with applied permission for AWS DynamoDb operations.
**Package** : com.infosys.aws.dynamodb.blueprint

**Class** : AwsDynamoDbManager.getInstanceOfDynamoDbBlueprint(...)

For example:
```shell
@Bean
public AwsDynamoDbManager customAmazonDynamoClient() {
	if(accessKey != null && !accessKey.trim().isEmpty() && secretKey != null && !secretKey.trim().isEmpty()) {
		return AwsDynamoDbManager.getInstanceOfDynamoDbBlueprint(region,accessKey,secretKey); //For Access Keys
	}
	else {
		return AwsDynamoDbManager.getInstanceOfDynamoDbBlueprint(); //For IAM profile role
	}
}
```

## Functional scope and methods

Calling methods as per requirement
* writeDynamoDBItem(...)
* readDynamoDBItem(...)

For example:
```shell
@Autowired
private AwsDynamoDbManager customAmazonDynamoClient;

boolean isInserted = customAwsDynamoDBClient.writeDynamoDBItem(<TABLE_NAME>, <ConcurrentHashMap data>);
String result = customAwsDynamoDBClient.readDynamoDBItem(<TABLE_NAME>, <primary key name>, <primary key value>, <column name>);
```

## Building and Packaging

To create deployable jar or war for your spring boot project including its dependency added automatically.
```shell
mvn clean install
```

## Contributing

Powered by Infosys Team

## Links

Even though this information can be found inside the project on machine-readable
format like in a .json file, it's good to include a summary of most useful
links to humans using your project. You can include links like:

- Repository: https://your.github.com/AWS-DynamoDB-Java-Blueprint/
- Issue tracker: https://your.github.com/AWS-DynamoDB-Java-Blueprint/issues
- Related projects:
  - Your other project: https://github.com/your/AWS-S3-Java-Blueprint/
  - Someone else's project: https://github.com/someones/AWS-SNS-Java-Blueprint/


## Licensing
Powered by Infosys Team

"The code in this project is licensed under Infosys."
