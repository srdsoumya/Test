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

As part of aws cloud service operation role based or Access keys authentication authorization required
* ACCESS_KEY_ID
* SECRET_ACCESS_KEY
* AWS_REGION
Note : Access keys are long-term credentials for an IAM user, for best practice ues IAM profile or role

### Deploying / Publishing

@return Create new client builder instance for authentication and authorization
* AwsDynamoDbManager.getInstanceOfDynamoDbBlueprint //class with static method and @Bean
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

And again you'd need to tell what the previous code actually does.
