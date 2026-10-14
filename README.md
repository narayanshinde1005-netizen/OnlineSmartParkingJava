# Online Smart Parking (Java)

This is a web version inspired by the uploaded Java Swing SmartParkingSystem project. It uses Java 17, Spring Boot, Thymeleaf and an H2 file database. It supports user registration/login, online slot booking, shared slot availability, and an admin booking dashboard with vehicle exit and demo charge calculation.

## Run locally
1. Install JDK 17 or newer and Maven.
2. Open this folder in VS Code.
3. Open Terminal in the project folder and run: `mvn spring-boot:run`
4. Open `http://localhost:8080` in a browser.

## Demo admin login
- Username: `admin`
- Password: `1234`

## Demo rates
Bike ₹20/hour, Car ₹40/hour, SUV ₹50/hour, Other ₹30/hour. Exit billing rounds any started/partial hour up to one chargeable hour.

## Important before public hosting
- This is an academic prototype. Payment is simulated, not a real UPI/bank transaction.
- User passwords are currently stored as plain text for demonstration. Before real public use, add BCrypt password hashing, CSRF/security protections, login rate limits, validation and HTTPS.
- H2 file storage is useful for local testing; on many hosting providers the filesystem may be ephemeral. Configure a persistent disk or managed PostgreSQL database for deployment.
- A public WhatsApp-shareable URL is only available after deploying this app to a Java-capable hosting service. The local URL `http://localhost:8080` works only on the computer running it.

## Deploy
Use a hosting provider that supports Java/Maven builds. Build command: `mvn clean package`; start command: `java -jar target/online-smart-parking-1.0.0.jar`. Set `PORT` if the provider requires it and configure persistent database storage before real use.
