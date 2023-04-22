# CloudMode_ON
Me vs Cloud, starting 23/02/2023  
Udemy Links  

# Lectures
## Ultimate AWS Certified Solutions Architect Associate SAA-C03  
https://www.udemy.com/course/aws-certified-solutions-architect-associate-saa-c03/learn/lecture/13528014?start=15#overview  
Video: 27 total hours  
Skill level: All Levels  

## Ultimate AWS Certified Developer Associate 2023 NEW DVA-C02
https://www.udemy.com/course/aws-certified-developer-associate-dva-c01/learn/lecture/11851550?start=60#overview  
Video: 33.5 total hours  
Skill level: All Levels

## AWS Certified DevOps Engineer Professional 2023 - Hands On!
https://www.udemy.com/course/aws-certified-devops-engineer-professional-hands-on/learn/lecture/16049994?start=0#overview  
Video: 20.5 total hours  
Skill level: Intermediate Level

# Exams
## Practice Exams | AWS Certified Developer Associate 2022
https://www.udemy.com/course/aws-certified-developer-associate-practice-tests-dva-c01/learn/quiz/4540356/results?expanded=877878780#overview  
Exams: 6  
Skill level: Beginner Level

## Practice Exams: AWS Certified SysOps Administrator Associate
https://www.udemy.com/course/practice-exams-aws-certified-sysops-administrator-associate/learn/quiz/5107000#overview  
Exams: 4  
Skill level: Beginner Level

## Practice Exams | AWS Certified Solutions Architect Associate
https://www.udemy.com/course/practice-exams-aws-certified-solutions-architect-associate/learn/quiz/4726082/results?expanded=808896788#overview  
Exams: 6  
Skill level: Beginner Level




## ============================================================
## Ultimate AWS Certified Solutions Architect Associate SAA-C03  
https://www.udemy.com/course/aws-certified-solutions-architect-associate-saa-c03/learn/lecture/13528014?start=15#overview  
Video: 27 total hours  
Skill level: All Levels  

## Section 1:  
* AWS = Amazon Web Services (Cloud Provider)  
* On Demand + Easy Scalability  
* AWS = Sphagetti Bowl, all services are linked  
After this course, most learners move on to AWS Certified Developer or AWS Certified SysOps Administrator.   

## Section 2:  
Resources  

## Section 3:
Gartner Magic Quadrant: Magic Quadrant is a series of market research reports published by IT consulting firm Gartner that rely on proprietary qualitative data analysis methods to demonstrate market trends, such as direction, maturity and participants.  
AWS = 47% of the market in 47% followed by Google (22%) + it has 1M + active users  
Uses: Every company has a usecase for the cloud  
Example: Enterprise IT, Backup & Storage, Big Data Analytics, Website Hosting, Mobile and Social Apps, Gaming Servers  
AWS Global Infrared Structure: AWS Regions, AWS Availability Zones, AWS Data Centers, AWS Edge Locations / Points of Presence  
https://aws.amazon.com/about-aws/global-infrastructure/regions_az/  
Regions all around the world, each region has a name  
AWS are region scoped, 

