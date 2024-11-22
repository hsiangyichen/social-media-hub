# User-Game Service

## Overview

The **User-Game Service** is responsible for managing the relationship between users and games. It provides APIs for linking games to users, unlinking them, and retrieving the list of games associated with a specific user.

## Features

- **Link Game to User**: Allows linking a game to a specific user.
- **Unlink Game from User**: Removes the association of a game from a specific user.
- **Get User's Games**: Retrieves the list of games associated with a given user.

## Tech Stack

- Language: TypeScript (Node.js)
- Database: MongoDB
- Framework: Express.js
- Testing: Jest (Unit and Integration Testing)
- Containerization: Docker

## Project Structure

- `controllers/`: Defines the request handlers for the API endpoints.
- `services/`: Contains the business logic, such as linking/unlinking games and managing user-game relationships.
- `repositories/`: Handles data access logic (currently uses in-memory storage but can be extended for database integration).
- `routes/`: Handles the API routing and mapping.
- `schemas/`: Contains the data validation schemas (if applicable).

## Rationale for Implementation

1. **MongoDB**: MongoDB was chosen for its flexibility with unstructured data and ease of use with Node.js applications.
2. **Clean Structure**: The project is structured into distinct layers (controllers, services, repositories) to ensure clear separation of concerns, which makes the code more maintainable and easier to scale.
3. **TypeScript**: Using TypeScript to provides type safety, reducing potential runtime errors by catching them during development.
4. **Testing**: The service includes unit tests covering the core functionalities of linking and unlinking games to users and retrieving user games, ensuring that we meet the 100% test coverage requirement.

## How to Run the Service

### Prerequisites

- Node.js (v14 or later)
- Docker

### Running Locally

1. Install dependencies:

   ```bash
   npm i
   ```

2. Start the service:

   ```bash
   npm start
   ```

3. The service should now be running on `http://localhost:3002`.

## API Endpoints

| HTTP Method | Endpoint      | Description                                 | Request Body                                   | Response                                           |
| ----------- | ------------- | ------------------------------------------- | ---------------------------------------------- | -------------------------------------------------- |
| POST        | `/user-games` | Links a game to a user.                     | `{ "gameId": "string", "username": "string" }` | Success message or error details.                  |
| GET         | `/user-games` | Retrieves a list of games linked to a user. | `?username=string` (as query parameter)        | An array of game objects associated with the user. |
| DELETE      | `/user-games` | Unlinks a game from a user.                 | `{ "gameId": "string", "username": "string" }` | Success message or error details.                  |
