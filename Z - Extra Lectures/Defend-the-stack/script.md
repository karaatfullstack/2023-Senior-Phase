# Defend the Stack

Contributions by David Adewoyin and Ben Rodriguez

## Script

An assortment of questions to ask students based on the technology. 

### React

- Why use React (instead of using plain native Javascript)?
  - _Virtual DOM_ - try to push students towards mentioning the Virtual DOM. If they do, ask them for a general idea of how it works. If they don't bring it up at the end, bring it up & explain (generally) how it works.
  - _Modularity_ - easier to stay DRY (Don't repeat yourself). Better structuring (& testing) of the application
  - _Single Page Application_ - students tend to mention this as their first reason. Consider this the brute force solution to this problem and try to push students to mention the two listed above. 

- What's the difference between a class (smart) component & a functional (dumb) component?
  - Class components have state. Functional components do not.
  - Class components come with lifecycle methods such as componentDidMount. Functional components do not.

- Which is better to use regularly? Class components or functional components? Why? (Consider this a follow up from question above)
  - Functional components are better to use regularly (if possible)
  - Easier to test a functional component since it doesn't have state
  - Less prone to bugs using functional components. Not every component needs state, lifecycle methods, etc

### Redux

- Do you have to use Redux with React? Can you use it on its own?
    - You _can_ use Redux on its own. Redux is a state management library that is completely independent from React. 

- Why use Redux when React can handle state on its own?
    - Having an application with a lot of state can be troublesome to manage
    - Only using React forces you to properly plan how "high or low" you place your state since you can't pass state back up
    - This can lead to "props hell", where you have to pass props multiple levels down, which introduces complexity

- What does a reducer do? Why is it important for a reducer to be _pure_?
    - Pure reducers are _deterministic_. When you give it the same input, it'll always return the same output
    - Impure reducers violate this since the output will now depend on the same input _and_ the same state of the application
    - See [this](https://stackoverflow.com/questions/44767160/why-are-pure-reducers-so-important-in-redux) for more


### Sequelize

- What is Sequelize?
    - An Object Relational Mapper (ORM)
    - Allows you to _query_ your _relational_ database
    - Writes the SQL queries for you so you don't have to
    <!-- - Works underneath the hood by translating your Javascript objects (models) to relational info (tables) & vice-versa -->

- What is the difference between PostgreSQL and Sequelize?
    - PostgreSQL is a relational database management system. It is used to store persistant information for an application.
    - Sequelize is an object relational mapper. It is used to _query_ a relational database such as PostgreSQL.


### PostgreSQL

- What does it mean for a database to be relational?
- What are some differences between a relational & a non-relational database?
- Why use one database over the other?