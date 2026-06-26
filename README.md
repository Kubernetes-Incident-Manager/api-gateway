# API Gateway

## Overview
The **API Gateway** acts as the single entry point for the Incident Tracker platform. It routes incoming client requests to the appropriate internal microservices, handles cross-cutting concerns such as authentication, authorization, rate limiting, and request logging.

## Features
- Routes HTTP requests to internal services (e.g., incidents-service, analysis-service).
- Aggregates responses from multiple microservices if necessary.
- Manages authentication via tokens and handles basic security policies.
- Built with Python, FastAPI, and `httpx`.

## Getting Started

### Prerequisites
- Python 3.10+
- `pip` package manager
- Docker (optional for containerized deployment)

### Installation
1. Navigate to the service directory:
   ```bash
   cd services/api-gateway
   ```
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Service
To run the service locally for development:
```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

## Docker
Build the Docker image:
```bash
docker build -t incident-tracker/api-gateway .
```
Run the Docker container:
```bash
docker run -p 8000:8000 incident-tracker/api-gateway
```