Question: How do you choose an AWS region?  
Factors: 
* Compliance (Government wants data to stay local)  
* Latency (If users in America, stay in america or else lag)  
* Available Services (New services and features aren't available in every region so ensure that where you deploy, does have the service)  
* Pricing (differs from region to region so it depends)  

Availability Zones (AZ)
Each region has many availability zones (min:3, max 6)  
Example: AWS Region Sydney has 3 availability zones named  
ap-southeast-2a, ap-southeast-2b, ap-southeast-2c  
Each zone has data centers, networking, connectivity  
These AZs are separate from each other and are isolated from disasters  
So something happens to ap-southeast-2a will not cascade into 2b or 2c  
These AZs are connected via high bandwith ultra low latency and all together form a region  
AWS has 216 points of presence (205 edge locations & 11 regional caches) in 84 cities across 42 countries  
  
Some AWS Services  
* IAM: Identity and Access Management  
* DNS Service: Route 5  
* Content Delivery Network: Cloud Front   
* WAF: Web Application Firewall  
  
Most AWS services are region scoped  
  
* Infrastucture as a Service (Amazon EC2)  
* Platform as a service (Elastic Beanstalk)  
* Function as a service (Lambda)  
* Software as  service (Rekognition)  
  
There is a region table to check if service is available in your region  
If after choosing a service, the region changes to global, it means its available the same to all regions  
If it doesn't change, its region specific... most are region specific  

## Section 4
### IAM Service
Identity and management global service  
root account created by default shouldn't be used / shared  
users should be created within for the organization and should be grouped  
1 user = 1 person  
Group: Developers, Group: Operations, ... ... Groups can only contain users, and not other groups  
Users can belong to multiple groups, or no groups at all (not good practice)  
We make groups so we can give permissions  
Users or groups can be assigned JSON documents called policies  
This is something like..we "allow" usesrs to use service "EC2:Service Command" on it  
We allow users to use some services ... i.e. define permissions  
We use the __least privilege principle__ (don't give more permissions than a user needs)  

IAM = Global  
Users -> add users (dont use root account)  
U know ur using root because top right shows root id and not user id  
  You can create user, define a password, make him change password on next login and so  
Tags are just for comments / additional information.  
Now that user is created, possible to email the instructions or download a .CSV  
User name -> click user -> shows permissions that he has and if those permissions come from a group  
IMuser is created by / from the original root user and the username on top right differs. IMuser (sub-user)'s username is such as username @ rootuser's id such aa Account ID: 5787-4025-1387  
IAM user: AbdulJunior  
or AbdulJunior@578740251387  

### End of Video 12

IAM Policies  
inline policies are for individuals that maybe don't belong to a group  

policy structure  
{  
"Version":"2023-04-15",  
"Id":"S3-Account-Permissions"   (Identifier for policy)  
"Statement": (square bracket open)    
{  
"Sid":"1",  (statement ID identifier)(optional)   
"Effect": "Allow", (allow / deny)  
"Principal":  {  
"AWS": ["arn:aws:iam::1231231231:root"]  (account / user / role to apply policy to)  
},  
"Action": (square bracket open)  
"s3:GetObject",(list of actions this policy allows / denies)     
"s3:PutObject"  
(square bracket close),  
"Resource": "arn:aws::s3:::mybucket/" 
}  
square bracket close  
close close  

#### Protection  
Password Policy ->1 , Multi Factor Authentication(MFA) ->2  
Minimum password length, specific character type  
Allow users to change or not change their own passwords or password expiration   
Prevent password reuse   
MFA = password u own + device u own  (requires 2 sequential codes for setup instead of the usual one)  
Virtual MFA = google auth , authy, (authy can be used on multiple devices)  
U2F (universal 2nd factor), physical device  

Three ways to access AWS  
* AWS management console (protected by password + MFA)  
* AWS Command line interface (CLI) protected by access keys  
* AWS Software Developer Kit (SDK) - for code, - protected by access keys  

Access keys are generated by AWS console  
access keys are secret like password  
Access key ID: username  
Secret Access Key: password  

Every command in AWS CLI starts from AWS  
from CLI, with access keys, you can use AWS's API  
CLI can be used to manage resources and automate tasks  

SDK -> Software Development Kit  
set of library (SDK is language specific)  
SDK is not something you use with your termnimal, it is something that you embed within your application  
Javascript, python, php, .net, ruby, go, node js, C++  
Also supports mobile SDK,  IoT device SDK (arduino, embedded c)  

### AWS CLI CONFIGURE
open terminal  
type "aws configure"  
type access key, then type secret key, then type region u want to choose,  then enter (none) as output, and AWS CLI is configured  
aws iam list-users  
AWS cloudshell alternative to terminal (cloudshell is terminal inside AWS on the cloud)  
in the cloudshell, u have a full repository, which means that u have place to save files and all files will retain if you restart the cloudshell  
can also download and upload file in cloud  
can have more tabs, can split tabs  
cloudshell doesn't need configuration as its active in the account its opened in (as i believe)  

### IAM ROLES Video 24
we assign permissions to AWS services using IAM roles  
EC2 instance = virtual server  
Common roles: 1- EC2 instance roles, 2- Lambda function roles, 3- Roles for cloud formation  

### IAM Credentials Report  
a report that lists all account's users and status of their credentials  
IAM access advisor (at user level), shows service permissions granted to user and when these services were last accessed (helps with least priviledge principal)  
Access advisor in users shows when a service was last used and shows what permissed granted or alloewd to use that service  


## Section 5
### EC2 Fundamentals  
AWS budget management helps limiting / debugging where money going  
u can set zero spend budget (that informs when all free tiiers are getting exhausted), monthly cost budget, daily savings plan coverage budget, can set buddget to 1$   
notification gets sent to emails specified  

IAM users who are administrators, need a separate checkup so they can configure billing and cost management set (in root account settings, IAM user and role access to billing info)  


EC2 = Elastic Compute Cloud = Infrastructure like a cloud  
Something very cool being widely used everywhere  
EC2 is not just one service, composed of many things  
mainly consists of  
rent virtual machines (EC2) called instances  
storing data on virtual devices (EBS)  
distribute load across machines (ELB)  
scale service using auto-scaling group (ASG)  
EC2 is fundamental .. important to know  

EC2 sizing and configuration options include: 
* OS for EC2 instances -> Linux, Windows and Mac OS  
* How much computer power and cores (CPU)  
* 

~ renting virtual machines 
