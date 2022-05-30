# product 
https://thegiridhar.com/

##info
this static website is hosted on AWS as static web site on s3 with cloud front distribution and ssl from aws certificate manager 

##Steps to create 
- create a S3 bucket with public access.
- UPLOAD webiste content and link index.html 
- enable static host web hosting under bucket properties
- set bucket policy as below 
- {
    "Version": "2012-10-17",
    "Id": "Policy1569048588734",
    "Statement": [
        {
            "Sid": "Stmt1569048587703",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:*",
            "Resource": "arn:aws:s3:::agsportfolio/*"
        }
    ]
}

created a hosted zone in route53 for my domain
generated a ssl certificate using aws certification manager 
created cloud front distribution using s3 and certificate 
added cloud front end point as A record in R53

##improvement
will migrate to AWS Amplify which provides all the functionalities with CI/CD capabilities 
