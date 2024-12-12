# Viper Authentication Server

Viper is a robust and high-performance authentication server built using the **FastAPI** framework. Inspired by the viper snake—a symbol of safeguarding vital information—Viper provides secure authentication and permission-based access token services for client applications. The app adheres to modern security standards and utilizes the latest technologies to deliver a fast and reliable solution.

## Features

- **Authentication and Authorization**: Supports user authentication and role/permission-based access control.
- **OAuth 2.0 and OpenID Connect (OIDC)**: Implements industry-standard protocols for secure token-based authentication.
- **Modern Technologies**:
  - **FastAPI**: High-performance API framework.
  - **SQLAlchemy**: Database ORM for managing user data efficiently.
  - **Pydantic**: Data validation and serialization.
  - **Python asyncio**: Asynchronous programming for improved performance.
- **PostgreSQL**: Reliable and scalable database for data storage.

## Use Cases

- User authentication for client applications.
- Issuing and validating access tokens for secure API access.
- Managing role-based permissions and access control.
- Educational purposes for understanding authentication and authorization concepts.

## Prerequisites

- **Python**: Version 3.9 or higher.
- **PostgreSQL**: Installed and configured.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/viper-auth-server.git
   cd viper
   ```

2. Set up a virtual environment:
   ```bash
   pipenv shell
   ```

3. Install dependencies:
   ```bash
   pipenv install
   ```

4. Configure environment variables:
   Create a `.env` file in the root directory with the following:
   ```env
   DATABASE_URL=postgresql://username:password@localhost:5432/viper
   SECRET_KEY=your_secret_key
   TOKEN_EXPIRY_MINUTES=30
   ```

5. Apply database migrations:
   ```bash
   alembic upgrade head
   ```

6. Start the server:
   ```bash
   uvicorn app.main:app --reload
   ```

The API will be available at [http://127.0.0.1:8000](http://127.0.0.1:8000).

## Endpoints

### Authentication
- **POST /auth/login**: Authenticate user and return an access token.
- **POST /auth/register**: Register a new user.
- **POST /auth/refresh**: Refresh an expired token.

### User Management
- **GET /users/**: Retrieve details of a all users (admin-only).
- **GET /users/{user_id}**: Retrieve details of a specific user (admin-only).

### Permissions
- **POST /permissions**: Define new permissions (admin-only).
- **GET /permissions**: List available permissions.

## Technologies Used

- **FastAPI**: API framework for building web applications.
- **SQLAlchemy**: Database ORM for handling complex queries and relationships.
- **Pydantic**: Ensures data validation and correctness.
- **PostgreSQL**: Database for secure and efficient data storage.
- **OAuth 2.0 and OpenID Connect**: Standards for token-based authentication and user identity management.
- **Python asyncio**: Enhances performance with asynchronous processing.


## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

Viper was built as a concept understanding app to explore modern authentication techniques and principles. Special thanks to the FastAPI and SQLAlchemy communities for their excellent tools and documentation.

---

Feel free to reach out for any questions or feedback at [support@sahilsharma.co](mailto:support@sahilsharma.co).

