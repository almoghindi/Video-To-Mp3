# Video to MP3 Converter

The Video to MP3 Converter is a Python-based application designed to convert video files to MP3 format using a microservices architecture. The project leverages Flask for the web framework, MySQL and MongoDB for databases, AWS S3 for file uploads, RabbitMQ for queue messaging, and Docker and Kubernetes for containerization and orchestration.

## Features

- **Authentication with JWT:** Secure user authentication using JSON Web Tokens.
- **File Conversion Service:** Converts video files to MP3 format.
- **Email Notification Service:** Sends notifications to users after the conversion is complete.

## Technologies

- **Backend:** Python, Flask
- **Microservices Architecture**
- **Databases:** MySQL, MongoDB
- **File Storage:** AWS S3
- **Queue Messaging:** RabbitMQ
- **Containerization:** Docker
- **Orchestration:** Kubernetes

## Getting Started

### Prerequisites

- Python and Flask installed
- Docker and Docker Compose installed
- Kubernetes cluster set up (e.g., Minikube or a cloud provider)
- AWS account with S3 bucket configured
- RabbitMQ server

### Installation

1. **Clone the Repository:**
    ```bash
    git clone https://github.com/yourusername/videotomp3converter.git
    cd videotomp3converter
    ```

2. **Set Up Environment Variables:**
    Create a `.env` file in the root directory with the necessary environment variables:
    ```env
    MYSQL_DATABASE=your_mysql_database
    MYSQL_USER=your_mysql_user
    MYSQL_PASSWORD=your_mysql_password
    MONGODB_URI=your_mongodb_uri
    AWS_S3_BUCKET=your_aws_s3_bucket
    JWT_SECRET=your_jwt_secret
    RABBITMQ_URL=your_rabbitmq_url
    EMAIL_HOST=your_email_host
    EMAIL_PORT=your_email_port
    EMAIL_USER=your_email_user
    EMAIL_PASS=your_email_password
    ```

3. **Build and Run Services with Docker Compose:**
    ```bash
    docker-compose up --build
    ```

4. **Deploy to Kubernetes:**
    ```bash
    kubectl apply -f k8s/
    ```

## Microservices Overview

### Authentication Service
- **Functionality:** Manages user authentication and issues JWT tokens.
- **Key Features:**
  - User registration and login.
  - Token generation and validation.

### File Conversion Service
- **Functionality:** Converts video files to MP3 format.
- **Key Features:**
  - Upload video files to AWS S3.
  - Convert videos to MP3.
  - Store conversion metadata in MongoDB.

### Email Notification Service
- **Functionality:** Sends email notifications after file conversion.
- **Key Features:**
  - Queue messages with RabbitMQ.
  - Send emails upon conversion completion.

## Usage

1. **Register and Login:**
   - Use the authentication service to register and obtain a JWT token.
   - Include the JWT token in the Authorization header for subsequent requests.

2. **Convert Files:**
   - Upload video files to the conversion service.
   - The service will process the conversion and store the MP3 file in AWS S3.

3. **Receive Notifications:**
   - After conversion, an email notification will be sent to the user.

