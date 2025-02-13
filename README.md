# Photoz Clone

## Overview

Photoz Clone is a simple Spring Boot REST API for uploading, retrieving, and deleting photos. It uses an H2 in-memory database for storage and follows a layered architecture with models, repositories, services, and controllers.

## Features

- Upload photos via a REST API
- Retrieve all uploaded photos
- Retrieve a photo by ID
- Download photos
- Delete photos

## Technologies Used

- **Spring Boot 3.3.0**
- **Spring Web** (for REST API)
- **Spring Data JDBC** (for database access)
- **Spring Boot Validation**
- **H2 Database** (for in-memory storage)
- **Maven** (for dependency management)

## Project Structure

```plaintext
photoz-clone/
│── src/
│   ├── main/java/com/ezahema/photoz/clone/
│   │   ├── model/        # Entity classes
│   │   ├── repository/   # Data access layer
│   │   ├── service/      # Business logic layer
│   │   ├── web/          # REST controllers
│   │   ├── PhotozCloneApplication.java # Main application entry point
│   ├── test/java/com/ezahema/photoz/clone/ # Test cases
│── pom.xml              # Maven configuration
│── .gitignore           # Git ignore rules
│── README.md            # Project documentation
```

## API Endpoints

### **Upload a Photo**

**POST** `/photoz`

#### Request

- `multipart/form-data`
- **Parameter:** `data` (file)

#### Response

```json
{
  "id": 1,
  "fileName": "example.jpg",
  "contentType": "image/jpeg"
}
```

### **Get All Photos**

**GET** `/photoz`

#### Response

```json
[
  {
    "id": 1,
    "fileName": "example.jpg",
    "contentType": "image/jpeg"
  }
]
```

### **Get a Photo by ID**

**GET** `/photoz/{id}`

#### Response

```json
{
  "id": 1,
  "fileName": "example.jpg",
  "contentType": "image/jpeg"
}
```

### **Download a Photo**

**GET** `/download/{id}`

#### Response

- Returns the file as an attachment.

### **Delete a Photo**

**DELETE** `/photoz/{id}`

#### Response

- `204 No Content`

## Running the Project

### Prerequisites

- Java 17+
- Maven

### Steps

1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/photoz-clone.git
   cd photoz-clone
   ```
2. Build and run the application:
   ```sh
   mvn spring-boot:run
   ```
3. Access the API at `http://localhost:8080/`

## Future Improvements

- Add user authentication
- Support for external databases (MySQL, PostgreSQL)
- Frontend UI for photo management

## License

This project is open-source and available under the MIT License.

