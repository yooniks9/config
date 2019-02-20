## Allow IAM user to use lightsail
#### ref : https://lightsail.aws.amazon.com/ls/docs/en/articles/create-policy-that-grants-access-to-amazon-lightsail
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "lightsail:*"
            ],
                "Resource": "*"
        }
    ]
}
```
