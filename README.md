# Getting Started

A simple rest server written in Java 11, Spring and Docker.<br>
It uses the https://github.com/guikeller/tides to do the heavy work.<br>
You will be able to get tide stations and tides for a given station on a given date. 

### Pre-requisites
Install the following tools / framework:

* Java 11
* Maven 3
* Docker

Install the https://github.com/guikeller/tides dependency into your maven repo.<br>
Download the jar from: https://github.com/guikeller/tides/releases/tag/0.0.3
```bash
mvn install:install-file -Dfile=jtides-0.0.3.jar -DgroupId=com.github -DartifactId=jtides -Dversion=0.0.3 -Dpackaging=jar
```

### Build 
Follow the steps below:

```bash
mvn clean package -DskipTests
docker build -t open-tides/open-tides:latest .
```

### Run
To run the server do the following
```bash
docker run --name open-tides -p 8080:8080 open-tides/open-tides:latest
```

### Docker Compose
To run it using docker-compose
```bash
cd docker-compose
docker-compose up -d
```

### Endpoints
Date format: YYYY-MM-DD
```bash
curl http://localhost:8080/api/open-tides/tideStations
curl http://localhost:8080/api/open-tides/tideStationsTree
curl http://localhost:8080/api/open-tides/highLowTides?tideStation=Bolama,%20Guinea-Bissau&tideDate=2021-06-03
curl http://localhost:8080/api/open-tides/hourlyTides?tideStation=Bolama,%20Guinea-Bissau&tideDate=2021-06-03
```

### License

MIT - Enjoy!

## Project supported by JetBrains
<p>
 Many thanks to Jetbrains for kindly providing a license for me to work on this and other open-source projects.
 <br>
 <a href="https://www.jetbrains.com/?from=7505-idea-jetty-runner">
   <img alt="Jetbrains" src="https://raw.githubusercontent.com/guikeller/blob/master/jetbrains.png" width="250" height="250">
 </a>
 <br>
 <a href="https://www.jetbrains.com/?from=7505-idea-jetty-runner">
   https://www.jetbrains.com
 </a>
 <br>
</p>
