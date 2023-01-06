# FSA Lesson Plan

## REACTO - System Design

### Daily Objectives

Students will be able to:

- Discuss approaches to scaling a software prototype, as well as use-cases for caches, load-balancers, and microservices.
- Discuss the philosophy of "Chaos Engineering", and intentially seeking out breakpoints at the service of building better software.

### Needs Statement

Students need to understand where and how to start scaling (and/or) maintaining a system. This will help them understand and have conversations about potential bottlenecks and how to identify them and mitigate them in the future.

### Key Topics

- Scalability
- Cache
- Load Balancer
- Microservices
- Queues
- Chaos engineering

### Format

- Characteristics of Systems
- Load Balancers
- Caches
    - Cache Eviction Policies
        - Use Cases for each listed
- Queues
    - Use Cases: Email, WhatsApp, Throttling
- Microservices
    - Use Case: Uber
    - Use Case: Netflix
- The Secret Sauce of Scaling
- Chaos Engineering
- [If there's time] - Walkthrough of a warmup system design problem by designing a Grocery Store checkout line using the principles just learned.

![Grocery Store Checkout](./assets/grocery-store.png)

### Assets


|           | Assets             | Time  |
| ------------- |:---------------------: | -----:|
| **Sample System Design Slides**   | [System Design](https://drive.google.com/file/d/1Wln1sWneRmPv2CETmz0RQbsSfhrus7VN/view?usp=sharing)  |      |
| **Sample System Design Video** | [1904-FSA by Ben](https://www.youtube.com/watch?v=EI8pKit4gKM&feature=youtu.be) | ~1 HR


### REACTO Prompts

|           | Assets             | Time  |
| ------------- |:---------------------: | -----:|
| **System Design: Fandango I: Schema Design and API Design** | [System Design: Schema and API Design Fandango][fandango-i] | ~1 HR |
| **System Design: Fandango II: Load Balancers, Caches, and Microservices** | [System Design: Fandango II][fandango-ii] | ~1 HR |

[fandango-i]: https://github.com/FullstackAcademy/technical-interview-prep/blob/master/REACTO-problems/04-system-design/02-fandango-I.md
[fandango-ii]: https://github.com/FullstackAcademy/technical-interview-prep/blob/master/REACTO-problems/04-system-design/03-fandango-II.md

## Resources

- [Stackshare](https://stackshare.io/)
- [High Scalability Blog](highscalability.com/)
- [Uber Engineering Blog](https://eng.uber.com)
- [Netflix Blog](https://medium.com/netflix-techblog)
- [Netflix: Chaos Monkey Repo](https://github.com/Netflix/chaosmonkey)
- [System Design Github Repo](https://github.com/donnemartin/system-design-primer#step-1-review-the-scalability-video-lecture)

## Notes

- The current video listed is from the first iteration of system design done in 1904 so it's not the abridged, more targeted version.
- Instructors can further decrease the time of this lecture by not including the characteristic slides and the queue slides. That would decrease the number of slides from 37 to 24.
