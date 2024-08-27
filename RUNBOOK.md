# Deploy
## General info
Runbook 

## FrontendDockerfile
FROM node:14.17.4

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]


## Database
1. Download and install the last version of PostgreSQL https://www.postgresql.org/download/
2. Configure your username, password and connection url in `hibernate.properties` file

##Redis
1. Download and install the last version of Redis  https://redis.io/download
2. Configure connection url in `cache.properties` file

## Starting backend server using IntelliJ IDEA and Tomcat
1. Download and install the Ultimate version of IntelliJ IDEA (alternatively you can use a trial or EAP version) https://www.jetbrains.com/idea/download
2. Download and install Tomcat 9.0.50 https://tomcat.apache.org/download-90.cgi
3. Start the IDE and open class_schedule.backend project from the folder where you previously download it.
4. Make sure Tomcat and TomEE Integration is checked (`File –>> Settings –>> Plugins`).
5. `Run –>> Edit Configurations…`
6. Clicks `+` icon, select `Tomcat Server –>> Local`
7. Clicks on “Server” tab, then press `Configure...` button and select the directory with Tomcat server
8. Clicks on “Deployment” tab, then press `+` icon to select an artifact to deploy, and select `Gradle:com.softserve:class_schedule.war`
9. Press OK to save the configuration
10. `Run –>> Run 'Tomcat 9.0.50'` to start the backend server

## Starting frontend server using Node.js
1. Download and install Node.js 14.17.4 LTS version https://nodejs.org/en/
2. Open a terminal in `/frontend` directory of the downloaded project and run the following command.

       npm install
3. After the installation is finished run the following command to start the frontend server

       npm start
