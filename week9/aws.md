## AWS - Amazon Web Services
- Offer a bunch of online services that let us perform certain actions on the cloud
- Pay-As-You-Go
    - Offer services at affordable prices, no upfront costs of setting up data centers
    - Don't have to guess/predict capacity
        - A lot of AWS services are scalable, meaning that will go up/down in size as needed
    - Increased set-up speed
        - Deploy back-end in a minutes
        - Normally, this would take weeks to set up
    - Eliminate over-head costs of maintaining data centers
    - Benefit from massic economies of scale
        - because so many people use AWS services, the price is more convenitent for users
- Similar to Azure which is Microsoft's cloud service

## AWS Regions
- A region is part of the world (US East, US West, US Central, Europe, Asia)
- Within regions are multiple availability zones
    - AZ - Availability Zone
    - AZs are isolated from each other in the same region
    - So, if one AZ was taken down by natural disaster or some other big phenomenon, the other AZ would still be operational, so people's services wouldn't be messed up
    - Redundancy - data could be stored in multiple AZs so if one was destroyed, the data wouldn't be lost
    

### IAM - Identiy Access Management
- Create roles on our account so one person can't control everything
- The root user is the account owner and can assign roles to different users

### EC2 - Elastic Compute Cloud
- provides secure, resizable compute capacity in the cloud
- makes web-scale cloud computing easier
- We can create virtual computing environments (instances)
- Configure CPU, memory, storage, networking capacity
- Secure connections to EC2
- AMI - Amazon Machine Images - template for instances (ex: what operating system we choose)
- Elastic - meaning that we can respond to the traffic flow and scale up/down depending

#### EC2 Auto-Scaling
- Improve fault tolerance - terminatig faulty EC2 instances and replacing them
- Increase availability - predictive scaling, making sure that the instance is available to consumers
- Lower cost - scaling down if we don't need a high performance for lower traffic times
- Groups - collection of EC2 instances with similar characteristics
    - we maintain a fixed number of instances even if one of the instance becomes unhealthy
    - increase the number of instances if we're expecting a lot of traffic
    - decrease the number if traffic is expected to go down

### Security Groups
- Act as a virtual firewall for EC2 instances
    - control incoming and outgoing traffic based on ip address
    - based on protocols/port numbers
    - ex: allow traffic from our own ip address, port 5432 for postgres
- stateful -
    - if we send request from an instance, the reponse will be allowed to flow in regardless of inbound rules
    - if we're sending a response from a request to the instnace, we will be allowed to send that response regardless of outbound rules

### RDS - Relational Database Service
- Instead of running a database server locally, we'll have it hosted on the web
- We'll be able to connect to it from anywhere (as long as we set up the right permissions)
- We can configure storage type, CPU, networking capacity
- When we make RDS, make sure to choose free tier

### S3 - Simple Storage Service
- Host files online
- We can S3 buckets to store any type of file (html, text, pdfs, videos, images, zip files)
- More unstructured than RDS
- Like an online drive
- Specifically, we'll use S3 to host the build of our back-end and front-ends so they can be deployed
- When we build our front-end, we will host the html page on S3 (Static Website Hosting)
    - Our website still has functionality, but we won't set up a pipeline like we did with the back-end
    - Looks at our static index file and deploys that
- Each item in our bucket has a url that we can use to access the item in the bucket
    - We'll have to specify whether it's public or not (default to private)

### Code Build
- Given some sort of code source (Github), Code Build is going to build our project for us based on some commands we give it

### Code Pipeline
- Set up so that, we listen to changes, for example: whenever we push to Github, it will trigger the Code Build to build our project with the latest updates

### Elastic Beanstalk
- The environment that we will run the project on
- The EBS will implicitly create an EC2 instance
- To shut this down and prevent charges (after 750 hours), you must termine EBS (Not the EC2)

### Our Spring Boot Project
1. We'll set up an RDS on AWS and put the credentials in our .properties file. Then, when we run the program, all changes made to the database will affect RDS database rather than our local/H2. 
2. We'll create an S3 bucket that will store our build output.
3. We'll add some configuration files to our source code and then host it on Github.
4. We'll create a Code Build that takes our Github code and builds it into a zip file, which will then be stored in the S3 bucket.
5. Set up our Elastic Beanstalk which takes that zip file and runs the application on the cloud. It will give us a link so that we can access our endpoints. 
6. Set up our code Pipeline so that whenever we make changes to our main branch, it will trigger the build and then deploy the new project on Elastic Beanstalk.

### AWS Account
- Set up our account at this link: https://portal.aws.amazon.com/billing/signup#/start/email
- Because the services cost money, you will put in some card information
    - Make sure to pay attention to the demos to make sure we're always picking the free versions of the services
    - Because you're setting up card information, it is very very important to set up 2 factor authentication

#### 2FA
- Sign in as the root user
- Click on Services -> Security -> IAM, there should be a link to set up MFA.
- Quick Links -> My Security Credentials
- Assign MFA Device -> Authenticator App
- Download the Google Authenticator App (or any Authenticator App)
- Should be an option to scan QR code
    - On google, we click the plus button and then "Scan QR Code"
    - Scan the QR code on the AWS site
    - It will prompt you to enter in 2 codes in order to sync the accounts
    - Click the confirm button
- Now, try signing out and then back in. Make sure that AWS prompts you for the code

#### Create IAM group
- Naviage to the IAM page on AWS
- Click on User Groups and create a new group
- Scroll down to the bottom of the page and select the policies that you want to approve
    - You want to choose the most restrictive policies that still allow the users in the group to do everything they need to do
- Go to Users and add a new User
    - Give them a name
    - Give a temporary password and require them to create a new password when they sign in
- On the permissions tab, select the group that we created earlier
- Can skip tags or add some information
- Navigate to the user and click on security credentials
- Copy the console sign-in link and paste it in a new tab