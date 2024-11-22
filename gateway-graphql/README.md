# gateway-graphql-service

The Gateway service acts as the single entry point for all client requests in the social media application. It aggregates GraphQL APIs from the **User Management Service**, **Post Service**, and **Comment Service** using Apollo Federation.

## Features

- Centralized GraphQL API for User, Post, and Comment services.
- Built using Apollo Gateway for service federation.
- Interactive GraphQL Playground available at [http://localhost:3000/graphiql](http://localhost:3000/graphiql).

## Service Layout

- `__tests__` : Jest test cases for the Gateway service
- `index.js` : Main entry point of the Gateway service
- `resolvers.js` : GraphQL resolvers for aggregating APIs
- `server.js` : Apollo Server configuration and setup
- `typeDefs.js` : GraphQL schema definitions

## Commands

### Install Node Dependencies

    npm i

### Run Server in dev mode with auto-reload on file change

    npm run dev

### Run Server

    npm start

### Run Tests

Run all test cases using Jest:

    npm test

This will execute all tests in the **tests**/ directory and provide coverage reports if configured.

## API Gateway Services

This gateway aggregates the following services:

- User Service: http://localhost:3001
- Post Service: http://localhost:3002
- Comment Service: http://localhost:3003
