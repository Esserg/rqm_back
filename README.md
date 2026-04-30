# Random Quote Machine (Backend)

Это backend-часть приложения для выдачи случайных фраз. Проект написан на Java с использованием фреймворка Spring Boot.

## Требования
- Java 21
- PostgreSQL (или Docker для запуска базы данных)
- Maven (опционально, так как в проекте есть `mvnw`)

## Настройка базы данных
По умолчанию приложение ожидает базу данных PostgreSQL со следующими параметрами (можно переопределить через переменные окружения):
- **DB_HOST**: `localhost` (по умолчанию)
- **DB_PORT**: `5432` (по умолчанию)
- **DB_NAME**: `random_quote_machine` (по умолчанию)
- **DB_USER**: `postgres` (по умолчанию)
- **DB_PASSWORD**: `postgres` (по умолчанию)

Для быстрого старта базы данных в Docker выполните:
```bash
docker run --name rqm-postgres -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=random_quote_machine -p 5432:5432 -d postgres
```

## Сборка проекта
Для сборки проекта используйте Maven Wrapper, который идет в комплекте:
```bash
# На Linux/macOS
./mvnw clean package

# На Windows
mvnw.cmd clean package
```

## Запуск приложения
Запустить приложение можно несколькими способами:

### Способ 1: Через Maven Wrapper (для разработки)
```bash
# На Linux/macOS
./mvnw spring-boot:run

# На Windows
mvnw.cmd spring-boot:run
```

### Способ 2: Запуск собранного JAR-файла (для production)
После сборки проекта в папке `target` появится `.jar` файл. Выполните:
```bash
java -jar target/rqm_back-0.0.1-SNAPSHOT.jar
```

Приложение будет доступно по порту **8080**.
