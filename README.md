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

As part of aws cloud service operation Access keys authentication/authorization required to configure in cloud config or
or any key store or secrate mnager or resources/application.properties
* ACCESS_KEY_ID
* SECRET_ACCESS_KEY
* AWS_REGION

Access keys are long-term credentials for an IAM user, for best practice ues IAM profile or role.

### Implement

Package and class with static method create @return client builder instance with applied permission for AWS DynamoDb operations.
__com.infosys.aws.dynamodb.blueprint__ 
__AwsDynamoDbManager.getInstanceOfDynamoDbBlueprint__ 

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

And again you'd need to tell what the previous code actually does.

## Functional and method scope

Calling methods as per requirement
* writeDynamoDBItem
* readDynamoDBItem

For example:
```shell
@Autowired
private AwsDynamoDbManager customAmazonDynamoClient;

boolean isInserted = customAwsDynamoDBClient.writeDynamoDBItem(<TABLE_NAME>, <ConcurrentHashMap data>);
String result = customAwsDynamoDBClient.readDynamoDBItem(<TABLE_NAME>, <primary key name>, <primary key value>, <column name>);
```

## Configuration

Here you should write what are all of the configurations a user can enter when
using the project.

#### Argument 1
Type: `String`  
Default: `'default value'`

State what an argument does and how you can use it. If needed, you can provide
an example below.

Example:
```bash
awesome-project "Some other value"  # Prints "You're nailing this readme!"
```

#### Argument 2
Type: `Number|Boolean`  
Default: 100

Copy-paste as many of these as you need.

## Contributing

When you publish something open source, one of the greatest motivations is that
anyone can just jump in and start contributing to your project.

These paragraphs are meant to welcome those kind souls to feel that they are
needed. You should state something like:

"If you'd like to contribute, please fork the repository and use a feature
branch. Pull requests are warmly welcome."

If there's anything else the developer needs to know (e.g. the code style
guide), you should link it here. If there's a lot of things to take into
consideration, it is common to separate this section to its own file called
`CONTRIBUTING.md` (or similar). If so, you should say that it exists here.

## Links

Even though this information can be found inside the project on machine-readable
format like in a .json file, it's good to include a summary of most useful
links to humans using your project. You can include links like:

- Project homepage: https://your.github.com/awesome-project/
- Repository: https://github.com/your/awesome-project/
- Issue tracker: https://github.com/your/awesome-project/issues
  - In case of sensitive bugs like security vulnerabilities, please contact
    my@email.com directly instead of using issue tracker. We value your effort
    to improve the security and privacy of this project!
- Related projects:
  - Your other project: https://github.com/your/other-project/
  - Someone else's project: https://github.com/someones/awesome-project/


## Licensing

One really important part: Give your project a proper license. Here you should
state what the license is and how to find the text version of the license.
Something like:

"The code in this project is licensed under MIT license."
