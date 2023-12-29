This FastAPI-based API provides basic CRUD operations for managing items in a SQLite database.
The API supports creating, reading, updating, and deleting items. It uses SQLAlchemy for database interaction and Pydantic for data validation.

### Setup
Requirements
Python 3.7+
FastAPI
Uvicorn
SQLAlchemy
Installation
Install the required packages:

### bash
pip install fastapi uvicorn sqlalchemy


# Run the application:
### bash
uvicorn main:app --reload

# API Endpoints
1. Create Item
Endpoint: /items
Method: POST
Request Body:
{
  "name": "ItemName",
  "description": "ItemDescription"
}
Response:
{
  "id": 1,
  "name": "ItemName",
  "description": "ItemDescription"
}

2. Read Item
Endpoint: /items/{item_id}
Method: GET
Path Parameters:
item_id: ID of the item to retrieve
Response:
{
  "id": 1,
  "name": "ItemName",
  "description": "ItemDescription"
}

3. Read All Items
Endpoint: /all
Method: GET
Response:

  {
    "id": 1,
    "name": "ItemName1",
    "description": "ItemDescription1"
  },
  {
    "id": 2,
    "name": "ItemName2",
    "description": "ItemDescription2"
  } ...

4. Update Item
Endpoint: /items/{item_id}
Method: PUT
Path Parameters:
item_id: ID of the item to update
Request Body:
{
  "name": "UpdatedItemName",
  "description": "UpdatedItemDescription"
}

Response:
{
  "id": 1,
  "name": "UpdatedItemName",
  "description": "UpdatedItemDescription"
}
5. Delete Item
Endpoint: /items/{item_id}
Method: DELETE
Path Parameters:
item_id: ID of the item to delete
Response:
{
  "id": 1,
  "name": "UpdatedItemName",
  "description": "UpdatedItemDescription"
}


# Curl Commands
Create Item:
curl -X POST -H "Content-Type: application/json" -d '{"name":"ItemName","description":"ItemDescription"}' http://localhost:8000/items

Read Item
curl http://localhost:8000/items/1

Read All Items
curl http://localhost:8000/all

Update Item
curl -X PUT -H "Content-Type: application/json" -d '{"name":"UpdatedItemName","description":"UpdatedItemDescription"}' http://localhost:8000/items/1

Delete Item
curl -X DELETE http://localhost:8000/items/1





