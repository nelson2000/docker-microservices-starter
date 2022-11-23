FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install


FROM openjdk:11
WORKDIR /app
COPY --from=build /app/target/eureka-0.0.1-SNAPSHOT.jar .
EXPOSE 1005
CMD ["java", "-jar", "eureka-0.0.1-SNAPSHOT.jar" ]