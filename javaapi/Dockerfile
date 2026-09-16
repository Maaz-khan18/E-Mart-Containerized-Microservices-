FROM maven:3.9.9-eclipse-temurin-8 AS build
WORKDIR /usr/src/app/
COPY ./ /usr/src/app/
RUN mvn -B -DskipTests -Dmaven.wagon.http.retryHandler.count=5 clean package

FROM eclipse-temurin:8-jdk

WORKDIR /usr/src/app/
COPY --from=build /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar

EXPOSE 9000
ENTRYPOINT ["java","-jar","book-work-0.0.1.jar"]
# Test
