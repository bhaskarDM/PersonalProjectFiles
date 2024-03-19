FROM openjdk:11 as BUILD
RUN apt update && apt install maven -y
RUN git clone <provide source code url>
RUN cd folder_name required && git checkout branch_name && mvn install

FROM tomcat:9-jre11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD folder_name/target/*.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh","run"]
