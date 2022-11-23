FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install


FROM openjdk:11
WORKDIR /app
COPY --from=build /app/target/offers-0.0.1-SNAPSHOT.jar .
EXPOSE 9999
CMD ["java", "-jar", "offers-0.0.1-SNAPSHOT.jar" ]