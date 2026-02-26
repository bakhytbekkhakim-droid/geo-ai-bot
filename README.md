# Geo AI Assistant Bot 🌍🤖

Бұл — **Spring Boot**, **PostgreSQL** және **Gemini AI** негізінде жасалған Telegram бот. Жоба географиялық сұрақтарға жауап беруге және пайдаланушыларға көмектесуге арналған.

## 🛠 Технологиялық стек
* [cite_start]**Java 17** (Eclipse Temurin) 
* **Spring Boot 3.2.2**
* **PostgreSQL 15** (Деректер қоры)
* [cite_start]**Docker & Docker Compose** (Контейнеризация) 
* **Telegram Bot API**
* **Gemini API** (Жасанды интеллект)
* **Prometheus & Grafana** (Мониторинг)

## 🚀 Іске қосу нұсқаулығы

### 1. Локалды түрде (Docker арқылы)
Жобаны өз компьютеріңізде іске қосу үшін:
1. Репозиторийді жүктеңіз.
2. `docker-compose.yml` файлындағы `BOT_TOKEN` және `GEMINI_API_KEY` мәндерін өзгертіңіз.
3. Терминалда мына пәрменді орындаңыз:
   ```bash
   docker-compose up --build


---

# Geo AI Bot (Java/Spring Boot Telegram Bot) - English Documentation

This section provides English documentation for the Geo AI Bot. The bot is built with Spring Boot and Java, designed for containerized deployment using Docker, and includes Prometheus for monitoring.

## Features

*   **Telegram Integration:** Responds to user messages via a Telegram bot.
*   **Spring Boot:** Robust and scalable backend framework.
*   **Containerized Deployment:** Ready for Docker deployment with a provided `Dockerfile`.
*   **Monitoring:** Includes Prometheus configuration (`prometheus.yml`) for application metrics.
*   **Database Integration:** Configured for PostgreSQL (via `spring-boot-starter-data-jpa` and `postgresql` dependency).

## Setup Instructions

Follow these steps to get your Geo AI Bot up and running.

### 1. Clone the Repository

```bash
git clone https://github.com/bakhytbekkhakim-droid/geo-ai-bot.git
cd geo-ai-bot
```

### 2. Configure Application Properties

Edit the `application.properties` file located in `src/main/resources/` to set up your Telegram bot token and other configurations.

```properties
# application.properties
telegram.bot.token=YOUR_TELEGRAM_BOT_TOKEN
telegram.bot.username=YOUR_BOT_USERNAME

# PostgreSQL Database Configuration (example)
spring.datasource.url=jdbc:postgresql://localhost:5432/geobot_db
spring.datasource.username=geouser
spring.datasource.password=geopassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

*   **`telegram.bot.token`**: Obtain this from BotFather on Telegram.
*   **`telegram.bot.username`**: Your bot's username on Telegram.
*   **Database Configuration**: Adjust these settings for your PostgreSQL database. If you're not using a database, you might remove `spring-boot-starter-data-jpa` and `postgresql` dependencies from `pom.xml`.

### 3. Build the Application

This project uses Maven. You can build the application using the following command:

```bash
mvn clean package
```

This will generate a JAR file in the `target/` directory.

### 4. Run the Application

You can run the JAR file directly:

```bash
java -jar target/geo-ai-assistant-3.0.0.jar
```

### 5. Run with Docker

This project includes a `Dockerfile` for containerized deployment. Ensure Docker is installed on your system.

**Build the Docker image:**

```bash
docker build -t geo-ai-bot .
```

**Run the Docker container:**

```bash
docker run -p 10000:10000 --name geo-ai-bot-instance geo-ai-bot
```

(Note: The `Dockerfile` exposes port `10000` as per your configuration.)

### 6. Monitoring with Prometheus

A `prometheus.yml` file is provided for basic monitoring setup. You can integrate this with a Prometheus server to collect metrics from your bot.

## Project Structure

*   `src/main/java/com/geobot/`: Main Java source code.
*   `src/main/resources/application.properties`: Application configuration.
*   `pom.xml`: Maven project object model, defining dependencies and build process.
*   `Dockerfile`: Instructions for building a Docker image.
*   `docker-compose.yml`: (If applicable) Docker Compose configuration for multi-service deployment.
*   `prometheus.yml`: Prometheus configuration for monitoring.
*   `.gitignore`: Specifies intentionally untracked files to ignore.

## Contributing

Feel free to fork the repository, make improvements, and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is open-source and available under the MIT License. (Add if applicable)
