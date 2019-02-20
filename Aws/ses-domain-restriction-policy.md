## only allow SES SMTP AMI send with *@domain.com

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ses:SendEmail",
                "ses:SendRawEmail"
            ],
            "Resource": "*",
            "Condition": {
                "StringLike": {
                    "ses:FromAddress": "*@domain.com"
                }
            }
        }
    ]
}
```