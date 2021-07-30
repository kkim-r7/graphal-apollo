# Consuming-GraphQL-Apollo
Code repo for course Consuming a GraphQL API with Apollo Client and React on Pluralsight - by Adhithi Ravichandran 

### Run Stript
```js
//both app and api folder
npm i
npm start
```
> http://localhost:4000/graphql

## GraphQL Schema with Introspection
### Retrive a Schema's type
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
### Query / Mutation Types
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

### Aliases 
> The result object fields match the name of the field in the query but do not inclde arguements, 
>
> you cannot directly query for the same field with different arguements.
>
> Aliases let you remane the result or a field.
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
  speakerInfo: __type(name: "Speaker") {
    fields(includeDeprecated: true) {
      name
      description
      isDeprecated
      deprecationReason
    }
  }
}
```
> Reference: https://graphql.org/learn/queries/
