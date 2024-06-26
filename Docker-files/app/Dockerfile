# Use an OpenJDK image to build the project
FROM openjdk:11 AS build_image

# Install Maven and Git
RUN apt update && apt install -y maven git

# Clone the project repository
RUN git clone https://github.com/lagmaraj/vprofile-project.git

# Build the project using Maven
WORKDIR vprofile-project
RUN git checkout docker && mvn install

# Use a Tomcat image to run the application
FROM tomcat:9-jre11

LABEL Project="Vprofile"
LABEL Author="Raju"

# Remove default webapps
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy the built WAR file from the build stage
COPY --from=build_image /vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# Expose the port
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]
