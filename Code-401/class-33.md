# GraphQL @connection

GraphQL is an open-source data query and manipulation language for APIs, and a runtime for fulfilling queries with existing data. GraphQL was developed internally by Facebook in 2012 before being publicly released in 2015.

Usage:

- Relationships between types are specified by annotating fields on an @model object type with the @connection directive.
- The fields argument can be provided and indicates which fields can be queried by to get connected objects.
- When specifying a keyName, the fields argument should be provided to indicate which field(s) will be used to get connected objects.

Create a basic GraphQL API

you have to use a custom Amplify GraphQL directive called **@connection**. This creates a link between two fields, and can be implemented per the following:

```graphql
type Topic @model {
  id: ID!
  title: String!
  description: String
  comments: [Comment] @connection(keyName: "TopicComments")
  tags: [Tag]
}

type Tag @model {
  id: ID!
  tag: String
  topics: [Topic]
}

type Comment @model {
  id: ID!
  text: String
  topic: Topic @connection(keyName: "TopicComments")
}
```
