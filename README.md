# Learning Log for Improving and Learning to React and Sockets

## Widgets and Introduction(16/03/22)

I work as a web developer in a team for a company who are creating a web app for fellow videographers (filming, editing and directing) to help manage everything related to their projects. I'm hoping to improve my knowledge and experience with using Sockets with React. I aim to complete the two components in the following order:
- Widgets Dashboard: users should be able to view widgets relating to different aspects of the app: budgets, equipment, projects etc. Users should be able to drag different size cards about in a grid like format.
- Kanban board for project states: I've previously created a drag and drop kanban board where project states are displayed and can be changed but this fetches data using a REST API. However, there is an issue when multiple users are editing the project states at the same time, this would be fixed with sockets.
There maybe other features to build but it will depend on the demands of the team and what they want to achieve for the app at this time, all features that I will do will help me to improve with React and Sockets.

### Working on the widgets dashboard
First, I had to research React compatible drag and drop packages and the best one I could find was [react-grid-layout](https://react-grid-layout.github.io/react-grid-layout/examples/0-showcase.html). Using the examples they provided and trying apply it to the dashboard was the best way to learn it. The documentation wasn't too detailed so it was quite difficulte to use. But the end result was quite good though a bit unsmooth.
Here's the pull Request I created, which was approved by Elliot, a team member who reviewed my code and approved it.
![Pull Request for widgets](/screenshots/widgets-pr.png)
This is the main code for the widgets.
![The main code used for the widgets](/screenshots/widgets-code.png)
This is what the widgets dashboard looked like.
![What it looked like](/screenshots/widgets-view.png)
Completing this, enabled me to learn about the available react drag and drop packages and how to use them, mainly learning react-grid-layout but overall I improved my knowledge of React. I'd like to focus more on sockets in the next entries. My team wants me to approach the budget section of the app which I will detail more in the next section.

## Budgets for Projects using Sockets (07/04/22)
I created the socket functionality for the budget section of the app, this is where the finances of a project can be broke down. Multiple users need to be able to edit a budget at potentially the same time. Therefore, this is prime for sockets. I set it up in the back and front end, requiring multiple pull requests. This was my first implementation of sockets into the app; I had to learn how to use sockets. I did so by watching YouTube tutorials and reading the socket IO documentation (https://socket.io/get-started/chat). It was also useful to look up existing projects with React, on GitHub, that also used sockets to get an idea on how to layout them on and split the functions up elegantly. The functionality allows for budgets to be fetched and display the live number of users currently editing.
### Pull Requests
![Pull Request for get budgets socket back](/screenshots/budget-sockets-back-1.png)
I added Socket IO to the back-end and set up the socket initialisation with clients. Utilising sockets the budget can be fetched client side. Users are able to join rooms that are created for each budget. Elliot reviewed my code and approved the pull request. 

![Pull Request for get budgets socket back 2](/screenshots/budget-sockets-back-2.png)
I then fixed issues relating to the number of users editing a budget updates not being updated when a user left the budget.

![front-end PR for setting budgets up](https://user-images.githubusercontent.com/65136145/164986061-49b67505-8832-405d-bd70-bff9e94e6b21.png)
This set up all the redux functionality for the budgets to work with sockets. This involved setting up the redux state, actions and organising the existing file structure to flow with sockets. It was useful to use this repository https://github.com/Gethyl/RealTimeTodo as an example of how to use sockets.

### What I learned
I researched how to set and implement sockets up on express server - how to initilise the connection, how to send and receive messages. Something key to socket.IO that I learnt was how to set rooms up for users to join. The documentation for socket.IO rooms was very concise and clear and was all that I needed to utilise them (https://socket.io/docs/v3/rooms/). Using Redux was the best way to use sockets with React as it hid the complexity of sockets from the components. Therefore, the components only had to fetch and update the global state that redux provided. I learnt how to initialise the socket connection with redux so that data was stored in the redux state when appropriate. I also learnt how to set up actions so that the socket messages could be send and received from the client.
My next plan is to implement the functionality so that lines, headings and sub headings can be moved around which implementing different functions which manipulate data. This will greatly test my ability and push me to improve my knowledge of sockets as when data is being manipulated it is important that every user see's the correct data - especially in this case since the order of the entities are stored using a linked list. If a user has the incorrect data and they attempt to update the order of the linked list then it is very likely that the list will become corrupt (eg. nextId is equal to itself).

## Updating the order of lines in a budget with Sockets (13/04/22)
I added a function, on the server, that lines to be reordered in the budget. I then connected this function up with the front-end so when a user drags a line to a new position it would update it in the database and on render the changes for every other editing user (clients).

https://user-images.githubusercontent.com/65136145/163256211-be6685f2-4038-46b0-b494-806cfd101437.mp4

This video shows two clients - updating the order of lines on one client updates it for all clients (I'm using two private windows to replicate the idea of multiple clients, this is something I learnt to test the functionality of sockets).

<img width="831" alt="Front End Pull Request" src="https://user-images.githubusercontent.com/65136145/163858231-d946e32c-009d-49d8-afba-2e1c56f68364.png">
Here I add the new interoperability function with sockets on the front-end. Ahmed went through my code and approved it - it was then merged.

<img width="847" alt="Screenshot 2022-04-18 at 19 34 58" src="https://user-images.githubusercontent.com/65136145/163859029-cc0e1f1a-37f2-427f-b7d2-c50a939cb34a.png">
This pull request covered the back-end code which enabled users to drag lines within their category, changing the order of which they are displayed. It was reviewed, approved and merged by Ahmed

I learnt more about socket rooms, if I wanted to send data to the room and the socket that sent the data then you would use `io.to(roomId).emit(<message>, <data>)`. However, if you want to send it to just the room and not the socket you would use `socket.to(roomId).emit(<message>, <data>)`. I found the distinction between these message senders really important. Therefore improving my knowledge of socket.IO. This Stackoverflow post really helped with understanding the difference https://stackoverflow.com/questions/32674391/io-emit-vs-socket-emit.

I overestimated the amount of work that I am capable of doing in the time that I have available, my goal has been lowered to just trying to get the project board finished with sockets and leaving the project budgets for another time. I should be able to become more comfortable with using React with sockets by doing so.

## Implementing sockets into a Kanban Board (23/04/22)
A Kanban board looks like this:
![Kanban Board](/pictures/kanban_board_example.jpg)
Where there are multiple columns and items. But in this project, I want to implement a kanban board where items are projects and columns are project states - such as to do, in progress, done.

https://user-images.githubusercontent.com/65136145/164943062-59ace19f-c293-4c67-a970-9339d981479b.mov

This video shows the finished result - I reorder projects, move projects to other columns, reorder the columns and I can even hide and edit the labels of columns.

There are some visual bugs with the board which you may be able to see in the video, they will need to be fixed in the future. There also could be a better way to store functions, the way I've done it now to modularise the sockets is quite good but I believe with more time, experience and research I will find a better way to structure them.

These are the two pull requests I made into the project, they were later reviewed and approved by the team.
![Kanban Board](/screenshots/Back-end_PR_for_sockets_board.png)
![Kanban Board](/screenshots/front-end_PR_sockets_board.png)

I think my goal to learn and become comfortable with using sockets with React is complete, as I am able to confidently utilise complicated functions that involve drag and drop and linked lists whilst, on the front-end, storing the data in the react global state with redux. To carry on my learning venture with sockets, I should try to complete the budgets along with my work colleagues who are currently trying to finish the feature.
<!-- Inaccurate entry dates (git history) due format changes -->
