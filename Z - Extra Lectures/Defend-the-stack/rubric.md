# Defend the Stack: Grading Rubric

Contributions by David Adewoyin and Ben Rodriguez

## Grading Rubric for Grace Shopper

### React

#### Unsatisfactory

- No mention of Virtual DOM
- Only mentions "React helps make SPAs"
- Can't explain the difference between class & functional components

#### Adequate but Needs Work

- Mentions modularity and separations of concerns
- Mentions Virtual DOM, but can't articulate how the Virtual DOM updates the frontend

#### Deeper Understanding

- Talks about the Virtual DOM and how it's a local copy of the DOM
- Talks about the "diff algorithm" and how it compares the previous version of the DOM vs. the current version of the DOM and updates only what is necessary
- Talks about how DOM operations are expensive and updating it all at once especially with how intense our sites are now could affect performance
- Talks about how React helps us keep the UI and state in sync

### Redux

#### Unsatisfactory

- Talks about React & Redux as if they're the same
- "You can't use Redux without React" or vice-versa
- Can't describe the problem Redux is trying to solve

#### Adequate but Needs Work

- Talks about Redux being a centralized place for our state to live and it really becomes useful when we have a lot of state to manage

#### Deeper Understanding

- Mentions how local state can get troublesome to manage, specifically how React is unidirectional
    - For example, putting state "too low" means that other components that may need to share the same state might not be able to "see" state. 
    - For example, putting state "too high" means that you'd have to drill state down through multiple layers of components

- Has an understanding of the various questions one may ask themselves when dealing with state such as
    - What parts of my application care about the specific data?
    - Is the same data being used in multiple components?

- Talks about how reducers are pure functions and how state in Redux is not directly modifiable
    - Also talks about the predictability of state because of pure functions by default not having side effects

### Node

#### Unsatisfactory

- Just talks about it as being a runtime environment with very little context
- Only talks about "everything is in JavaScript"

#### Adequate but Needs Work

- Explains what a runtime environment is 
- Talks about Node being "event-based" with very little context
- Talks about the robust ecosystem (npm modules)

#### Deeper Understanding

- Explains how Node deals with asynchronicity through the Event Loop in clear detail and what benefits it provides


### Express

#### Unsatisfactory

- Just talks about it "being built on top of Node"
- "It's a library"

#### Adequate but Needs Work

- Talks about how it helps us built web applications on top of node
- Talks about how we build our routes in Express

#### Deeper Understanding

- Talks deeper into how we build our routes in Express such as the various HTTP verbs
- Talks about RESTful API architecture pattern
- Talks about the "request-response cycle"
- Talks about how Express let's us write custom middleware to be put anywhere we want in the request pipeline

### Sequelize

#### Unsatisfactory

- Just says it's an ORM with no context on what that means
- Interchangeably uses Sequelize and PostgreSQL

#### Adequate but Needs Work

- Talks about how it makes it easier for applications to talk to databases
- Understands that without it, they would need to write raw SQL
- Understands that it is different from PostgreSQL

#### Deeper Understanding

- Talks about the definition of an ORM: It maps our database tables to models (objects) in JavaScript
- Demonstrates understanding of how Sequelize works behind the scenes
    - Sequelize generates and passes SQL strings to pg (a DB driver)
    - pg connects to PostgreSQL and does whatever it was passed to it
    - data gets passed back to Sequelize and is returned as a JavaScript object

### PostgreSQL

#### Unsatisfactory

- No mention of PostgreSQL being relational
- Can't differentiate

#### Adequate but Needs Work

- Talks about how tables have connections to each other based something called associations and associations are ways to relate data to each other
    - Also talks about the types of associations

#### Deeper Understanding

- Talks about the power of thru tables
- Has an understanding of what kind of data would be adequate in relational DB
    - Static data (data that doesn't change much such as order history)
    - When you have a lot of data that has many relations (Ex: stock data)

#### Data Flow

- They need to be able to demonstrate/diagram a data flow in a part of their application such as from "Clicking add to cart all the way to checkout" and pass through it in their code


## Grading Rubic for Capstone

- Everything from Grace Shopper but with new technologies sprinkled in
- If they describe the reason they use specific new technologies as "We just want to learn something new", that is not adequate enough. They need to demonstrate an understanding of what they are replacing in our stack and what role that new technology fills

### If they use GraphQL

- They need to explain the difference between the traditional RESTful API architecture vs. the GraphQL API architecture
- They should understand it's not a replacement for a DB but a "replacement for rest"

- Instead of having multiple endpoints like REST, there is one endpoint for GraphQL and in order to get data, you write a query (using the GraphQL language) to specific the exact data you want; no more, no less
    - GraphQL solves the “overfetching/underfetching problem” where our REST endpoints can get way too much or way too little data
- GraphQL APIs contain schemas (has nothing to do with DBs) and resolvers
    - Schemas are just how they define relationships among data
    - Resolvers are functions to call the data in our schema
- GraphQL APIs cover all the bounds of our typical CRUD ops
    - Queries are GET (read) requests
    - Mutations are ways GraphQL modify our data and there are 3 types of mutations
        - Create new data
        - Update existing data
        - Delete existing data

    

### If they use a NoSQL document store like Firebase

- They need to demonstrate an understanding of how NoSQL (document stores) compares to SQL
- They also need to understand what tradeoffs happen between the two
    - Flexible and Dynamic Schemas in NoSQL stores
    - Predefined and Static Schemas in SQL stores
    - Can't have many relations in NoSQL Document Stores
        - Can't do complex queries in NoSQL as a result
    - NoSQL doesn't care about data redundancy
    - SQL cares - called normalization
- They also need to understand what types of data would be appropriate for each
    - Ex: Dynamic Data (Something like Github Projects or Trello)

#### They should be able to convert a NoSQL "schema" to a SQL Schema


### If They Use React Native

- They should explain how React Native works behind the scenes and how it achieves mobile development using JavaScript
    - It has two main threads
        - Main: renders all the stuff on the page
        - JavaScript: Executes JS code on another engine
        - They do not directly interact with each other
            - Bridge:
                - Guarantees:
                    - Asynchronous, non blocking comms between threads
                    - Batched: Transfers messages in an optimized way
                    - Serializable: Never share or operate on the same data so they exchange serializable messages

### Data Flow
- They need to be able to demonstrate/diagram a major data flow in a part of their application