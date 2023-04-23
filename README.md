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
* rent virtual machines (EC2) called instances  
* storing data on virtual devices (EBS)  
* distribute load across machines (ELB)  
* scale service using auto-scaling group (ASG)  
EC2 is fundamental .. important to know  

EC2 sizing and configuration options include: 
* OS for EC2 instances -> Linux, Windows and Mac OS  
* How much computer power and cores (CPU)  
* How much RAM  
* How much storage space  
  * Network attached (EBS & EFS)  
  * hardware (EC2 instance store)  
* Network card: speed of card, Public IP address
* Firewall rules:security group  
* Bootstrap script (configure at first launch): EC2 user data  

You bootstrap instances using EC2 user data script  
Bootstrapping = launching commands when a machine starts so a BS script runs only once at the instance first start  
you automate tasks using EC2 user data script such as  
* installing update
* installing software 
* downloading common files from internet
* anything u can think of

EC2 data script runs with root user so all commands will have psudo rights  
for EC2, u choose a kind of instance like (t2.micro, t2xlarge, or m5.8xlarge etc, each codes with its own vCPU, Mem, storage, network performance and EBS bandwidth)  

Hands on, EC2 experience  

Launching an instance: 
* Name Tag : anything 
* Application and OS image (AMI)(Amazon Machine Image): Amazon Linux (but can choose others) 
* Architecture 64x
* Instance type: t2.micro (free) 
* key pair: Not needed if using SSH utility for accessing, RSA = RSA encrypted private and public key, 
* Windows 10 or higher -> .pem, less than windows 10 -> .ppk (putty) private key format 

<!---
#!/bin/bash
# Use this for your user data (script from top to bottom)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
-->

When u stop and start an instance, the public ip changes, private does not change, so u need to the new public ip to visit the website  
different types of EC2 instances : https://aws.amazon.com/ec2/instance-types/  
each type of instance has different families.. e.g. general purpose has mac, t4g, t3 ....  
m5.2xlarge, m = instance class, 5 = generation (hardware based), 2x large = size within the instance class  
General purpose instances are great for diversity of workloads such as web servers or code repo  
Balance between -Computer, -Memory, -Networking  
Computer Optimized instances are great for intensive tasks i.e. 
* batch processing workloads, 
* media transcoding, 
* high performance web servers, 
* high performance computing, 
* scientific modeling and machine learning, 
* dedicated gaming servers  
normally all compute optimized servers start from C i.e. c5 c6 ..
Memory optimized instances are great for large datasets processing and are great for 
* high performance relational, non relational  
* distributed web scale cache stores  
* in-memory databases optimized for BI (business intelligence)
* applications performing real time processing of big unstructured data 
Normally start from R, X Z...  
Store optimized instances are great for storage intensive tasks that require high sequential read and write access to large data sets  
* high frequency online transaction (OLTP) systems
* relational and nosql databases
* cache for inmemory databases (Redis)  
* data warehousing applications 
* distributed file systems 
* they normally start with I, D or H1
instances.vantage.sh  Instances comparison website  

### Security Groups
video 34: https://www.udemy.com/course/aws-certified-solutions-architect-associate-saa-c03/learn/lecture/26098134#overview  
* fundamental of network security in AWS
* they control how traffic flows
* they only contain allow rules 
* group rules can reference by IP or by security groups 

* security group = firewall on EC2 instances  
they regulate
  * access to ports 
  * authorized IP ranges (IPv4 and IPv6)
  * control of inbound network (from other to instance) 
  * control of outbound network (from instance to other)

* they can be attached to multiple EC2 instances  
* an instance can have multiple security groups too 
* they are locked down to a region / VPC combination (so if u switch to another region, u make another security group) 
* Security groups live outside EC2, if traffic is blocked the EC2 instance wont even see it
* good to maintain one separate security group for SSH access (because it is important and needs to be done correctly so better that an independent security group exists for it)
* if the application is not accessible (time out) its a security group issue  
* if application gives a 'connection refused' error, then its application error or its not launched
* by default, all inbound traffic = blocked, outbound traffic = authorized 
* Referencing other security groups inside a security group: https://imgur.com/a/A7Sbh1b , we do this so we don't need to think of IPs and so all the time  

### Classic Ports
* 22 = SSH (seccure shell) - login into a linux instance 
* 21 = FTP (file transfer protocol) - upload files into a file share 
* 22 = SFTP (secure file transfer protocol) - upload files using SSH 
* 80 = HTTP (access unsecured websites)
* 443 = HTTPS (access secured websites) 
* 3389 = RDP (remote desktop protocl) - log into a windows instance 

hands on...
* go to EC2, start an instance
* go to public IP (http:// IP) 
* check if it works, if it does, go to EC2 / security groups
* delete the http security group that allows access
* reload the website, it wont work (you get time out)  
* all time outs are causes of security groups 100% 
* to make it work, add it back (http security rule) 

### SSH Summary Table
* SSH can be used on mac, linux, windows >=10 , not below 10
* putty works on windows > 10 or < 10 or = 10
* EC2 instance connect uses web browser to connect to EC2 instance connect, and can be used on any device but requires amazon NX2

### SSHing into an EC2 instance
* SSHing means to SSH into an EC2 instance that allows you to control a remote machine, all using the command line 
* Keypair name is needed to SSH into the instance... this is decided when launching an instance  

Steps:
* first you launch an ec2 instance from aws console
* while launching the ec2 instance, you attach a key to it, while attaching , you specify if u want a ppk or a pem file
* a ppk file can be directly opened from putty, a pem file needs to be opened by putty gen and then converted to a ppk file
* to open the instance access in CLI (putty), open putty, put in ec2-user@ public IP of the instance and also load the ppk key saved in SSH-auth-credentials
* open to launch the instance
* do whoami and see the username (ec2-user)  

### Windows 
for windows, use powershell, type ssh and press enter, see if you get something, if u do, ssh works (and I do)  
navigate to the directory with the key file (file downloaded after making the instance  

Videos 40 + - are videos o connect in linux, windows shell, ec2 connect amazon service putty etc  

### EC2 buying
* on demand instances
* reserved (1 & 3 years) 
* savings plan
* spot instances 
