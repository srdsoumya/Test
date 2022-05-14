![Logo of the project](https://upload.wikimedia.org/wikipedia/commons/9/95/Infosys_logo.svg)

# AWS-SNS-Java-Blueprint
> Less code more power without knowing AWS cloud.

This is a reusable AWS Java tech component can be used as maven dependency for other projects.
It integrated with aws SNS sdk and provide commonly and frequently used functions with additional scope,
without writing much code to communicate with Amazon Simple Notification Service.

## Getting started

Way to configure custom maven dependency 

```shell
Clone repository to IDE workspace
git clone https://infygithub.ad.infosys.com/soumya-2136099/AWS-SNS-Java-Blueprint.git
cd AWS-SNS-Java-Blueprint/
mvn clean install
or open the AWS-SNS-Java-Blueprint folder in any maven supported java IDE as a maven project
```

```shell
Download AWS-SNS-Java-Blueprint.jar copy/paste inside .m2 repository folder 
C:\Users\soumya.2136099\.m2\repository

or

mvn install:install-file -Dfile=c:\Users\soumya.2136099\Downloads\AWS-SNS-Java-Blueprint.jar 
-DgroupId=com.infosys.aws.sns.blueprint -DartifactId=com-infosys-aws-sns-blueprint 
-Dversion=0.0.1-SNAPSHOT -Dpackaging=jar
```

The maven dependency successfully configured in the system and ready to use as a maven dependency.

### Add dependency configuration to project .pom file
```xml
<!— Infy AWS DynamoDB custom component maven dependency -->
<dependency>
  <groupId>com.infosys.aws.sns.blueprint</groupId>
  <artifactId>com-infosys-aws-sns-blueprint</artifactId>
  <version>0.0.1-SNAPSHOT</version>
</dependency>
```

## Developing

To implement AWS-SNS-Java-Blueprint API, must understand functional scope or features 
and how to implement these methods to your project followed by:

* Environment Variables Setting
* Implementation
* Functional and method scope
* Building and Packaging

## Environment Variables Setting

As part of aws cloud service operation Access keys authentication/authorization required to configure in cloud config or any key store or secrate manager or resources/application.properties for your main project.
* AWS_ACCESS_KEY_ID
* AWS_SECRET_ACCESS_KEY
* AWS_REGION

Note : Access keys are long-term credentials for an IAM user, for best practice ues IAM profile or role.
No configuration required for this blueprint component because its parameterized.

## Implementation

Package and class with static method create @return client builder instance with applied permission for AWS S3 operations.

**Package** : com.infosys.aws.sns.blueprint

**Class** : AwsSnsManager.getInstanceOfAmazonSNSBlueprint(...)

For example:
```java
@Value("${AWS_REGION}")
private String region;
	
@Value("${AWS_ACCESS_KEY_ID}")
private String accessKey;
	
@Value("${AWS_SECRET_ACCESS_KEY}")
private String secretKey;
```
```java
@Bean
public AwsSnsManager customAmazonSnsClient()() {
	if(accessKey != null && !accessKey.trim().isEmpty() && secretKey != null && !secretKey.trim().isEmpty()) {
		return AwsSnsManager.getInstanceOfAmazonSNSBlueprint(region,accessKey, secretKey, GamestopConstants.TOPIC_ARN); //For Access Keys
	}
	else {
		return AwsSnsManager.getInstanceOfAmazonSNSBlueprint(GamestopConstants.TOPIC_ARN); //For IAM profile role
	}
}
```

## Functional scope and methods

Calling methods as per requirement
* publishMessageToSnsTopic(...)
* publishBatchMessageToSnsTopic(...)

For example:
```java
@Autowired
private AwsSnsManager customAmazonSnsClient;
```
```java
boolean isPublish = customAmazonSnsClient.publishMessageToSnsTopic(<MESSAGE>);
boolean isPublish = customAmazonSnsClient.publishBatchMessageToSnsTopic(<LIST_MESSAGE>);
```

## Building and Packaging

To create deployable jar or war for your spring boot project including its dependency added automatically.
```shell
mvn clean install
```

## Contributing

Powered by Infosys Team

## Links

Important useful links

- Repository: https://infygithub.ad.infosys.com/soumya-2136099/AWS-SNS-Java-Blueprint/
- API documentation : https://infygithub.ad.infosys.com/soumya-2136099/AWS-SNS-Java-Blueprint/document
- Issue tracker: https://infygithub.ad.infosys.com/soumya-2136099/AWS-SNS-Java-Blueprint/issues
- Related projects:
  - AWS-S3-Java-Blueprint: https://infygithub.ad.infosys.com/soumya-2136099/AWS-S3-Java-Blueprint/
  - AWS-DynamoDB-Java-Blueprint: https://infygithub.ad.infosys.com/soumya-2136099/AWS-DynamoDB-Java-Blueprint/


## Licensing
Powered by Infosys Team

"The code in this project is licensed under Infosys."
