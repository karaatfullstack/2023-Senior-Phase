# Grace Shopper Sprint Meeting

(Formally known as "Code Reviews")

## Overview

Both Grace Shopper and Capstone projects are intended to serve as "Job Simulations" for students. In keeping with this, Grace Shopper has two scheduled "Sprint Meetings", in which Instructors, Students and their assigned Fellow will review their project's progress, give and receive feedback on relevant code, discuss blockers, and organize tasks for the next sprint.

Please note that the following flow is *recommended* but not mandated. Instructors should feel free to supplement with any of their chosen personal Code Review practices

### Roles

* **Product Owner (Instructor)**
    
    * Prioritizes Product features to implement

    * Directs technical implementation of Product 

    * Reviews and gives feedback on project codebase 

* **Project Manager (Fellow)**

    * Leads daily standups

    * Advises on technical implementation and task breakdown

    * Tracks team progress and reports to Product Owner

* **Engineers (Students)**

    * Architect, engineer, and deploy product

    * Write and assign engineering tickets within group

## Sprint Meeting I 

### Flow + Objectives

* **Project Overview** (*Taskboard, Git Commits, Readme*)
    
    * Audit taskboard for sensible User Stories/task breakdown and fair distribution of tasks between engineers

    * Ensure team follows collaborative branch-based Git collaboration strategy and writes semantic commits

    * Review Project README to ensure it includes description of Product, collaborators, installation instructions and link to deployed version

    * Estimated length: 10 mins

* **Code Review** (*API*)

    * Comprehensive review of technical implementation of User, Product, Order, and OrderProduct Schemas in Sequelize, as well as Cart logic

    * Discuss tradeoffs and potential areas of technical debt in different Schema, Property, and Cart implementations

    * Instructors may give written feedback either in-line on a branch, or in a separate document which they share with students

    * Estimated Length: 25 mins

* **Feature Roadmap** (*Tier I, Cart, Security*)

    * Discuss remaining features to implement to complete Tier 1, including task breakdown and technical architecture

    * Discuss strategies for Cart logic, namely tradeoffs between `localStorage` and server-side implementations.

    * Discuss security best practices in Express, and relevant routes to protect

    * Estimated Length: 15 mins

* **Ticket Writing**

    * Fellow PM (Under Instructor Supervision) will lead the team in authoring relevant User Stories and Tasks based on the Feature Roadmap Discussions

    * Estimated Length: 10 mins


#### Sample Student Messaging

*The upcoming Sprint Meeting is meant to simulate the product planning and review practices typical to modern engineering shops. To that end, please note the "roles" Instructors, fellows, and students will play during throughout the project.*


* **Instructor**, *Product Owner*

    * Prioritizes Product features to implement

    * Directs technical implementation of Product 

    * Reviews and gives feedback on project codebase 


* **Fellow**, *Technical Project Manager*

    * Leads daily standups

    * Advises on technical implementation and task breakdown

    * Tracks team progress and reports to Product Owner

* **Students**, *Engineers*

    * Architects, engineers, and deploys product

    * Writes and assigns engineering tickets within group

*While a substantive portion of the meeting will focus on a code review of your project's codebase, Instructors and fellows will lead your team on a holistic overview of your project's progress, including (but not limited to) Agile task breakdown, git collaboration, schema design, technical architecture, feature roadmapping, testing, security, deployment, and documentation.*

*This coming Sprint Meeting will focus on your Shopper's API layer. Please note that all students are expected to participate in these meetings. Come prepared with questions to ask of the Product Owner (Instructors), as well as ready to talk about the technical choices you have and will make while working on the project. While Product Owners (Instructors) may give written feedback on your project, we advise that you work with the team to take notes to guide your project moving forward.*

## Sprint Meeting II

### Flow + Objectives

* **Project Overview** (*Deployed MVP*)

    * Audit deployed Tier I in the browser noting any bugs, UX concerns, or broken features.

    * For any major breakages, triage and discuss relevant code blocks to strategize for any "on fire" debugging

    * Estimated time: 10 mins

* **Code Review** (*Tiers I, II*)

    * Comprehensive review of technical implementation of Tiers I and II, potentially including any Tier III features accomplished

    * Audit code quality on master branch, reinforcing style best-practices for any portfolio-facing code project (e.g, testing, no console logs, documentation, semantic variable names, consistent formatting, etc.)

    * Instructors may give written feedback either in-line on a branch, or in a separate document which they share with students

    * Estimated Length: 20 mins

* **Feature Roadmap**

    * Discuss remaining features to implement to complete whichever Tier they are on, including task breakdown and technical architecture

    * *Product Owner* will share "last minute" feature requests from client, and lead discussion on technical architecture and implementation. Features can be creatively generated by the Instructors and may include:
       
        * 50% off Promo Code

        * Data Viz dashboard for marketing team

        * Pagination on all products list

        * Cryptocurrency Payments

        * etc...

    * Estimated Length: 15 mins

* **Ticket Writing**

     * *Fellow PM* (Under Instructor Supervision) will lead the team in authoring relevant User Stories and Tasks based on the Feature Roadmap Discussions. PM + PO will ensure students are well equipped to complete a project meeting *at least* Tier I goals

    * Estimated Length: 10 mins

#### Sample Student Messaging

*The upcoming Sprint Meeting is meant to simulate the product planning and review practices typical to modern engineering shops. To that end, please remember the "roles" Instructors, fellows, and students will play during throughout the project.*

*While a substantive portion of the meeting will focus on a code review of your project's codebase, Instructors and fellows will lead your team on a holistic overview of your project's progress, including (but not limited to) Agile task breakdown, git collaboration, schema design, technical architecture, feature roadmapping, testing, security, deployment, and documentation.*

*This coming Sprint Meeting will focus on the deployed MVP for your Shopper. Please note that all students are expected to participate in these meetings. Come prepared with questions to ask of the Product Owner (Instructors), as well as ready to talk about the technical choices you have and will make while working on the project. While Product Owners (Instructors) may give written feedback on your project, we advise that you work with the team to take notes to guide your project moving forward.*

### Additional Resources

* [Stack Overflow Guide to Code Reviews](https://stackoverflow.blog/2019/09/30/how-to-make-good-code-reviews-better/)

* [Ben's Extensive Grace Shopper Notes](https://hackmd.io/@2ctk-Q4uQAmhb4qw1GghPA/H1mtXntPF)

