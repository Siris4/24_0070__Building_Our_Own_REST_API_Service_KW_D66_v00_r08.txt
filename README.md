# Cafe & Wifi API

Welcome to the Cafe & Wifi API, a Flask application that allows you to manage and access information about cafes, including their amenities and locations.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Postman Documentation](#postman-documentation)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/cafe-wifi-api.git
    cd cafe-wifi-api
    ```

2. Create a virtual environment and activate it:

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. Install the dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Set up the database:

    ```bash
    flask db upgrade
    ```

## Usage

1. Run the Flask application:

    ```bash
    flask run
    ```

2. Open your browser and navigate to `http://127.0.0.1:5000/` to see the homepage.

## API Endpoints

### Get a Random Cafe

- **URL**: `/random`
- **Method**: `GET`
- **Description**: Returns a random cafe from the database.

### Get All Cafes

- **URL**: `/all`
- **Method**: `GET`
- **Description**: Returns all cafes in the database.

### Search Cafe by Location

- **URL**: `/searchlocation`
- **Method**: `GET`
- **Description**: Searches for cafes by location.
- **Query Parameter**: `location` (string)

### Add a New Cafe

- **URL**: `/add`
- **Method**: `POST`
- **Description**: Adds a new cafe to the database.
- **Form Data**:
  - `name` (string)
  - `map_url` (string)
  - `img_url` (string)
  - `location` (string)
  - `seats` (string)
  - `has_toilet` (boolean)
  - `has_wifi` (boolean)
  - `has_sockets` (boolean)
  - `can_take_calls` (boolean)
  - `coffee_price` (string)

### Update Cafe Price

- **URL**: `/update_price/<int:cafe_id>`
- **Method**: `PATCH`
- **Description**: Updates the coffee price of a cafe.
- **Query Parameter**: `new_price` (string)

### Delete a Cafe

- **URL**: `/delete_cafe/<int:cafe_id>`
- **Method**: `DELETE`
- **Description**: Deletes a cafe from the database.
- **Query Parameter**: `api-key` (string)

## Postman Documentation

You can explore and test the API endpoints using Postman. The detailed Postman documentation is available [here](https://documenter.getpostman.com/view/37008172/2sA3kRJPh5).

## Database Schema

The database schema consists of a single table named `Cafe` with the following columns:

- `id` (integer, primary key)
- `name` (string, unique, not null)
- `map_url` (string, not null)
- `img_url` (string, not null)
- `location` (string, not null)
- `seats` (string, not null)
- `has_toilet` (boolean, not null)
- `has_wifi` (boolean, not null)
- `has_sockets` (boolean, not null)
- `can_take_calls` (boolean, not null)
- `coffee_price` (string)

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes.

## License

This project is licensed under the MIT License.
