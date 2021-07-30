# Consuming-GraphQL-Apollo
Code repo for course Consuming a GraphQL API with Apollo Client and React on Pluralsight - by Adhithi Ravichandran 

### Run Stript
```js
//both app and api folder
npm start
```
> http://localhost:4000/graphql

### GraphQL Schema with Introspection
-  Retrive a Schema's type
```js
query retriveAllSchemaTypes {
  __schema {
    types {
      name
      kind
      description
    }
  }
}
```
-  Retrive Supported Query / Mutation Types
```js
query retriveQueryMutationType {
  __schema {
    queryType {
      fields{
        name
        description
      }
    }
    mutationType {
      fields {
        name
        description
      }
    }
  }
}
```

-  Retrive Type info
```js
query retriveTypeInfo {
	sessionInfo: __type(name: "Session") {
    fields(includeDeprecated: true) {
      name
      description
      isDeprecated
      deprecationReason
    }
  }
  speakerInfo:__type(name: "Speaker") {
    fields {
      name
      description
    }
  }
}
```
