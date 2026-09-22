# ☕ Cafe Menu API

A simple read-only REST API built with **FastAPI** for managing and displaying cafe menu items.

This project does not use a database. Menu data is stored in a Python list and exposed through API endpoints.

## 🚀 Features

- View all cafe menu items
- Filter menu items by category
- Get a specific menu item by ID
- Input validation using Pydantic
- Automatic API documentation with Swagger UI
- Proper HTTP status codes and error handling
- No database required

## 🛠️ Technologies Used

- Python
- FastAPI
- Pydantic
- Uvicorn

## 📁 Project Structure

```text
cafe-menu-api/
│
├── main.py
├── models.py
├── data.py
├── requirements.txt
└── README.md
```

The API will be available at:
http://127.0.0.1:8000

## 📚 API Documentation
- FastAPI automatically provides interactive API documentation.

- Swagger UI
http://127.0.0.1:8000/docs

- ReDoc
http://127.0.0.1:8000/redoc


## 🔗 API Endpoints
1. Welcome Endpoint

- GET /
  Returns a welcome message.

Example response:
{
  "message": "Welcome to Cafe Menu API"
}

2. Get All Menu Items

GET / menu
Returns all available menu items.

Example:
GET http://127.0.0.1:8000/menu

Example response:
```{
  "status": "success",
  "count": 10,
  "items": [
    {
      "id": 1,
      "name": "Cappuccino",
      "category": "coffee",
      "price": 140.0,
      "description": "Rich espresso topped with velvety milk foam.",
      "available": true
    }
  ]
}
```
3. Filter Menu by Category
GET /menu?category={category}

Returns menu items belonging to a specific category.

Supported categories:
- coffee
- tea
- sandwich
- bakery
- dessert
- combo

Example:
GET /menu?category=coffee

Example response:
```
{
  "status": "success",
  "count": 4,
  "items": [
    {
      "id": 1,
      "name": "Cappuccino",
      "category": "coffee",
      "price": 140.0,
      "description": "Rich espresso topped with velvety milk foam.",
      "available": true
    }
  ]
}
```
If the category does not exist:
{
  "detail": "No item found in category: pizza"
}

HTTP status:
404 Not Found


4. Get Menu Item by ID

GET /menu/{item_id}
Returns a specific menu item using its ID.

Example:
GET /menu/1

Example response:
```
{
  "id": 1,
  "name": "Cappuccino",
  "category": "coffee",
  "price": 140.0,
  "description": "Rich espresso topped with velvety milk foam.",
  "available": true
}

If the item does not exist:
{
  "detail": "Menu item with id 99 not found"
}
```

HTTP status:
404 Not Found


## 🧪 Testing the API
You can test the API using:

- Swagger UI
- Postman
- Browser
- curl

Example using curl:
curl http://127.0.0.1:8000/menu 

Filter by category:
curl "http://127.0.0.1:8000/menu?category=coffee"

Get an item:
curl http://127.0.0.1:8000/menu/1


## 🎯 Project Purpose

This project demonstrates how to build a basic REST API using FastAPI without depending on a database.

It is suitable for use cases such as:

- Cafe kiosk displays
- Mobile applications
- Digital menu systems
- Internal cafe applications
- API development practice
- 🔮 Future Improvements

The current version intentionally does not use a database.

## Possible future improvements:

- Add PostgreSQL/MySQL database
- Add CRUD operations
- Add authentication
- Add admin endpoints
- Add menu item search
- Add pagination
- Add automated tests
- Dockerize the application
- Deploy the API to the cloud

# 👨‍💻 Author
Uppula Kalyan 

