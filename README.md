# Spring Books - Hello GraphQL

This is a demo project that will introduce you to [https://spring.io/projects/spring-graphql](Spring for GraphQL). 
The Spring Boot application uses Spring for GraphQL and creates a single endpoint at `/graphql` for all GraphQL queries.
If you want to test out the application you can use the GraphiQL UI located at http://localhost:8080/graphiql

If you want to learn more you can check out my Intro to Spring for GraphQL article + video over on my blog: 

TODO: Add Blog Post Here

## Development 

- Run the Spring Boot application which will run on port 8080
- Run the Vue application (/src/frontend) with the command `npm run dev` and it will start up on port 3000

## Packaging 

When you run `mvn clean package` command the frontend Vue application will be built into the `/dist` directory. 
The Maven plugin maven-resources-plugin will copy the contents of the build directory into `/target/static/classes`. 
Once the artifact has been created you can run the application using the following command: 

` java -jar target/spring-books-0.0.1-SNAPSHOT.jar`


## Advantages of GraphQL over REST
1. You can specify which fields should be return on the API call itself - means fewer bandwidth on slow internet
2. You make one call to the backend - one request - which executes multiple `endpoints` - see example below. This means better performance and reducing
overfetching or underfetching in API's
```
query {
  findOne(id: 1) {
    title
  }
  allBooks{
    title
  }
}
```

## Advantages of REST over GraphQL
1. HTTP Caching - this is not possible in GraphQL and has to be custom build
2. Monitoring and Error Reporting - GraphQL is one endpoint and HTTP is always 200 - so hard to monitor and track errors

https://www.imaginarycloud.com/blog/graphql-vs-rest/
