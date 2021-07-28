## App Details
It is a code snippet for handling real time quizes for student's in a school.

## Frontend
This is a React app built on NextJS framework using typescript. In this app we are using GraphQL as a layer for managing api hits, caching and state. This app also supports real time communication via sockets.

#### QuestionBankHook.ts
This is a custom hook for questions listing, pagination, filteration. It contains all the stateful logic and graphql query to get the data from server.

#### class.tsx
This is a class component which handles class information and contains following features:
 - school name
 - class grade, total students in class
 - students listing and filters

#### quizQuestion.tsx
This is a component to render question on the screen and allow user to answer the question. Based on user input it will notify user if answer is correct or incorrect.


## Backend
Its backend is built in NodeJS using NestJS framework. Backend is using "MongoDB" & "MySql" for persistence storage and "Redis" is used as in-memory cache for handling socket connections & its state.

#### School Module
1. **schools.resolvers.ts:** It contains code for handling different operations related to school like "querying", "updating", "deleting". It is making use of services to perform database operation.
2. **schools.service.ts:** It contains code for connecting to database schema and provide the requested data accordingly

#### Socket Module
1. **socket-state.adapter.ts:** This contains code to initiate and destroy socket connections. Along with that it is also making sure that user is authenticated.
2. **socket-state.module.ts:** Module file generated by nestJS cli for handling services and adapter.
3. **socket-state.service.ts:** This contains logic to add, remove, get Users from socket state. 
