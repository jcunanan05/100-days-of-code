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

# FE Masters AWS for Frontend Engineer

Newer Course. Steve talks about moving their company from rails app that serves their react app IN Chicago, to AWS, which serves to multiple places. This resulted in speed increase to those who are further in Chicago because the servers now are hosted to different servers through cloudfront cdn. 

They separated client to server because, everytime they push changes to the front-end code, they need to build the rails server, which is unneeded. He talks about his experiences on how did they host their app on AWS. AWS provides services from small to large scale apps.

## AWS Free tier

You can find the boundaries of a free tier in their website. Here are the main points.

* There are services within 12 months.
* There are things that are forever free
* You can set billing alerts

## Billing 

AWS has its billing dashboard that can let you set billing alerts, set a budget (with diff categories), set a budget to a group, etc...

### Free Tier Billing Alerts Setup

When you're free tier, you can setup alerts when you're going the limits of a free tier:

1. In your AWS console, search Billing and click.
2. Go to preferences, Check the box of `receive free tier usage alerts.`

### Creating Budget

There's a Budget tab on the AWS billing console, they're straight forward fields. You can organize your budget based on:

* Cost
* Usage
* RI (whatever this is)

You can also have notifications (email or SMS), and add which users to notify, and a lots of customization.

## Identity Access and Management (IAM)

AWS gives us a power to manage multiple users, multiple groups, with different permissions. It is a bad practice to use the root account with keys because if the root account is compromised, all of your resources can be exploited.

### Best practices for IAM

* Create a sub account admin and then manage from there.
* Principle of least access - give groups / roles only the access that they need. So even if it's compromised, the damage is minimized.
* Enable MFA
