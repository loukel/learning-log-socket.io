# Learning Log For improving at React and Sockets

## Widgets and introduction(16/03/22)

I work as a web developer for a company in a team of web developers who are creating a web app for fellow videographers to help manage everything related to their projects. My goal for this learning venture is to improve my skills in React and sockets. I'm hoping that from improving my knowledge and experience using React and sockets I can create a concise and efficient guide for learners so that my web developer associates can use it to utilise sockets with React. I aim to complete two components in the following order:
- Widgets Dashboard: for the home page of the app, users should be able to view widgets relating to different aspects of the app: budgets, equipment, projects etc. I want to be able to use React to create a dashboard for this. My goal is to set it up for the future so uses can drag different size cards about in a grid. Therefore, this can later be used to display the actual widgets where the user can move to them to view an overview of whats going on with their business.
- Kanban Board for project states: I've previously created a drag and drop kanban board where project states are displayed and can be changed. However, there is an issue when multiple users are editing the project states at the same time. I will need to implement sockets into the site, which will require knowledge of using sockets in the back-end and the front-end with React. I plan to ensure that the code readable and understandable to other web developers in the team that I am working with so that they can understand it and hopefully reuse some of the code for elsewhere in the app. I'm expecting that this part will be split up in several entries.
There may be other components of the web app that may need to be completed to achieve my goal of improving my skills in React and sockets. It will depend on the demands of what the team wants to achieve for the app.
My general goal is to add as many features to the web app so that they can release a minimum viable product as quickly as they can.

### Working on the widgets dashboard
To allow users to drag and drop cards on the dashboard, I first had to reseach react compatible drag and drop packages. The best one I could find was [react-grid-layout](https://react-grid-layout.github.io/react-grid-layout/examples/0-showcase.html). I learned how to use it by going through all of their examples and tried to apply to the dashboard I wanted to create. I then had to use it with React and bootstrap. I learned how to do this using trial and error trying different things out until it worked accordingly. The documentation wasn't too detailed so it so I had to go through the source code of the examples and try to understand how it works.
Here is the pull Request I created, which was approved by Elliot, a team member who went over my code approved it, then merged it into the project. We collaborated by him checking the code and merging it, which is a great habbit to prevent issues in the future if there is some code that could malicously affect the rest of the project.
![Pull Request for widgets](/screenshots/widgets-pr.png)
This is the main code for the widgets.
![The main code used for the widgets](/screenshots/widgets-code.png)
This is what the widgets dashboard looked like.
![What it looked like](/screenshots/widgets-view.png)
Completing the widgets dashboard, mainly enabled me to learn about available react drag and drop packages and how to use them, mainly react-grid-layout. For this learning venture, I hope to learn more about React and sockets in my next entry so I can achieve my goal of improving my knowledge and experience in React and sockets.

## Making Budgets for Projects with Sockets (07/04/22)
In this entry, I set up sockets for the budget section of the app where the finances of a project can be broke down, users need to be able to edit a budget at potentially the same time as other users therefore sockets will need to be utilised. I set it up in the back end and the front end of the app. I made two pull requests to the back-end of the project, and one pull request to the front-end of the project. The sockets that were implemented only allows a budget to be fetched but it also allows for the number of users currently editing the budget to be tracked.
![Pull Request for get budgets socket back](/screenshots/budget-sockets-back-1.png)
You can see that one of the developers, Elliot, I work with reviewed my code and approved it. It was the merged the project. In this pull request, I add Socket IO to the back-end and set up the socket initialisation with the front end. Clients will be able to connect up with the sockets and the selected budget can be fetched utilising sockets.
![Pull Request for get budgets socket back 2](/screenshots/budget-sockets-back-2.png)
Elliot and Ahmed then approved the second pull request to the back end of the project. In this pull request I fixed issues with the sockets functionality where the number of users editing a budget updates wasn't updated when a user left the budget.
I improved my knowledge of sockets here by learning how to set the connection up on the server and how to connect to those sockets with react - sending and receiving data. I also learnt how to store the data with redux which made it easier to use the data in the budget components.
I think I want to focus on learn the best ways on implementing sockets with React - is it better to use Redux or not? what is the best way to modularise the socket functionality.
My next plan is to implement the update and create functionality so that the user can update - change the order and data of budget lines, headings and sub headings - and create new lines, headings and sub headings.

## Updating the order of lines in a budget with Sockets (13/04/22)
In this entry, I submitted multiple pull requests to the back-end and front-end on the work project that I am working on. I added a function that allowed for lines in the budget to be reordered, this uses an abstract singly linked list in the database where each line points to the next within its category. 

https://user-images.githubusercontent.com/65136145/163256211-be6685f2-4038-46b0-b494-806cfd101437.mp4

This video shows two clients, updating the order of lines on one client updates it for all clients.

<img width="831" alt="Front End Pull Request" src="https://user-images.githubusercontent.com/65136145/163858231-d946e32c-009d-49d8-afba-2e1c56f68364.png">
This is the front end pull request, adding the new function with sockets. Ahmed went through my code and approved it - it was then merged.

<img width="847" alt="Screenshot 2022-04-18 at 19 34 58" src="https://user-images.githubusercontent.com/65136145/163859029-cc0e1f1a-37f2-427f-b7d2-c50a939cb34a.png">
This is the back end pull request that I made, it was reviewed and approved by Ahmed. This pull request covered the code which enabled users to drag lines within their category changing the order of which they are displayed.

I learnt more about socket rooms, specifically about how to send data, if I wanted to send data back to the socket (that sent the data) and the room then you would use `io.to(roomId).emit(<message>, <data>)`. However, if you want to send it to just the room and not the socket you would use `socket.to(roomId).emit(<message>, <data>)`. I found the distinction between these message senders was very important therefore improving my knowledge of sockets (socket.IO).

I overestimated the amount of work that I am capable of doing in the time I have available so my goal has been lowered to just trying to develop the project budgets section by adding as much flexibility with reordering lines - being able to move them to other categories. I should be able to become more comfortable with using React with sockets by doing so.
