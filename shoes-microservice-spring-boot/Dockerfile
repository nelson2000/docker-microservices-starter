FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install


FROM openjdk:11
WORKDIR /app
COPY --from=build /app/target/shoes-0.0.1-SNAPSHOT.jar .
EXPOSE 1002
CMD ["java", "-jar", "shoes-0.0.1-SNAPSHOT.jar" ]