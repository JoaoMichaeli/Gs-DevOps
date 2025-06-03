FROM eclipse-temurin:17-jdk-jammy

RUN groupadd -r appuser && useradd -r -g appuser -d /home/appuser -m appuser

WORKDIR /app

COPY . /app

RUN chown -R appuser:appuser /app /home/appuser

USER appuser

RUN ./mvnw clean install -DskipTests

EXPOSE 8080

ENV APP_ENV=production

CMD ["./mvnw", "spring-boot:run"]
