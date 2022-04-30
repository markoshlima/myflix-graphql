# **Introduction**

Myflix GraphQL as the name sugest is a simple project about testing graphQL interface with AWS AppSync, and discovery the positives and negatives points about implementing this kind of technology.
The main point is to mapper with resolvers some AWS Dynamodb tables and expose with a GraphQL contract, another objective is compare the performace and how dificult is the implementation/calling between API GraphQL and API Rest.

# **Integration**

![alt text](https://raw.githubusercontent.com/markoshlima/myflix-graphql/main/doc/integration/Integration.png)

In this picture we can see how simple is the architecture, basicly was created a frontend in Angular, and this frontend call both paths in graphQL and rest to get data from AWS Dynamodb. Bellow there is an image with the final frontend result, the data showed is the same, but the interface was not the same.

![alt text](https://raw.githubusercontent.com/markoshlima/myflix-graphql/main/doc/images/frontend-result.png)

# **Conclusion**

GraphQL is known about offer another way to conect services, another from most popular like gRPC and Rest, but there are some points to observe:
- It is not easy to implement all the resolvers like queries, mutations and so on, but the result after everything done could bring agility to implement new features from the products, because all the responsability to join and chose data is from the consumer service.
- There are less network traffic resulting in more performance
- GraphQL could be a problem for governancy strategies


**GraphQL Call**
![alt text](https://raw.githubusercontent.com/markoshlima/myflix-graphql/main/doc/images/graphql-result.png)

**Rest Call**
![alt text](https://raw.githubusercontent.com/markoshlima/myflix-graphql/main/doc/images/rest-result.png)

- In these tests, we can see the AppSync being more expensive to network traffic then the rest calls, but it is because rest traffic is from localhost.

# Addition Information & Setup

- The backend: `myflix-hexagonal`is used to create all data in AWS Dynamodb and the backend rules.
- The folder `config` there is the schema.graphql that could be used inside AWS AppSync
- Also the same folder, there are the resolvers that could be used in the AWS tool as well
- It is needed to created the dynamodb connectors