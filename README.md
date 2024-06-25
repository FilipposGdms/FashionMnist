# Soteria Nudge Engine

The Soteria Nudge Engine is a backend service designed to provide safety messages to users based on their mode of transport, time of day, location type, and weather conditions. It is built using FastAPI and MongoDB and runs inside Docker containers for easy deployment.

## Technology Stack

### FastAPI
FastAPI is a modern, fast (high-performance), web framework for building APIs with Python 3.6+ based on standard Python type hints. It is designed to be easy to use and fast to code with, making it ideal for creating robust and high-performance web APIs.

### MongoDB
MongoDB is a source-available cross-platform document-oriented database program. Classified as a NoSQL database program, MongoDB uses JSON-like documents with optional schemas. It is known for its high performance, high availability, and easy scalability.

### Docker
Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. With Docker, you can manage your infrastructure in the same ways you manage your applications.

## Features

- Provides safety messages to users based on various conditions
- Uses FastAPI for the backend
- Uses MongoDB for data storage
- Containerized using Docker for easy setup and deployment

## Requirements

- Docker
- Docker Compose

## Setup and Installation

### Clone the Repository

```sh
git clone https://github.com/yourusername/soteria-nudge-engine.git
cd soteria-nudge-engine

```

## Directory Structure 
The project directory should have the following structure:

```sh
soteria-nudge-engine/
├── Dockerfile
├── Dockerfile.init
├── README.md
├── app/
│   ├── main.py
│   └── ... (other application files)
├── docker-compose.yml
├── insert_data.py
├── mongodb.Dockerfile
└── requirements.txt
```


## Confuguration
Ensure the docker-compose.yml file is configured correctly. By default, it includes the necessary services and configurations for the nudge engine and MongoDB.

## Build and Run the Containers
Build and run the Docker containers using Docker Compose:

```sh
docker-compose up --build
```

This command will:

- Build the Docker images for the MongoDB service, the nudge engine service, and the data initialization service.
- Start the MongoDB container and the nudge engine container.
- Run the insert_data.py script to populate the MongoDB database with initial data.

## API Endpoints

- The nudge engine API runs on port 8000
- Exmaple endpoint to get a response :

```sh
curl -X POST "http://localhost:8000/api/v1/message" -H "Content-Type: application/json" -d "{\"userId\": \"user123\", \"tripStatus\": \"pre-trip\", \"location\": {}, \"speed\": 10, \"userProfile\": {\"primaryTransportMode\": \"bike\"}}"
```

You should receive a response that looks like this :
```sh
{"message":"Please ensure your safety equipment, like helmets and knee pads, are secured."}
```




