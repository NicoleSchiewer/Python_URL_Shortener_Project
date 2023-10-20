# URL Shortener API

This FastAPI-based application provides a simple yet powerful interface for shortening URLs.

## Features

1. **URL Shortening**: Create a short URL for a longer one.
2. **Redirection**: Access the short URL to get redirected to the original URL.
3. **Admin Info**: Each shortened URL comes with a secret key for administration, letting you view information about the URL and its usage.
4. **Deletion**: If you wish, you can delete the shortened URL using its secret key.

## Endpoints

### 1. Home

- **Endpoint**: `/`
- **Method**: `GET`
- **Description**: A basic welcome endpoint for the URL shortener API.

### 2. Create a Short URL

- **Endpoint**: `/url`
- **Method**: `POST`
- **Input**: 
  - `target_url` (string) - The URL you want to shorten.
- **Response**:
  - Information about the shortened URL and its admin link.

### 3. Access Short URL

- **Endpoint**: `/{url_key}`
- **Method**: `GET`
- **Description**: Use the short URL key to get redirected to the original URL.

### 4. Get Administration Info for a Short URL

- **Endpoint**: `/admin/{secret_key}`
- **Method**: `GET`
- **Description**: Obtain details about the shortened URL, like the original URL, its shortened version, and an admin link.

### 5. Delete a Short URL

- **Endpoint**: `/admin/{secret_key}`
- **Method**: `DELETE`
- **Description**: Deactivate and delete the short URL using its secret key.

## Setup & Running

1. **Dependencies**: Ensure you have all the dependencies installed, which includes `fastapi`, `sqlalchemy`, `validators`, and others.
2. **Database**: This application uses a database for storing the shortened URLs. Ensure the database is set up and configured properly.
3. **Settings**: Adjust the settings in the `config` module, particularly the `base_url` setting, which determines the base URL for your short URLs.
4. **Run**: Use a tool like Uvicorn or Hypercorn to run the FastAPI application. Example:
```bash
uvicorn main:app --reload
