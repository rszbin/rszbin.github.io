---
layout: post
title: 'AWS CloudFormation for DynamoDB'
categories: tools
---

## Important Components of CloudFormation

Template File > Stack > ChangeSet

A template file (.cfn) defines the desired state for our cloud environment.

A stack is a logical grouping of AWS resources, such as the dynamodb and the IAM role required to access it.

When a cloud formation template for an existing environment is modified and applied, a changeset applies the differences.

CloudFormation resource definitions allow for "DependsOn" to create relationships between objects, allows them to be created in a particular order etc.

The name of the resource in your yml file can be different to the name of the resource in AWS.

## Importing Existing AWS Resources into Cloud Formation
> The resource import feature allows you to import existing AWS resources into a new or existing CloudFormation stack. This feature is useful if you want to start using CloudFormation to manage resources that were created outside of CloudFormation, without having to delete and recreate them.

There are two ways to import existing resources:
- IaC Generator: Scans existing resources and generates a CloudFormation template based on their current state
- Resource Import: a manual process where you describe existing resources in a CloudFormation template (this approach requires you to manually specify the resource properties and configurations in the template)

Importing will create a change set that imports the existing resources into your stack.

You need to provide two values for every resource you're importing:
- an identifier property, like AWS::S3::Bucket
- an identifier value, the resource's actual property value

When importing a resource the following validation is performed:
- The resource to import exists.
- The properties and configuration values for each resource to import adhere to the resource type schema, which defines its accepted properties, required properties, and supported property values.
- The required properties are specified in the template. Required properties for each resource type are listed in the AWS resource and property types reference.
- The resource to import doesn't belong to another stack in the same Region.

NOTE: **CloudFormation doesn't check that the template configuration matches the actual configuration of resource properties.** 

## Using IaC generator
If instead, you want to generate a template for resources that are not already managed by CloudFormation then look into [Generate templates from existing resources with IaC generator](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/generate-IaC.html)

## Further Resources
https://www.youtube.com/watch?v=YXVCdGyHDSk

[AWS CloudFormation Resource Import Feature](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/resource-import.html)
