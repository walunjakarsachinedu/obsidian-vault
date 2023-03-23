### Basic Concepts

GraphQL has three basic concepts: Queries, Mutations, and Subscriptions.

1.  **Queries:** Queries are used to retrieve data from a server. They describe the data that you want to get back, and the server will respond with the requested data.
    
2.  **Mutations:** Mutations are used to modify data on a server. They allow you to add, update, or delete data.
    
3.  **Subscriptions:** Subscriptions allow you to receive real-time updates from a server. When data changes on the server, the server will send a message to the client with the updated data.
    

### Syntax

Here's an example of a GraphQL query:
```scss
query {
  user(id: 1) {
    name
    email
    posts {
      title
      content
    }
  }
}
```
This query asks the server for the name, email, and posts of the user with an ID of 1. The response from the server would look something like this:
```json
{
  "data": {
    "user": {
      "name": "John",
      "email": "john@example.com",
      "posts": [
        {
          "title": "My First Post",
          "content": "This is my first post!"
        },
        {
          "title": "My Second Post",
          "content": "This is my second post!"
        }
      ]
    }
  }
}
```

### Schema

In GraphQL, the schema defines the types of data that can be queried or mutated. Here's an example schema:
```typescript
type Query {
  user(id: ID!): User
}

type Mutation {
  createUser(name: String!, email: String!): User
}

type Subscription {
  userUpdated(id: ID!): User
}

type User {
  id: ID!
  name: String!
  email: String!
  posts: [Post!]!
}

type Post {
  id: ID!
  title: String!
  content: String!
  author: User!
}
```

