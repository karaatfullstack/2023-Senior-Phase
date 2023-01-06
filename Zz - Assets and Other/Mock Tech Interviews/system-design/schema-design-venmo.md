# Technical Mock Interview

## Overview

We want to be able to pay someone else for a service they offered or sold to us. We also want to be able to request payment as well if we did the same thing.

### Question 

#### Schema Design Venmo (30 mins)

Draw an appropriate schema for a Venmo type service

MVP

1. Users should be able to pay or request to other users through "posts"
2. Users should be able to set posts to private or public
3. Users should be able to write an optional message on posts
4. Users can like posts on feeds

#### Solution

[Schema Diagram](https://app.quickdatabasediagrams.com/#/d/sPcD1E)

### Notes

- Feel free to not give them the MVP as they can discuss it with the interviewer
- One of the hard parts about this question is realizing that even though this is a payment platform, it's a social payment platform which means how users pay is through "posts" with a set level of visibility so try to steer them towards the posts idea
- The other hard part about this question is the friendship (self referencing many to many relationship) portion. It's highly encouraged in Venmo to not send money to a user that's not an added friend
