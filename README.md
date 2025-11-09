# Doctor Service

Microservice for managing doctor information and availability in the Hospital Management System.

## Overview

The Doctor Service provides CRUD operations for doctor data, department filtering, and availability checking.

## Features

- ✅ Full CRUD operations for doctors
- ✅ Department and specialization filtering
- ✅ Availability checking for specific dates
- ✅ API version `/v1`
- ✅ OpenAPI 3.0 documentation at `/docs`
- ✅ Standard error schema
- ✅ Pagination support

## Quick Start

### Prerequisites

- Python 3.8+
- pip

### Installation

```bash
pip install -r requirements.txt
```

### Running Locally

```bash
python app.py
```

The service will start on `http://localhost:8002`

### Using Docker

```bash
docker build -t doctor-service:latest .
docker run -p 8002:8002 doctor-service:latest
```

### Using Docker Compose

```bash
docker-compose up
```

## API Documentation

Once the service is running, visit:
- Swagger UI: http://localhost:8002/docs
- ReDoc: http://localhost:8002/redoc

## Endpoints

- `GET /v1/doctors` - List all doctors (with pagination and filtering)
- `GET /v1/doctors/{doctor_id}` - Get doctor by ID
- `POST /v1/doctors` - Create a new doctor
- `GET /v1/doctors/{doctor_id}/availability` - Check availability for a date
- `GET /v1/doctors/{doctor_id}/department` - Get doctor's department
- `GET /health` - Health check endpoint

## Environment Variables

- `PORT` - Service port (default: 8002)
- `DATABASE_URL` - Database connection string (default: sqlite:///./doctor.db)

## Kubernetes Deployment

```bash
kubectl apply -f k8s/deployment.yaml
```

## Database Schema

**Doctors Table:**
- `doctor_id` (Integer, Primary Key)
- `name` (String)
- `email` (String, Unique)
- `phone` (String)
- `department` (String)
- `specialization` (String)
- `created_at` (DateTime)

## Clinic Hours

- Start: 9:00 AM
- End: 6:00 PM
- Slot Duration: 30 minutes

## Contributing

This is part of a microservices architecture. For integration with other services, see the main Hospital Management System documentation.

## License

Academic use only.

