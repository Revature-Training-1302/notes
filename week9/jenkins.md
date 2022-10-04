## Jenkins
- Jenkins - self-contained, automation server
    - automate building, testing, deployment of software
- Project/Job - a repeatable set of steps that automate a task
    - Jobs can be triggered manually, externally, or by another job
    - Jobs have health, represented by a weather condition
        - Sunny - more than 80% tests passing
        - Partially Sunny - 61%-80%
        - Cloud - 41% - 60%
        - Raining - 21%-40%
        - Stormy - < 21%
    - Builds have colors
        - blue - success
        - yellow - unstable
        - red - failure
        - grey - no builds

## Blue Ocean
- A way to visualize builds

## Installation
- [Link](https://www.jenkins.io/download/#downloading-jenkins)
- [Instructions](https://www.jenkins.io/doc/book/installing/windows/)
- Next, navigate to http://localhost:8080 and follow the instructions to complete the installation process.

## Demo
- We will follow these instructions for the demo: https://www.jenkins.io/doc/tutorials/build-a-java-app-with-maven/
