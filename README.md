# Travel API

A REST API for managing travel destinations, built with Flask and SQLAlchemy.

## Features

- Create, read, update, and delete travel destinations
- SQLite database for persistent storage
- JSON responses for all endpoints
- Input validation and error handling

## Tech Stack

- **Python 3.11+**
- **Flask 3.1.3** — Web framework
- **Flask-SQLAlchemy 3.1.1** — ORM integration
- **SQLAlchemy 2.0.51** — Database toolkit
- **SQLite** — Database engine

## Getting Started

### Prerequisites

- Python 3.11 or higher
- pip

### Installation

```bash
git clone https://github.com/your-username/flask-api-study.git
cd flask-api-study
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### Running the API

```bash
python main.py
```

The API will be available at `http://127.0.0.1:5000`

## API Endpoints

| Method | Endpoint | Description | Status Code |
|--------|----------|-------------|-------------|
| GET | `/` | Welcome message | 200 |
| GET | `/destinations/` | List all destinations | 200 |
| GET | `/destinations/<id>` | Get a specific destination | 200, 404 |
| POST | `/destinations/` | Create a new destination | 201, 400 |
| PUT | `/destinations/<id>` | Update a destination | 200, 404 |
| DELETE | `/destinations/<id>` | Delete a destination | 200, 404 |

### Request Examples

**POST /destinations/**

```json
{
  "destination": "Paris",
  "country": "France",
  "rating": 4.5
}
```

**PUT /destinations/1**

```json
{
  "destination": "Paris",
  "country": "France",
  "rating": 4.8
}
```

### Response Example

```json
{
  "id": 1,
  "destination": "Paris",
  "country": "France",
  "rating": 4.5
}
```

## Data Model

### Destination

| Field | Type | Constraints |
|-------|------|-------------|
| id | Integer | Primary Key |
| destination | String(50) | Not Null |
| country | String(50) | Not Null |
| rating | Float | Not Null |

## Project Structure

```
flask-api-study/
├── main.py
├── requirements.txt
├── README.md
├── .gitignore
└── instance/
    └── travel.db
```
