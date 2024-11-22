# Game Service

## Overview

The **Game Service** is responsible for managing game entities. It provides APIs for creating new games and fetching all available games.

## Features

- **Create Game**: Allows creating new games by specifying the game title.
- **List All Games**: Retrieves a list of all available games.

## Tech Stack

- Language: TypeScript (Node.js)
- Database: MongoDB
- Framework: Express.js
- Testing: Jest (Unit and Integration Testing)
- Containerization: Docker

## Project Structure

- `controllers/`: Handles HTTP requests for linking, unlinking, and listing games associated with users.
- `services/`: Contains the business logic that processes user-game relationships before interacting with the repository layer.
- `repositories/`: Handles data access for the UserGames collection in MongoDB.
- `routes/`: Handles the API routing and mapping.
- `schemas/`: Schema definitions for user-game relationships.

## Rationale for Implementation

1. **MongoDB**: MongoDB was chosen for its flexibility with unstructured data and ease of use with Node.js applications.
2. **Clean Structure**: The project is structured into distinct layers (controllers, services, repositories) to ensure clear separation of concerns, which makes the code more maintainable and easier to scale.
3. **TypeScript**: Using TypeScript to provides type safety, reducing potential runtime errors by catching them during development.
4. **Testing**: The service includes unit tests covering the core functionalities of game creation and listing, ensuring that we meet the 100% test coverage requirement.

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

3. The service should now be running on `http://localhost:3001`.

## API Endpoints

| HTTP Method | Endpoint     | Description                                 | Request Body            | Response                                              |
| ----------- | ------------ | ------------------------------------------- | ----------------------- | ----------------------------------------------------- |
| POST        | `/games`     | Creates a new game.                         | `{ "title": "string" }` | The created game object including its ID and title.   |
| GET         | `/games`     | Retrieves a list of all available games.    | N/A                     | An array of game objects.                             |
| GET         | `/games/:id` | Retrieves details of a specific game by ID. | N/A                     | The game object corresponding to the provided GameID. |
