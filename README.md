# Sonar Qube and Sonar Scanner running on Docker with database Postgres. 

![](https://github.com/fsaires/sonarqube/blob/master/sonarqube.png)

# What is Sonar?

Sonar is a web based code quality analysis tool for Maven based Java projects. It covers a wide area of code quality check points which include: Architecture & Design, Complexity, Duplications, Coding Rules, Potential Bugs, Unit Test etc. Sonar has a rich set of features like what you would get with different tools such as Covertura, PMD, FindBugs, Check Styles combined.

# Getting started

## Using container

1. Simply run `docker-compose up -d` and go to `http:localhost:9000`. Wait some seconds until Sonar is ready, and log with `admin` password `admin`, and skip the tutorial.

![](https://github.com/fsaires/sonarqube-docker/blob/master/img/login.png?raw=true)

2. Create new project 

![](https://github.com/fsaires/sonarqube-docker/blob/master/img/project.png?raw=true)

3. Generate the Token and going to the terminal and run Sonar Scanner, see the next step. 

![](https://github.com/fsaires/sonarqube-docker/blob/master/img/token.png?raw=true)

4. Now, to perform the code analysis you will need to run the Sonar Scanner, just use the executable in container, at the end of the execution the container will be removed. Run the comand inside your project folder or add the path in `sonar-project.properties`. 

`docker run -e SONAR_HOST_URL=<YOUR_IP>:9000 -it -v ${pwd}:/usr/src --network sonarqube_sonarqube --rm sonarsource/sonar-scanner-cli sonar-scanner`

![](https://github.com/fsaires/sonarqube-docker/blob/master/img/running.png?raw=true)

> Sometimes, on Windows you need to add IP.

3. Wait until analysis finish and check in you dashboard in `http:localhost:9000`

![](https://github.com/fsaires/sonarqube-docker/blob/master/img/analysis.png?raw=true)

> Note that you will need a file to config sonar-project, that file is `sonar-project.properties`, there is all configs to perform you code analysis. See the example file and sample code for more information.

## Documentacion
For more information, access the Sonar Qube docs [Sonar Qube docs](https://docs.sonarqube.org/display/SONAR/Documentation) and [Sonar Scanner Docs](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner)
