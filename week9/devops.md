## DevOps
- Development Operations
- a set of practices/methodologies designed to combine the development, deployment, and maintenance of code into a streamlined process
    - Usually involving the automation of tasks
    - Structured workflows
    - Striving for efficiency and sustainability

### Steps in Dev Ops
1. Source Code Control - writing code and pushing to a repository
2. Automation - test functionality of code (unit testing) and create a new, working build
3. Deploying to Staging - deploy working code to a temporary environment
4. Acceptance Testing - more complex testing (integration) within temporary environment
5. Deployment of Build - migrate the build to the production environment that is accessible by end users

### Agile and DevOps
- Agile: More flexible and iterative approach to programming and developing
- DevOps: Coming up with a rigid set of steps to follow during our production
- Both strive to make the development process more streamlined and efficient

#### Continuous Integration
- Process of regularly/consistently merging code into a repository, reviewing new code as it comes up to make sure it fits in well with the current code base
- Push/Merge as you go
- Github/Gitlab
- Without CI, you wouldn't have Continuous Delivery or Deployment
- the more frequently you merge code, the fewer issues will arise
- Make sure team is working on the most up to date code
- Identifying failures earlier
- Reducing risks
- TDD - Test Driven Development, writing tests before code

#### Continuous Delivery
- Automating the Source Code Control, Building/Testing, and the deployment to staging
- Leaving acceptance testing and deployment to production to human intervention
- Deployments can be performed "at the push of a button" with human intervention
- We need CI to be set up before we can achieve Continuous Delivery
- Reduced Risk on deployment, detect some issues in the temporary environment
- Predictable progress - iterative builds that indicate overall progress
- Feedback - from developers/client
- Requires CI as well as comprehensive test coverage
- The final step is still human-based, so it's not fully automated
- Need rigorous communication between the development team and client

#### Continuous Deployment
- Every step of the way is automated
- The most attractive of these methodologies because everthing is automated
    - But also the most difficult to achieve in terms of setting up the automation
- Don't need the final, manual approval before the project is deployed to production
- Ensures that all stages of Dev Ops are automated and working together seamlessly
- Need Continuous Integration and Continuous Delivery set up
- Rigorous communication between developers, clients, end users
- More pipelines to manage and maintain
- More efficient workflow, without the need to pause when we deploy to prod.
- Because deployments happen more frequently, new releases are less risky because you'll get quicker feedback
- Regular updates are going to be appreciated

### Monolith Deployment
- Creating our project as one big project rather than many parts working together (Microservices)
- ex: we have one zip file for our back-end
- Microservices - create many different services that work together and serve the large project

### Sonar
- detecting Code Smells Code Quality Analysis
- Code Smells
    - Vulnurabilities
        - Security
    - Bugs
        - Functionality of the code
    - Maintainability
        - Confusing code
        - Repeated code
        - Unused imports
        - Empty code blocks
        - Unaddressed comments
#### Sonar Cloud
- Online website
- Login and connect Github
- Sonar Cloud will perform an analysis of one of your repositories

#### Sonar Lint
- Extension for VS Code
- Plugin for IntelliJ
- Give real-time feedback for code
    - not just compile-time errors, but addressing those code smells