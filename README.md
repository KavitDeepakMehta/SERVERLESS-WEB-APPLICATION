# SERVERLESS WEB APPLICATION USING DIFFERENT AWS SERVICES

## Project Description

Building a Serverless web application using AWS Lambda, DynamodDB, Route 53, CloudFront  and S3. To deploy a simple greeting web application and show how many users have viewed the website on DynamoDB.

## Project Architecture

![Serverless Web Application on AWS](https://github.com/user-attachments/assets/adfb131c-02f6-4503-8009-e3bc13b30ce1)

## Steps
### 1.	Create a Lambda IAM Role
•	Trusted entity type: AWS Service

•	Use Case: Lambda

•	Next

•	Add Permissions: Amazon DynamoDBFullAccess

•	Name: serverless-web-application-on-aws

•	Next, Review and Create Role

### 2.	Create a Lambda Function 
•	Choose Author from scratch

•	Function name: serverless-web-application-kdm

•	Runtime: Python 3.8

•	Architecture: x86_64

•	Use an existing role: serverless-web-application-on-aws

•	Advanced settings: √ Enable function URL 

•	Auth type: ⸰ None

•	Invoke Mode: Buffered (Default)

•	√ Configure CORS

•	Create Lambda Function

### 3.	Create a S3 Bucket
•	Bucket Type: General purpose

•	Bucket name: server-less-web-application-kdm

•	Object Ownership: ACLs disabled

•	Block public access settings for this bucket : √ Block all public access

•	Bucket Versioning: Enable

•	Encryption type: SSE-S3

•	Bucket Key: Enable

•	Object Lock: Disable

•	Create Bucket 

•	Upload HTML, CSS and JS Files in S3 Buckets


### 4.	Create a CloudFront distribution
•	Origin: server-less-web-application-kdm.s3.us-east-1.amazonaws.com

•	Name: server-less-web-application-kdm.s3.us-east-1.amazonaws.com

•	Click on Create new OAC

•	Name: server-less-web-application-kdm.s3.us-east-1.amazonaws.com-1

•	Create

•	Keep Everything else Default

•	Create Distribution

•	Copy the policy and paste it in Created S3 Bucket 

### 5.	In S3 Bucket (server-less-web-application-kdm)
•	Add Bucket Policy

•	Save Changes

### 6.	Go Back to CloudFront
•	In general section, go to settings to edit Default root object as index.tml and Save changes

### 7.	Create hosted zone of your own domain name in Route 53:
•	Domain name: itskdm.online

•	Type: Public hosted zone

•	Create hosted zone

•	Copy and Paste NameServers of AWS in Your Custom Domain’s NameServers and save them

### 8.	Go back to CloudFront
•	Alternate domain name: greeting.itskdm.online

•	Request certificate

•	Next

•	Fully qualified domain name: *.itskdm.online

•	Keep everything else as Default

•	Request

•	Wait for it to be issued

•	Once issued now Go back to Cloudfront>General>Settings>Custom SSL Certificate

•	Attach the certificate

•	Save Changes

### 9.	Go to AWS Certificate manager
•	Create DNS Record by selecting the certificate

### 10.	Now go back to your Route 53
•	CNAME Type Record will be created automatically

•	Now Click on Create Record

•	Record name: greeting

•	Record type: A

•	Alias: 1. Routes traffic to – Alias to CloudFront Distribution

                  2. Select the created cloudfront
•	Routing policy: Simple Routing

•	Create Records

•	Copy and Paste created record in new tab (greeting.itskdm.online)

## Documentation Link: 

https://docs.google.com/document/d/1muS14Kv3thJ4L9v5bmawShCduasijwNjaAKIyQQ-Ig0/edit?usp=sharing

## Expected Outcome:

Upon completing the project, I have a working serverless web application hosted on AWS.
I have hands-on experience building a serverless application using AWS Lambda, Route 53, DynamoDB, S3, CloudFront.
Additionally, I have gained experience working with AWS services and integrating them to build a complete solution.

This project has help me improve my skills in cloud computing, serverless architecture, and AWS services.
