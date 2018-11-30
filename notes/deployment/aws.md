# AWS notes

# FE Masters Rapid Development with AWS

I didn't finish the course because it turns out, AWS Mobilehub has a new API. But here's my notes.

## IAM roles

IAM means Identity Access Management. This service lets you create new users with selected permissions / access.

### Why create an IAM role?

It is not a good idea to use root user account. If your identity gets leaked or your api keys, your billing details and everything in your account will get compromised. Accidentally pushing your API keys in github always happens.

* Principle of least privilege
* limit the scope of breach / damage

### Setup

The steps are pretty straight forward, username, password, and some permissions you can assign to users.

> Tips: You can only see the secret keys once. It's best to download the `.csv` file and encrypt it.

### Assigning permissions

Think of your permissions as users and as an app. What permissions does the app need? 

There are 400+ permissions setup by aws, you can also create your own.

## Terminologies

AWS Mobile hub - Dashboard for easily managing multiple AWS services.
Cognito, S3, Lambda, DynamoDB, Cloudfront, Pinpoint.

Aws Amplify - JS libraries with helper functions for working with AWS Mobilehub

Aws Appsync - graphQL as a service. Built on top of DynamoDB, ElasticSearch, Lambda, real-time push notifications, etc...
