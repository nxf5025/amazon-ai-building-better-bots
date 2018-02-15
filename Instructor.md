# CoffeeBot Instructor Manual

## Permissions

The users accessing this bot will need the following IAM managed policies associated with their account:

- AWSLambdaFullAccess
- AmazonLexFullAccess

## IAM Roles

Create the following IAM role that users will associate with their Lambda function

- Name: coffeebot-lambda-role
- Policy

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "logs:CreateLogGroup",
                "logs:CreateLogStream",
                "logs:PutLogEvents"
            ],
            "Resource": "arn:aws:logs:*:*:*"
        }
    ]
}
```

- Trust relationship: lambda.amazonaws.com

## Resources Required
Below are the resources required in the AWS account that will be created.  All are per student unless noted otherwise

- 1 Lambda Function
- 1 Lex Bot
	- 1 Custom Intent
	- 4 Custom Slot Types
- 1 Lambda IAM Role (can be used for all students)
- 1 CloudWatch Logs Group


## Other Note
Users are optionally given instruction for creating a mobile application or web app which can be used to integrate Amazon Polly for voice into the solution, if they choose to do so they will need access to Cognito, the Amazon Mobile Hub, an Android Device, and to setup a local Android SDK.  If they choose to use the example for a website, they will need an IAM user with access to the Lex bot.