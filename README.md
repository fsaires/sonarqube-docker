# Sonar Qube and Sonar Scanner running on Docker

![](https://github.com/fsaires/sonarqube/blob/master/sonarqube.png)

# What is Sonar?

Sonar is a web based code quality analysis tool for Maven based Java projects. It covers a wide area of code quality check points which include: Architecture & Design, Complexity, Duplications, Coding Rules, Potential Bugs, Unit Test etc. Sonar has a rich set of features like what you would get with different tools such as Covertura, PMD, FindBugs, Check Styles combined.

# Getting started

## Using container

1. Simply run `docker-compose up -d` and go to `http:localhost:9000`. Wait some seconds until Sonar is ready, and log with `admin` password `admin`, and skip the tutorial.

Now, to perform the code analysis you will need run the Sonar runner, just use the executable in container, running: 

`docker exec -it sonarqube sonar-runner`. Wait until analysis finish and check in you dashboard in `http:localhost:9000`.

> Note that you will need a file to config sonar-runner, that file is `sonar-runner.properties`, there is all configs to perform you code analysis. See the example file and sample code for more information.

## Installing plugins

Sonar Qube comes with some plugins installed, but, if your language isn't available, go to Update Center in `http://localhost:9000/updatecenter/`


## Documentacion
For more information, access the Sonar Qube docs [Sonar Qube docs](https://docs.sonarqube.org/display/SONAR/Documentation) and [Sonar Runner docs](https://docs.sonarqube.org/display/SCAN/Analyzing+with+SonarQube+Scanner)
