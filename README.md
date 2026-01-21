# FastAPI Address Book Application

## Overview
This is a **minimal REST API** built using **FastAPI** and **Python 3**, demonstrating core backend skills.  
The application allows API users to **create, update, delete, and query addresses** stored in a SQLite database.  
Each address includes **geographic coordinates** (latitude and longitude) and supports **distance-based queries**.

The application does **not have a GUI**. FastAPI's built-in **Swagger UI** is used for API exploration and testing.

---

## Features
- **CRUD Operations**
  - Create, update, delete addresses
  - Validation of input data
- **Distance Query**
  - Retrieve addresses within a specified distance from a given latitude/longitude
  - Uses the **Haversine formula** for accurate distance calculation
- **Database**
  - SQLite database for persistence
  - SQLAlchemy ORM for data access
- **Validation**
  - Input data validated using Pydantic schemas
- **Error Handling**
  - Graceful handling of missing or invalid data

---

## Tech Stack
- Python 3.10+
- FastAPI
- SQLAlchemy ORM
- SQLite
- Pydantic
- Uvicorn

---

## Setup and Execution

### 1. Clone and setup
# Clone the repository
git clone <your-repo-url>
cd fast_api_addressbook

# Create Virtual Environment
python -m venv venv

# Activate Virtual Environment
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# Install Dependencies
pip install -r requirements.txt

### 2. Run the application
uvicorn app.main:app --reload

### 3. Access the API
Open your browser to the interactive documentation: http://127.0.0.1:8000/docs

## API Endpoints

1. POST /addresses - Create a new address
2. GET /addresses/{address_id} - Retrieve specific address
3. PUT /addresses/{address_id} - Update an address
4. DELETE /addresses/{address_id} - Delete an address
5. GET /addresses/nearby/ - Find addresses within distance

## Usage Example
# Create An address post
Endpoint: /addresses/ Sample JSON Payload:

{
  "name": "Indiranagar",
  "latitude": 12.9784,
  "longitude": 77.6408
}

# Find Nearby Addresses (GET)
Endpoint: /addresses/nearby/ Parameters:

latitude: 37.7750
longitude: -122.4180
distance_km: 5.0

----------------------

