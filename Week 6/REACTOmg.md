# FSA Lesson Plan

## REACTO - Hard Problems

### Daily Objectives

Students will be able to:

- Break down a purposefully open-ended "Hard" whiteboarding problem into several discrete and solvable sub-problems
- Implement a breadth or depth-first traversal of an adjaceny matrix and discuss tradeoffs
- Implement a Class pattern for a custom Data Structure (Offices)

### Key Topics

- Adjacency Matrix
- Object Oriented Design
- Graph traversal
- Breadth-first
- Depth-first


### Lesson


### Prompt

Imagine you are programming a Roomba to clean every room in an office. Your Roomba has three pre-built methods:

* `isCurrentRoomDirty() //returns Boolean if current room needs cleaning)`

* `cleanRoom() //cleans dirty room Roomba is currently in`

* `move(directionString) // consumes a string ('North', 'South', 'East', 'West') and attempts to move to next room in that direction`

Create a `cleanFloor()` method, which traverses all the available rooms on a floor and cleans the dirty offices. You may use the above methods, as well as any custom helper functions you deem necessary.


#### Further Considerations

- What data structures will you use to represent a floor plan? How about an office? You may assume all offices are accessable through at least one door.

- Can you travel from one room to any of it's neighboring rooms? If not, how will we represent doors versus walls?

- Does your Roomba have a floorplan of the office stored in memory, or does it create the floorplan dynamically?

- Does your Roomba travel along predefined paths?


|           | Assets             | Time  |
| ------------- |:---------------------: | -----:|
| **Sample REACTOmg Slides**   | [REACTOmg](https://drive.google.com/open?id=1adyo55u9oqAc_7rOOcu8LsIXFb5uvzG7)  |      |
| **Sample REACTOmg Video** | [1911-GH by Natalie](https://www.youtube.com/watch?v=c6_1Y3MH4ZE&feature=youtu.be) | ~1 HR


### REACTO Prompts

|           | Assets             | Time  |
| ------------- |:---------------------: | -----:|
| **Rain Collecter** | [Rain Collecter][rain] | ~1 HR |
| **Balanced Brackets** | [Brackets][brackets] | ~1 HR |


[rain]: https://github.com/FullstackAcademy/technical-interview-prep/blob/master/algorithms/7-mix/2-rain-water-collector.md
[brackets]: https://github.com/FullstackAcademy/technical-interview-prep/blob/master/algorithms/7-mix/1-balanced-brackets.md
