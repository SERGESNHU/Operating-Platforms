# CS 230 Portfolio — Draw It or Lose It Software Design Document

## About This Project

This repository contains the completed software design document created for The Gaming Room as part of CS 230: Operating Platforms at Southern New Hampshire University. The document was built across multiple projects throughout the course and covers the full design process from the initial executive summary through platform evaluation and final architecture recommendations.

---

## Client Summary

The Gaming Room is a company that had an existing mobile game called Draw It or Lose It, which at the time was only available on Android. The game is loosely based on the old Win, Lose or Draw television show from the 1980s where teams compete to guess what is being drawn on screen. Images from a stock library are revealed over the course of a one-minute round and teams have to guess the puzzle before time runs out. My job as a technology consultant for Creative Technology Solutions was to design a web-based version of the game that could run across multiple platforms, not just Android. The client needed the game to support multiple teams and players, enforce unique game and team names, and only ever run one instance of the game in memory at a time. The software design document is what I put together to show them how that could be done.

---

## Reflection

**What did you do particularly well in developing this documentation?**

The platform evaluation table came out well. Going through each operating platform for server side, client side, and development tools and actually thinking through the tradeoffs for each one instead of just listing features was useful. The domain model section also felt solid. Breaking down the UML class diagram and explaining how Entity, Game, Team, and Player all connect through inheritance, and why the singleton pattern in GameService directly addresses what the client asked for, made that section feel like it actually meant something rather than just describing the diagram.

**What about the process of working through a design document did you find helpful when developing the code?**

Having the UML diagram and the requirements written out before writing any code made it a lot clearer what each class was supposed to do. When I got to actually implementing the singleton pattern in GameService or writing the iterator logic for checking unique names, I already knew what the expected behavior was because it was spelled out in the design document. Without that it would have been easy to write code that technically runs but does not actually meet the client's requirements. The design doc forced me to think about the problem before jumping into the solution.

**If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?**

The Requirements section is the one I would go back to. It is the shortest section in the document and it is not being graded, but it is also the section that everything else is built on. A more thorough breakdown of business versus technical requirements, with more specific detail about things like expected user load and performance targets, would have made the later sections easier to write and more grounded. Right now it reads like a quick list. It could be a lot more useful as a reference.

**How did you interpret the user's needs and implement them into your software design? Why is it so important to consider the user's needs when designing?**

The client's requirements came through pretty clearly in the project description so interpretation was mostly about understanding what those requirements actually meant in practice. The single-instance requirement for example sounds simple but in a distributed web environment it has real implications for how GameService has to be structured. The name uniqueness requirement meant the iterator pattern had to be applied in specific places. Getting those details right in the design phase meant the code could reflect what the client actually needed instead of just what seemed logical to build. User needs matter in design because if you build the wrong thing in a technically correct way you still built the wrong thing. The design process is where you catch those mismatches before they become expensive to fix.

**How did you approach designing software? What techniques or strategies would you use in the future to analyze and design a similar software application?**

The approach here was to start with the client requirements, translate them into a domain model using UML, identify which design patterns applied to the specific problems in the requirements, and then document the platform and architecture decisions that would support the deployment of the application. For a future project I would keep that same sequence but spend more time on the requirements phase before moving to the model. I would also look harder at failure cases earlier, things like what happens when a network connection drops mid-game or what the behavior should be if the server restarts while a session is active. Those edge cases did not really get addressed until the distributed systems section and they probably should have been part of the initial design conversation with the client.

---

## Files in This Repository

- `CS230_ProjectThree_SoftwareDesign_Traudt.docx` — Completed software design document covering executive summary, requirements, design constraints, domain model, platform evaluation, and architecture recommendations for The Gaming Room
