FROM maven:3.9.11

EXPOSE 8080
WORKDIR /opt/server

# Copy source code
COPY pom.xml .
COPY src ./src

# Build JAR
RUN mvn clean package -DskipTests

# Copy final jar to a stable name
RUN cp target/shipping-1.0.jar shipping.jar

ENV CART_ENDPOINT="cart:8080" \
    DB_HOST="mysql"

# Start app
CMD ["java", "-jar", "shipping.jar"]
