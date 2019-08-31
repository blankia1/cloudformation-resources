 ansible-galaxy install -r roles/requirements.yml --force
export AWS_DEFAULT_REGION=eu-west-1

# Find the Cloudformation templates in aws-cloudformation repository
# Add this repository under the roles directory in this repository
This can be done by the command "make roles"


# There needs to be a trust relationship between the role and your user account.
# https://medium.com/@ngocson2vn/how-to-fix-the-error-an-error-occurred-accessdenied-when-calling-the-assumerole-operation-e85f0152daca
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "ec2.amazonaws.com",
        "AWS": "arn:aws:iam::003342916324:user/blankia"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}

# Docker in Production using AWS CloudFormation Resources Playbook

## Introduction

This repository is part of the [Docker in Production using Amazon Web Services](https://app.pluralsight.com/library/courses/docker-production-using-amazon-web-services/table-of-contents) course material, and provides an Ansible playbook for creating CloudFormation related resources.

## Branches

This repository contains two branches:

- [`master`](https://github.com/docker-production-aws/cloudformation-resources/tree/master) - represents the initial starting state of the repository as viewed in the course.  Specifically this is an empty repository that you are instructed to create in the module **Deploying AWS Infrastructure Using Ansible and CloudFormation**.

- [`final`](https://github.com/docker-production-aws/cloudformation-resources/tree/final) - represents the final state of the repository after completing all configuration tasks as described in the course material.

> The `final` branch is provided as a convenience in the case you get stuck, or want to avoid manually typing out large configuration files.  In most cases however, you should attempt to configure this repository by following the course material.

To clone this repository and checkout a branch you can simply use the following commands:

```
$ git clone https://github.com/docker-production-aws/packer-ecs.git
...
...
$ git checkout final
Switched to branch 'final'
$ git checkout master
Switched to branch 'master'
```

## Errata

No known issues.

## Further Reading

Please see the README of the [AWS Starter repository](https://github.com/docker-production-aws/aws-starter) for instructions on how to use the Ansible playbook included with this repository.
