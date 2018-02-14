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
}```

- Trust relationship: lambda.amazonaws.com