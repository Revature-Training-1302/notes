## CI/CD
- Continuous Integration
- Continous Delivery
- Continous Deployment
#### Project 3
Develop a CI/CD pipeline that will at minimum do the following for both the frontend and backend of the application.
- Run existing tests
- Build the application
- Deploy the application

These steps should not run if any previous steps have failed. Code pipeline will help with this requirement because we know that it won't continue to the next step if a previous stage fails.

### Back-End
- Code Build - define how the project is built/tested
    - buildspec.yml file
    - output the zip file to an S3 bucket
- S3 Bucket - store the built project
- Elastic Beanstalk
    - environment that the built project will run on
    - implicitly create an EC2 instance
- RDS - hosting database
    - put the connection configuration in our application.properties file
- Code Pipeline
    - connect the Source Code to the Code Build to the Elastic Beanstalk

### Front-End
- We've seen how to deploy an Angular build to an S3 bucket
- https://enlear.academy/automating-the-deployment-of-an-angular-app-with-a-ci-cd-pipeline-and-aws-2b8b1c46b779
- Code Build - define how the project is built/tested
- S3 Bucket - 
    - store the build of the Angular project
- Code Pipeline -
    - connect the different stages together from source to Code Build to S3 Bucket
