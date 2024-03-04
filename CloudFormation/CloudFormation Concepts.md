Why use AWS CloudFormation?
What is AWS CloudFormation?
How does AWS CloudFormation work?
AWS CloudFormation Concepts
- Template in AWS CloudFormation
- Stack in AWS CloudFormation
CloudFormation Access Control
Demo - LAMP stack on EC2 instance
Demo - Create a redeployable template

# How does AWS CloudFormation work?
Refer to the image in one note

# AWS CloudFormation Concepts
- Template in AWS CloudFormation
- Stack in AWS CloudFormation

## Template
- A template in AWS CloudFormation is a formatted text file in JSON or YAML language that describes your AWS infrastructure.
- To create, view and modify templates you can use AWS CloudFormation Designer or any text
editor tool.
- Template in Amazon CloudFormation consists of nine main objects:
	- Format version
	- Description
	- metadata
	- Parameters
	- mappings
	- conditions
	- transform
	- resources
	- outputs

### Format Version
- Format version defines the capability of a template
- The latest value of a format version is "2010-09-09" ( yyyy-mm-dd)
- Example in YAML
``` 
"AWSTemplateFormatVersion":"2010-09-09"
```
- If not mentioned, the latest version is assumed.
### Description
- Any comments about your template can be specified in description
### Metadata
- Metadata can be used in the template to provide further information using JSON or YAML objects.
### Parameters
- Templates can be customized using parameters
- Each time you create or update your stack, parameters help in giving custom values to
	your template at runtime.
### Mapping
- Mapping enables you to map keys to a corresponding named value that you specify in
    conditional parameter
- Also, you can retrieve values in a map by using the Fn :: FindInMap intrinsic function
### Conditions
- are optional
- Conditions can be used when you want to reuse the templates by creating resources in
    different context
- In a template, during stack creation, all the conditions in your template are evaluated
- Any resources that are associated with a true condition are created and the invalid conditions are ignored automatically.
- You can use intrinsic function to define conditions
	- FN::OR
	- FN::NOT
	- FN::IF
	- FN::EQUALS
	- FN::AND
### Transform
- Transform builds a simple declarative language for AWS CloudFormation and enables reuse of
    template components
### Resource
- Using resource section, declare the AWS resource that you want to create and specify in the stack,
    such as Amazon S3 bucket or AWS Lambda.
### Output
- In a template, the output section describes the output values that you can import into other stacks
    or the values that are returned when a user view's his own stack properties
- For example, for a S3 bucket name, you can declare an output and use the "Description-stacks"
    command from the AWS CloudFormation service in order to make the bucket name easier to find
## Template Resource Attributes
- Creation policy
- Deletion policy
- Depends on
- Metadata
- Update policy
### Creation Policy
- Associate the CreationPolicy attribute with a resource when you want to delay on resource
	configuration actions before proceeding with stack creation
- With this attribute a stack creation is delayed, until AWS CloudFormation receives a specified number
	of success signals
- It can be used only for AWS AutoScaling, AWS EC2 Instance and AWS CloudFormation
### DeletionPolicy
- Using deletion policy, preserving and backing up of resources is possible when its stack is deleted
- By default, AWS CloudFormation deletes the resource and all its content if a resource has no DeletionPolicy attribute in a template
- Before deleting a resource, AWS CloudFormation creates its snapshot
### DependsOn
- Using the DependsOn attribute in a template, any user can define the creation of a specific resource followed by another resource
### Update Policy
- With UpdatePolicy attribute in AWS CloudFormation, you can manage and replace the updates of the instances in the Auto Scaling group.
## Stacks
- A collection of AWS resources is called a stack and it can be managed in a single unit
- CloudFormation's template defines a stack in which the resources can be created, deleted or updated in a predictable way
- A stack can have all the resources (web server, database etc.) that can be required to run a web application
### Nested Stacks
- Nested stack results a hierarchy of stacks
- Using the CloudFormation stack resource, a user can create a nested stack within another stack
### WindowsStacks
- Windows stack gives you the ability to update and configure your own stack in windows instances
- With AWS CloudFormation, you can create Microsoft Windows stacks for Amazon EC2's Windows AMI (Amazon Machine Images)
### Stack Set
- Using an AWS CloudFormation template, you can define a stackset that lets you to create stacks in AWS accounts across the globe by using a single template
- After a stack set is defined by you, creating , updating or deleting stacks in the target accounts and regions can also be specified
- 