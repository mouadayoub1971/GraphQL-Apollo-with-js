# Games GraphQL API

## Overview
Welcome to the **Games GraphQL API** repository! This project provides a fully functional GraphQL API designed for managing and retrieving information about video games, authors, and reviews. The API enables users to perform various operations such as fetching game details, adding new games, and managing reviews seamlessly through GraphQL queries and mutations.

GraphQL offers a flexible way to interact with data, allowing clients to specify the exact fields they need. This results in efficient data retrieval and better performance compared to traditional REST APIs.

## Getting Started
To set up and run the GraphQL server locally, follow these steps:

### Prerequisites
Ensure you have the following installed on your machine:
- **Node.js** (latest stable version recommended)
- **npm** (Node Package Manager)

### Installation
1. Clone this repository to your local machine:
   ```sh
   git clone https://github.com/your-repo/games-graphql-api.git
   cd games-graphql-api
   ```
2. Install the required dependencies:
   ```sh
   npm install
   ```

### Running the Server
Once the dependencies are installed, you can start the GraphQL server by running:
```sh
npm run dev
```
The server will start and be accessible at **http://localhost:4000**.

To interact with the API, open **GraphQL Playground** (usually available at `http://localhost:4000/graphql`). This interactive environment allows you to test queries and mutations easily.

## GraphQL Schema
The API is structured using a **GraphQL schema**, which defines the types and operations available. The schema is implemented in `schema.js` and consists of the following key types:

### Types
- **Game**: Represents a video game with attributes such as:
  - `id`: Unique identifier for the game.
  - `title`: Name of the game.
  - `platform`: Platform(s) the game is available on.
  - `reviews`: List of reviews associated with the game.

- **Review**: Contains information about a review, including:
  - `id`: Unique identifier for the review.
  - `rating`: Numeric rating given to the game.
  - `content`: Written review content.
  - `game`: Reference to the associated game.
  - `author`: Reference to the reviewer.

- **Author**: Represents an individual who writes reviews, with fields such as:
  - `id`: Unique identifier for the author.
  - `name`: Name of the author.
  - `verified`: Boolean indicating whether the author is verified.
  - `reviews`: List of reviews written by the author.

### Queries
The API supports the following queries to fetch data:
- `games`: Retrieve a list of all available games.
- `game(id: ID!)`: Fetch details of a specific game by its ID.
- `authors`: Get a list of all authors.
- `author(id: ID!)`: Retrieve details of a specific author.
- `reviews`: Fetch all reviews available in the database.
- `review(id: ID!)`: Get details of a specific review.

### Mutations
To modify data, the API provides several mutations:
- `addGame(game: AddGameInput!)`: Add a new game to the database.
- `deleteGame(id: ID!)`: Remove a game from the database by its ID.
- `updateGame(id: ID!, edits: EditGameInput!)`: Update the details of an existing game.

### Input Types
To support mutations, the following input types are defined:
- `AddGameInput`: Structure for adding a new game.
- `EditGameInput`: Structure for updating an existing game.

## Data Structure
The API uses an **in-memory database** to store data, defined in the `db.js` file. This includes sample datasets for games, authors, and reviews.

Since this is an in-memory storage setup, any changes made will be lost when the server restarts. To persist data, you may consider integrating a database like MongoDB, PostgreSQL, or MySQL.

## Customization
Feel free to explore and modify the code to better suit your needs. You can extend the schema, add new fields, or integrate a database to enhance functionality. The modular structure makes it easy to expand and adapt.

Happy coding and enjoy building with the **Games GraphQL API**! 🚀

